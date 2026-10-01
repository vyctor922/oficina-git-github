# Integração de Históricos Git Locais

Este guia mostra como integrar o histórico de um repositório Git local a outro, quando um projeto foi iniciado em um repositório e posteriormente continuado em outro.

O objetivo é transformar:

```text
Repositório anterior:
A ── B ── C

Repositório novidade:
X ── Y ── Z
```

em:

```text
A ── B ── C ── Y ── Z
```

O procedimento usa `git rebase --onto` para reaplicar os commits feitos na novidade a partir do último commit do histórico anterior.

> Importante: o rebase recria os commits reaplicados. Portanto, os hashes desses commits podem mudar.

---

## 1. Cenário

Considere dois repositórios locais:

```text
C:\Projetos\anterior
C:\Projetos\novidade
```

O repositório `anterior` possui:

```text
A ── B ── C
```

O repositório `novidade` foi iniciado posteriormente, possivelmente por cópia manual dos arquivos, e possui:

```text
X ── Y ── Z
```

Queremos integrar os históricos.

---

## 2. Trabalhe em uma branch de segurança

Entre no repositório que será utilizado como base da integração:

```bash
cd "C:\Projetos\anterior"
```

Crie uma branch para não trabalhar diretamente na `main` ou `master`:

```bash
git switch -c backup
```

Essa branch funciona como ponto de segurança antes da reescrita do histórico.

---

## 3. Adicione o outro repositório como remote local

Adicione o repositório que contém a continuação do projeto:

```bash
git remote add novidade "C:\Projetos\novidade"
```

Confira o remote:

```bash
git remote -v
```

O resultado deve mostrar algo semelhante a:

```text
novidade  C:\Projetos\novidade (fetch)
novidade  C:\Projetos\novidade (push)
```

Essa verificação é opcional e não modifica o histórico.

---

## 4. Busque o histórico da novidade

Execute:

```bash
git fetch novidade
```

Agora o histórico do outro repositório está disponível localmente.

Para visualizar os dois históricos:

```bash
git log --oneline --graph --decorate --all
```

Essa etapa é apenas de conferência.

---

## 5. Identifique os commits

No exemplo:

```text
Anterior:

A ── B ── C
          ↑
    último commit anterior
```

e:

```text
Novidade:

X ── Y ── Z
↑
primeiro commit da novidade
```

Precisamos dos hashes de:

```text
[hash final anterior] = C
[hash inicial em novidade] = X
```

Por exemplo:

```text
C = b50896f
X = 936d3cf
```

---

## 6. Faça uma checagem antes do rebase

Antes de integrar, compare o estado final do histórico anterior com o estado inicial da novidade:

```bash
git diff --stat [hash final anterior] [hash inicial em novidade]
```

Exemplo:

```bash
git diff --stat b50896f 936d3cf
```

### Se não aparecer nada

Se o comando não produzir nenhuma saída, os dois commits possuem o mesmo estado dos arquivos.

Isso significa que:

```text
C
```

e:

```text
X
```

representam o mesmo estado do projeto, embora sejam commits diferentes e pertençam a históricos independentes.

Nesse caso, você pode seguir diretamente com o rebase:

```bash
git rebase --onto [hash final anterior] [hash inicial em novidade] novidade/master
```

Exemplo:

```bash
git rebase --onto b50896f 936d3cf novidade/master
```

O resultado será:

```text
A ── B ── C ── Y' ── Z'
```

Os commits posteriores a `X` são reaplicados depois de `C`.

Se `novidade` tiver 3, 200 ou 2000 commits depois de `X`, o princípio é o mesmo. O Git reaplicará toda a sequência posterior a `X`.

---

## 7. Se o `git diff --stat` mostrar diferenças

Se:

```bash
git diff --stat [hash final anterior] [hash inicial em novidade]
```

mostrar arquivos ou alterações, então o estado de `C` e `X` não é igual.

Nesse caso, não é recomendável assumir automaticamente que `X` pode ser simplesmente descartado.

Você pode primeiro analisar as diferenças:

```bash
git diff [hash final anterior] [hash inicial em novidade]
```

Depois, decidir se deseja:

1. resolver manualmente as diferenças antes da integração;
2. fazer a integração e resolver eventuais conflitos;
3. ou utilizar outra estratégia de integração.

O rebase continua podendo ser usado, mas o resultado precisa ser conferido.

---

# 8. Opcional: preservar X para obter A → B → C → X → Y → Z

O rebase anterior normalmente produz:

```text
A ── B ── C ── Y' ── Z'
```

porque o comando:

```bash
git rebase --onto C X novidade/master
```

significa:

> Pegue os commits depois de `X` e reaplique-os depois de `C`.

Portanto, o próprio `X` fica de fora.

Se `X` e `C` possuem o mesmo estado dos arquivos, mas você deseja manter também o commit `X` na sequência:

```text
A ── B ── C ── X' ── Y' ── Z'
```

é possível fazer isso opcionalmente.

A ideia é preservar `X` como um novo commit depois de `C` e, depois, reaplicar todos os commits posteriores.

---

## 9. Cherry-pick opcional

Depois de colocar o histórico anterior como base, crie a sequência usando `cherry-pick`.

O princípio é:

```text
A ── B ── C
          ↓
          X'
          ↓
          Y'
          ↓
          Z'
```

Para poucos commits, pode-se fazer:

```bash
git cherry-pick X --no-commit
```

Porém, quando `X` possui exatamente o mesmo conteúdo de `C`, o Git pode informar que o cherry-pick ficou vazio.

Nesse caso, se o objetivo for preservar o commit como registro histórico, pode-se criar o commit manualmente:

```bash
git commit --allow-empty -m "mensagem de X"
```

Depois, os commits seguintes podem ser reaplicados:

```bash
git cherry-pick Y Z
```

---

## 10. Quando existem muitos commits na novidade

A novidade pode possuir apenas:

```text
X ── Y ── Z
```

ou milhares de commits:

```text
X ── Y ── Z ── ... ── 1998 ── 1999 ── 2000
```

Não é necessário escrever todos os hashes manualmente.

É possível selecionar um intervalo de commits:

```bash
git cherry-pick X..novidade/master
```

Isso significa:

> Aplique todos os commits posteriores a X até o commit atualmente apontado por `novidade/master`.

Assim, para:

```text
X ── Y ── Z ── ... ── 2000
```

o comando:

```bash
git cherry-pick X..novidade/master
```

aplica:

```text
Y ── Z ── ... ── 2000
```

de uma vez.

---

# 11. Resumo do fluxo normal

Quando o último commit do histórico anterior e o primeiro commit da novidade possuem o mesmo estado:

```bash
git switch -c backup

git remote add novidade "C:\Projetos\novidade"

git remote -v

git fetch novidade

git log --oneline --graph --decorate --all

git diff --stat [hash final anterior] [hash inicial em novidade]

git rebase --onto [hash final anterior] [hash inicial em novidade] novidade/master
```

Resultado:

```text
A ── B ── C ── Y' ── Z'
```

---

# 12. Fluxo opcional mantendo X

Se o objetivo for preservar a sequência:

```text
A ── B ── C ── X ── Y ── Z
```

e `X` possui o mesmo estado de `C`, o `rebase --onto` sozinho não mantém `X`.

Nesse caso, é necessário tratar `X` separadamente e depois reaplicar os commits posteriores, por exemplo:

```bash
git cherry-pick X --no-commit
```

e, se o cherry-pick ficar vazio:

```bash
git cherry-pick --abort
git commit --allow-empty -m "mensagem de X"
```

Depois:

```bash
git cherry-pick X..novidade/master
```

Assim, mesmo que a novidade tenha centenas ou milhares de commits, o intervalo permite reaplicar toda a sequência posterior automaticamente.

---

# 13. Atenção aos hashes

Após um rebase ou cherry-pick, os commits reaplicados normalmente recebem novos hashes.

Por exemplo:

```text
Antes:

X ── Y ── Z
```

pode se tornar:

```text
Depois:

X' ── Y' ── Z'
```

Isso é esperado.

As mensagens, autores e alterações podem ser preservados, mas o hash muda porque o commit passa a possuir outro commit pai.

---

# 14. Conferindo o resultado

Depois da integração:

```bash
git log --oneline --graph --decorate --all
```

Para o fluxo normal, o esperado é algo como:

```text
* Z'
* Y'
* C
* B
* A
```

Para o fluxo opcional que mantém o primeiro commit da novidade:

```text
* Z'
* Y'
* X'
* C
* B
* A
```

---

# 15. Regra principal

O comando:

```bash
git rebase --onto C X novidade/master
```

significa:

```text
Pegue tudo depois de X
e coloque depois de C.
```

Portanto:

```text
A ── B ── C

X ── Y ── Z
```

vira:

```text
A ── B ── C ── Y' ── Z'
```

Se você também quiser manter `X`:

```text
A ── B ── C ── X' ── Y' ── Z'
```

será necessário tratar `X` separadamente, por exemplo com `cherry-pick`.

O procedimento é aplicável tanto para uma novidade com 3 commits quanto para uma novidade com centenas ou milhares de commits.
