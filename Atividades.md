# ATIVIDADES DA OFICINA

---

### Atividade: Trabalhando com Branches

**Objetivo:** Criar, mudar e mesclar branches.

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

2. **Fazer Alterações e Commit:**
   - Faça alterações em um arquivo (por exemplo, edite `README.md`).
   - Adicione as mudanças ao staging:
     ```sh
     git add README.md
     ```
   - Faça o commit:
     ```sh
     git commit -m "Atualização README" -m "Atualização no README na minha nova branch"
     ```

3. **Mesclar a Branch:**
   - Mude de volta para a branch principal:
     ```sh
     git checkout main
     ```
   - Mescle as mudanças da nova branch:
     ```sh
     git merge minha-nova-branch
     ```

---

### Atividade: Uso de Pull Requests no GitHub

**Objetivo:** Contribuir para um repositório remoto utilizando pull requests.

**Passo a Passo:**

1. **Fork do Repositório:**
   - No GitHub, acesse um repositório público e clique em "Fork" para criar uma cópia no seu perfil.

2. **Clonar o Repositório Forkado:**
   - No terminal, clone seu fork:
     ```sh
     git clone https://github.com/seu-usuario/nome-do-repositorio.git
     ```

3. **Criar uma Branch para as Alterações:**
   - Navegue até o diretório do repositório clonado:
     ```sh
     cd nome-do-repositorio
     ```
   - Crie e mude para uma nova branch:
     ```sh
     git checkout -b minha-contribuicao
     ```

4. **Fazer Alterações e Commit:**
   - Faça as alterações necessárias no código.
   - Adicione as mudanças ao staging:
     ```sh
     git add .
     ```
   - Faça o commit:
     ```sh
     git commit -m "Minha contribuição"
     ```

5. **Enviar as Alterações para o GitHub:**
   - Empurre as mudanças para seu repositório forkado:
     ```sh
     git push origin minha-contribuicao
     ```

6. **Criar um Pull Request:**
   - No GitHub, navegue até o seu repositório forkado.
   - Clique no botão "Compare & pull request".
   - Adicione um título e descrição para o pull request.
   - Clique em "Create pull request".

---

### Atividade: Resolvendo Conflitos de Merge

**Objetivo:** Praticar a resolução de conflitos durante um merge.

**Passo a Passo:**

1. **Preparar o Ambiente:**
   - Crie um repositório local com dois branches: `main` e `feature`.
   - No branch `main`, adicione uma linha ao arquivo `README.md` e faça o commit.
   - No branch `feature`, adicione uma linha diferente ao mesmo arquivo e faça o commit.

2. **Tentar Mesclar os Branches:**
   - Mude para o branch `main`:
     ```sh
     git checkout main
     ```
   - Tente mesclar o branch `feature`:
     ```sh
     git merge feature
     ```
   - Um conflito de merge será gerado.

3. **Resolver o Conflito:**
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

Essas atividades fornecem uma experiência prática e abrangente para aprender a utilizar Git e GitHub, cobrindo desde os conceitos básicos até situações mais avançadas.
