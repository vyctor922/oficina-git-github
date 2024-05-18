# ATIVIDADES DA OFICINA

---

### Atividade: Trabalhando com Branches

**Objetivo:** Criar, alternar e mesclar branches.

**Passo a Passo:**

1. **Criar uma Nova Branch:**
   - Verifique a branch atual:
     ```sh
     git branch
     ```
   - Crie uma nova branch:
     ```sh
     git branch minha-nova-branch
     ```
   - Mude para a nova branch:
     ```sh
     git checkout minha-nova-branch
     ```
   - Verifique novamente a branch atual para confirmar:
     ```sh
     git branch
     ```

1. **Fazer Alterações e Commit:**
   - Faça alterações em um arquivo (por exemplo, edite `README.md`).
   - Adicione as mudanças ao staging:
     ```sh
     git add README.md
     ```
   - Faça o commit:
     ```sh
     git commit -m "Atualização README" -m "Atualização no README na minha nova branch"
     ```

1. **Mesclar a Branch:**
   - Mude de volta para a branch principal:
     ```sh
     git checkout main
     ```
   - Mescle as mudanças da nova branch:
     ```sh
     git merge minha-nova-branch
     ```

---

### Atividade: Prática com GIT

**Objetivo:** Praticar operações básicas com GIT.

**Passo a Passo:**

1. **Fork do Repositório:**
   - No GitHub, acesse o repositório [oficina-git-github](https://github.com/vyctor922/oficina-git-github) e clique em "Fork" para criar uma cópia no seu perfil.

1. **Clonar o Repositório Forkado:**
   - No terminal, clone seu fork:
     ```sh
     git clone https://github.com/seu-usuario/<nome-do-seu-fork-repositorio>.git
     ```

1. **Criar uma Branch para as Alterações:**
   - Navegue até o diretório do repositório clonado:
     ```sh
     cd <nome-do-repositorio>
     ```
   - Crie e mude para uma nova branch:
     ```sh
     git checkout -b minha-contribuicao
     ```

1. **Adicionar um Arquivo:**
   - Crie um arquivo chamado `index.txt` no diretório.

1. **Verificar o Status do Repositório:**
   - No terminal, verifique o status:
     ```sh
     git status
     ```

1. **Adicionar o Arquivo ao Stage:**
   - Adicione o arquivo para ser rastreado pelo Git:
     ```sh
     git add index.txt
     ```

1. **Confirmar a Alteração com um Commit:**
   - Faça o commit das alterações:
     ```sh
     git commit -m "seu título" -m "sua descrição"
     ```

1. **Enviar as Alterações para o Repositório Remoto:**
   - Atualize seu repositório local e envie as alterações:
     ```sh
     git fetch
     ```
     ```sh
     git pull
     ```
     ```sh
     git push
     ```

1. **Adicionar Conteúdo ao Arquivo:**
   - Adicione "hello world" ao `index.txt`:
     ```sh
     echo hello world > index.txt
     ```

1. **Verificar o Status do Repositório de Forma Compacta:**
    - Verifique o status de forma compacta:
     ```sh
     git status --short
     ```

    - Indicadores de status (--short):
      - `??` - Arquivos não rastreados
      - `A` - Arquivos adicionados ao stage
      - `M` - Arquivos modificados
      - `D` - Arquivos deletados

1. **Visualizar o Log do Repositório:**
    - Confira o log do repositório para ver as informações dos commits:
     ```sh
     git log
     ```

1. **Ver Detalhes de um Commit Específico:**
    - Com o ID de um dos commits no log, veja os detalhes do commit:
     ```sh
     git show <id_commit>
     ```

---

A partir daqui, apenas orientações:

- Faça alterações no `index.txt`, adicionando qualquer texto e confirme as alterações.
- Adicione uma imagem dentro de uma pasta chamada `img` no repositório e confirme as alterações.
- Delete a imagem do repositório e confirme a alteração.

---

- Gere um arquivo com a exportação do log do repositório:
  ```sh
  git log > saida.txt
  ```

- Adicione ao arquivo `saida.txt` a visualização do que fez no último commit:
  ```sh
  git show >> saida.txt
  ```

---

### Atividade: Uso de Pull Requests no GitHub

**Objetivo:** Contribuir para um repositório remoto utilizando pull requests.

**Passo a Passo:**

1. **Certifique-se de que Todas as Alterações Foram Enviadas:**
   - Garanta que não existem novas alterações para serem enviadas ao GitHub.

1. **Criar um Pull Request:**
   - No GitHub, navegue até o seu repositório forkado.
   - Clique no botão "Compare & pull request".
   - Adicione um título e uma descrição para o pull request.
   - Clique em "Create pull request".

---

### Atividade: Resolvendo Conflitos de Merge

**Objetivo:** Praticar a resolução de conflitos durante um merge.

**Passo a Passo:**

1. **Preparar o Ambiente:**
   - Crie um repositório local com dois branches: `main` e `feature`.
   - No branch `main`, adicione uma linha ao arquivo `README.md` e faça o commit.
   - No branch `feature`, adicione uma linha diferente ao mesmo arquivo e faça o commit.

1. **Tentar Mesclar os Branches:**
   - Mude para o branch `main`:
     ```sh
     git checkout main
     ```
   - Tente mesclar o branch `feature`:
     ```sh
     git merge feature
     ```
   - Um conflito de merge será gerado.

1. **Resolver o Conflito:**
   - Abra o arquivo `README.md` no editor de texto.
   - Encontre e resolva os conflitos (linhas marcadas por `<<<<<<`, `======`, `>>>>>>`).
   - Adicione as mudanças ao staging:
     ```sh
     git add README.md
     ```
   - Complete o merge:
     ```sh
     git commit
     ```

---

Essas atividades são práticas de fixação para auxiliar a compreensão dos conceitos de Git e GitHub.
