
<div align="center">
  <h1>Oficina de Git e Github</h1>
</div>

<br>
<p align="justify"> &emsp; Link da apresentação da oficina: <a href="https://www.canva.com/design/DAF1sSIMpfM/dg-M_uJUzcXZweOrENdkXw/edit?utm_content=DAF1sSIMpfM&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton" target="_blank">apresentação no canva</a></p>
<br>

<p align = "justify"> &emsp; Este repositório é uma cópia do repositório de <a href="https://github.com/JohKemPo" target="_blank">@JohKemPo</a> modificado para realização da oficina por <a href="https://github.com/vyctor922" target="_blank">@vyctor922</a>. </p>


<h2 align="center">S U M Á R I O</h2>
<br>

1. [Introdução](#capitulo1)
   - O que é Git?
   - O que é Github?
   - O que é Versionamento de Código?
   - Vantagens do Versionamento de Código
   - Tipos de estado de um arquivo

2. [Capítulo 1: Git Básico](#capitulo2)
    1. [Instalação do Git](#instalacao)
        - Como instalar o Git no Windows
        - Como instalar o Git no macOS
        - Como instalar o Git no Linux
    1. [Configuração Inicial do Git](#inicial)
        - Configurando seu nome de usuário e email
        - Configurando seu editor de texto preferido
        - Configurações globais e locais do Git
    1. [Conceitos Fundamentais do Git](#funfamental)
        - Repositórios Git
        - Commits
        - Branches
        - Tags
        - Working directory, Staging area e Repository
    1. [Comandos Básicos do Git](#basico)
        - git init: Iniciando um repositório Git
        - git clone: Clonando um repositório
        - git add: Adicionando alterações ao Staging area
        - git commit: Criando um commit
        - git pull: Sincronizar seu Repositório Local com o Remoto
        - git push: Envia as alterações ao repositório remoto.
        - git status: Verificando o status do repositório
        - git log: Visualizando o histórico de commits
        - git diff: Comparando mudanças
        - git reset: Desfazer commits
        - Comandos para Modificar o Estado de um Arquivo
        - Resolvendo erros

3. [Capítulo 2: Trabalhando com Branches](#capitulo3)
    1. [Branches no Git](#branches)
        - O que é uma branch?
        - Criando e alterando branches
        - Excluindo branches
    1. [Merges e Conflitos](#merges)
        - Merging de branches
        - Resolvendo conflitos de merge
        - Rebase vs. Merge
    1. [Fluxo de Trabalho Básico](#fluxo)
        - Criando e trabalhando em uma nova branch
        - Fazendo commits em uma branch
        - Merging de uma branch

4. [Capítulo 3: GitHub](#capitulo4)
    1. [Trabalhando com Repositórios](#repositorios)
        - Criando um novo repositório
        - Configurações do repositório
        - Clonando um repositório
        - Issues e Pull Requests
        - .gitignore
    1. [Colaboração no GitHub](#colaboracao)
        - Colaboradores e permissões
        - Forking de repositórios
        - Trabalhando em colaboração
        - Revisão de código
    1. [Segurança](#seguranca)
        - introdução
        - Chave SSH
          - No windows
          - No linux
          - No macOS
    1. [Multiplos usuários git na mesma máquina](#multiplos)

5. [Apêndice ](#apendice)
    - Guia de Markdown
    - Material complementar
</div>


<br>

<h2 id="capitulo1">Introdução</h2>
<h2 id="">O que é o Git?</h2>
<p align = "justify"> &emsp; O Git é um sistema de controle de versão distribuído que permite rastrear as mudanças em um conjunto de arquivos ao longo do tempo. Ele é amplamente utilizado para o gerenciamento de código fonte em projetos de desenvolvimento de software, mas pode ser usado para qualquer tipo de arquivo.</p>

<h2 id="">O que é o GitHub?</h2>
<p align = "justify"> &emsp; O GitHub é uma plataforma web que usa o Git para hospedar repositórios de código fonte e colaboração em projetos. Ele oferece recursos como controle de acesso, rastreamento de problemas (issues), solicitações de pull (pull requests) e muito mais.</p>

<h2 id="">Vantagens do Versionamento de Código</h2>
<p align = "justify"> &emsp; O versionamento de código oferece uma série de benefícios que são fundamentais para o desenvolvimento de software colaborativo e gerenciamento de código-fonte. </p>

1. **Colaboração Eficiente:** Permite que várias pessoas trabalhem em um projeto simultaneamente, rastreando quem fez quais alterações.

2. **Histórico de Alterações:** Mantém um registro completo de todas as modificações feitas em um projeto ao longo do tempo.

3. **Experimentação Segura:** Os desenvolvedores podem criar branches para experimentar novos recursos ou correções sem afetar a versão principal do projeto.

4. **Rastreamento de Bugs:** Facilita a identificação e correção de problemas, permitindo que os desenvolvedores voltem a versões anteriores para isolar bugs.

5. **Recuperação de Versões Anteriores:** Possibilita a restauração de versões anteriores de um projeto, caso seja necessário reverter as alterações.


<h2 id="">Tipos de Estado de um Arquivo</h2>
<p align = "justify"> &emsp; Quando se trabalha com Git, os arquivos em um repositório podem estar em diferentes estados. Esses estados refletem o status do arquivo em relação ao controle de versão. Os quatro tipos principais de estados de um arquivo são:</p>

1. **Untracked:** Arquivos que o Git não está rastreando. Isso significa que o Git não tem conhecimento desses arquivos. Para rastreá-los, você precisa adicioná-los ao Git.

1. **Staged:** Arquivos que estão preparados para serem incluídos no próximo commit. Quando você realiza alterações em um arquivo e o "adiciona" ao Staging area, ele entra nesse estado.

1. **Unmodified:** Arquivos que não foram alterados desde o último commit. Quando um arquivo é confirmado, ele fica neste estado até sofrer novas alterações.

1. **Modified:** Arquivos que foram alterados desde o último commit. Quando você faz alterações em um arquivo rastreado, ele entra neste estado.

<p align = "justify"> &emsp;Entender e gerenciar esses estados é fundamental para o uso eficaz do Git, pois permite controlar quais alterações serão incluídas em um commit. O comando <b><i>git status</i></b> é usado para verificar o estado atual dos arquivos no repositório.</p>

<h2 id="capitulo2">Git básico</h2>
<h2 id="instalacao">Instalação Git</h2>

### No Windows:

1. Acesse o site oficial do Git para Windows em https://git-scm.com/download/win.
1. Baixe o instalador para Windows.
1. Execute o arquivo de instalação baixado.
1. Siga as instruções do instalador, aceitando as configurações padrão, a menos que você tenha necessidades específicas.
1. Após a instalação, você pode verificar se o Git foi instalado corretamente executando o seguinte comando no Terminal:
```
git --version
```

### No macOS:

1. Use o Homebrew, um gerenciador de pacotes, para instalar o Git. Abra o Terminal e execute o seguinte comando:

```powershell
brew install git
```
1. Baixe o instalador para Windows.
1. Execute o arquivo de instalação baixado.
1. Siga as instruções do instalador, aceitando as configurações padrão, a menos que você tenha necessidades específicas.
1. Após a instalação, você pode verificar se o Git foi instalado corretamente executando o seguinte comando no Terminal:
```
git --version
```

### No Linux (Debian/Ubuntu):

1. No terminal execute o comando a seguir para instalar o Git:
```
sudo apt-get install git
```
1. Após a instalação, você pode verificar se o Git foi instalado corretamente executando o seguinte comando no Terminal:
```
git --version
```

<h2 id="inicial">Configuração Inicial do Git</h2>

<p align = "justify"> &emsp; Quando você instala o Git pela primeira vez, é importante configurar algumas informações iniciais, como seu nome de usuário e endereço de email, para que seus commits sejam identificados corretamente. Aqui estão as principais configurações iniciais:</p>

- Configurando seu nome de usuário e email:

  - Use os comandos git config para definir seu nome de usuário e endereço de email globalmente, para que sejam usados em todos os repositórios Git.
  - Exemplo:
  ```
  git config --global user.name "Seu Nome"
  git config --global user.email "seu@email.com"
  ```

- Configurando seu editor de texto preferido (Opicional):

  - Você pode escolher o editor de texto que deseja usar ao escrever mensagens de commit. Isso é configurado globalmente.
  - Exemplo:
  ```
  git config --global core.editor "seu_editor_preferido"
  ```

- Configurações globais e locais do Git:
  - As configurações do Git podem ser definidas globalmente ou localmente para um repositório específico.
  - Configurações globais se aplicam a todos os repositórios em sua máquina.
  - Configurações locais se aplicam apenas a um repositório específico.
  - Para listar as cofigurações globais:
  ```
  git config --list
  ```

<h2 id="funfamental">Conceitos Fundamentais do Git</h2>
<p align = "justify"> &emsp; O Git é baseado em alguns conceitos fundamentais que são essenciais para entender como ele funciona:</p>

- **Repositórios Git:** Um repositório Git é um diretório que contém todos os arquivos do seu projeto, juntamente com um banco de dados especial para rastrear as alterações (histórico).

    ### **Repositório Local:**

    <p align = "justify"> &emsp;Um repositório local é um diretório em seu computador onde você armazena todos os arquivos e informações relacionadas a um projeto Git. Ele contém:</p>

    - **Working Directory (Diretório de Trabalho):** O diretório no seu computador onde você cria, edita e organiza seus arquivos de projeto.

    - **Área de Staging (ou Index):** Uma área intermediária onde você prepara as alterações que deseja confirmar (commit) no repositório. Isso permite que você selecione quais alterações serão incluídas no próximo commit.

    - **Histórico de Commits:** Uma série de snapshots (instantâneos) das versões do seu projeto. Cada commit contém informações sobre as alterações feitas, o autor e uma identificação única.

    - **Branches:** Divisões no histórico de commits que permitem que você trabalhe em diferentes linhas de desenvolvimento sem afetar o branch principal (geralmente chamado de "master" ou "main"). Você pode criar, mesclar e alternar entre branches no seu repositório local.

    ### **Repositório Remoto:**

    <p align = "justify"> &emsp;Um repositório remoto é um repositório Git armazenado em um servidor remoto (como GitHub, GitLab, Bitbucket ou um servidor próprio). Ele contém:</p>

    - **Histórico de Commits Remotos:** Uma cópia do histórico de commits do projeto, incluindo todas as alterações confirmadas por outros colaboradores.

    - **Controle de Acesso:** O repositório remoto geralmente possui configurações de controle de acesso, como permissões de leitura e gravação, que determinam quem pode visualizar e contribuir para o projeto.

    - **Colaboração:** O repositório remoto permite que várias pessoas colaborem em um projeto. Os desenvolvedores podem clonar (copiar) o repositório remoto para seus computadores locais, fazer alterações e, em seguida, enviar essas alterações de volta para o repositório remoto. Isso permite uma colaboração eficiente em projetos de equipe.

    - **Backup e Distribuição:** O repositório remoto serve como um local centralizado para armazenar e fazer backup de todo o histórico de commits do projeto. Também facilita a distribuição do código para outros desenvolvedores.

- **Commits:** Um commit é um snapshot do estado do seu projeto em um determinado momento. Cada commit tem uma mensagem descritiva que explica o que foi alterado.

- **Branches:** As branches são ramificações do desenvolvimento do seu projeto. Elas permitem que você trabalhe em funcionalidades ou correções separadamente, sem afetar o código principal.

- **Tags:** As tags são usadas para marcar pontos específicos no histórico do Git, como versões estáveis ou marcos importantes.

- **Working Directory, Staging Area e Repository:** O Working Directory é onde você faz as alterações nos arquivos. O Staging Area é onde você prepara as alterações para serem commitadas. O Repository é onde todas as alterações são armazenadas.

<h2 id="basico">Comandos Básicos do Git</h2>
<p align = "justify"> &emsp; O Git oferece uma variedade de comandos fundamentais que são essenciais para o gerenciamento de repositórios. Aqui estão os principais comandos e suas descrições:</p>

### git init: Iniciando um repositório Git
<p align = "justify"> &emsp;O comando <b><i>git init</i></b> é usado para iniciar um novo repositório Git em um diretório. Isso cria um ambiente de controle de versão para os arquivos naquele diretório.</p>

- Exemplo:
```
git init
```

### git clone: Clonando um repositório
<p align = "justify"> &emsp;O comando <b><i>git clone</i></b> permite criar uma cópia local de um repositório Git remoto. Isso é útil quando você deseja colaborar em um projeto existente ou trabalhar em diferentes máquinas.</p>

- Exemplo:
```
git clone URL_do_Repositório
```

### git add: Adicionando alterações ao Staging area
<p align = "justify"> &emsp;O comando <b><i>git add</i></b> é usado para adicionar alterações específicas de arquivos ao que é chamado de <b><i>Staging area</b></i>. Isso prepara as alterações para serem incluídas no próximo commit.</p>

- Exemplo:
- Para adicionar arquivos especificos em estado `Untracked` ou `Modified`:
```
git add nome_do_arquivo
```
- Para adicionar todos os arquivos em estado `Untracked` ou `Modified`:
```
git add .
```

### git commit: Criando um commit
<p align = "justify"> &emsp;O comando <b><i>git commit</i></b> é usado para criar um novo commit que inclui todas as alterações que estão no Staging area. Cada commit deve ter uma mensagem descritiva.</p>

- Exemplo:
```
git commit -m "Mensagem do commit" -m "Descrição do commit"
```

### git pull: Sincronizar seu Repositório Local com o Remoto
<p align = "justify"> &emsp;O comando <b><i>git pull</i></b> usado para sincronizar seu repositório local com o repositório remoto para garantir que você esteja trabalhando com as informações mais atualizadas. Use o comando <b><i>git</b></i> pull para puxar as mudanças do repositório remoto e mesclá-las com o seu repositório local.</p>

- Exemplo:
```
git pull origin main
```

### git push: Enviando alterações ao remoto
<p align = "justify"> &emsp;Depois de comitar suas alterações e sincronizar seu repositório local, você está pronto para enviar as alterações para o repositório remoto. Use o comando <b><i>git push</i></b> seguido do nome do repositório remoto (por padrão, "origin") e o nome da ramificação que deseja atualizar.</p>

- Exemplo:
```
git push origin main
```

**Explicando melhor:**

- **git push:** Este é o comando principal para enviar suas alterações (commits) locais para um repositório remoto. Ele sincroniza as alterações locais com o repositório remoto.

- **-u (ou --set-upstream):** A opção -u é usada para definir o controle remoto padrão para o branch local. Isso é útil para que você possa usar `git pull` e `git push` posteriormente sem especificar o controle remoto e o branch toda vez. O `origin` e o `main` no comando indicam o nome do controle remoto e o nome do branch para o qual você está enviando suas alterações.

- **origin:** É o nome do controle remoto. O controle remoto é uma referência ao repositório remoto, que é geralmente hospedado em uma plataforma como GitHub, GitLab, Bitbucket, etc. O nome `origin` é um nome comum para o controle remoto principal, mas você pode dar a ele o nome que preferir.

- **main:** É o nome do branch que você está enviando para o repositório remoto.

### git status: Verificando o status do repositório
<p align = "justify"> &emsp;O comando <b><i>git status</i></b> permite verificar o estado atual do repositório, mostrando quais arquivos foram modificados, adicionados ao Staging area ou estão não rastreados.</p>

- Exemplo:
```
git status
```

### git log: Visualizando o histórico de commits
<p align = "justify"> &emsp;O comando <b><i>git log</i></b> é usado para visualizar o histórico de commits do repositório. Isso inclui informações como o autor, data e mensagem de cada commit.</p>

- Exemplo:
```
git log
```

### git diff: Comparando mudanças
<p align = "justify"> &emsp;O comando <b><i>git diff</i></b> é utilizado para visualizar as diferenças entre o estado atual dos arquivos e o último commit. Isso é útil para entender as alterações feitas.</p>

- Exemplo:
```
git diff
```

### git reset: Desfazer commits
<p align = "justify"> &emsp;O comando <b><i>git reset</i></b>  é utilizado para desfazer commits. Ele permite mover os commits para um estado anterior e pode ser útil para corrigir erros ou reorganizar o histórico.</p>

- Exemplo:
```
git reset HEAD~1
```

<p align = "justify"> &emsp;HEAD~1: Esta parte do comando especifica o ponto para o qual você deseja reverter. O HEAD representa o commit mais recente na branch atual, e o ~1 indica que você deseja voltar um único commit. Se você desejar voltar mais de um commit, poderá ajustar o número após o til (~).</p>

<p align = "justify"> &emsp;Portanto, quando você executa git reset HEAD~1, o Git moverá a branch atual para o commit anterior, desfazendo o último commit. As alterações feitas no commit desfeito não são perdidas; elas voltam ao estado "unstaged" no diretório de trabalho, permitindo que você modifique e reconfigure as alterações antes de fazer um novo commit.</p>

### Comandos para Modificar o Estado de um Arquivo
<p align = "justify"> &emsp;Além dos comandos mencionados acima, também é possível usar git checkout para desfazer alterações não salvas em um arquivo específico e git reset para mover arquivos do estado "staged" para "unmodified" ou "modified".</p>

<h2 id="capitulo3">Trabalhando com Branches</h2>
<h2 id="branches">Branches no Git</h2>

### Resolvendo erros
<p align = "justify"> &emsp;O Git é uma ferramenta poderosa, mas também é fácil cometer erros. Felizmente, existem maneiras de consertar erros inseridos na `main`. Aqui algumas alternativas como corrigi-los.</p>

<p align = "justify"> &emsp;O comando `git log` mostra o histórico de commits, com o hash do commit, o autor, a data e a mensagem de cada commit. O hash do commit é um identificador exclusivo para cada commit. Você pode usar o hash do commit para reverter para o último commit sem o erro.</p>

```
git log
```

<p align = "justify"> &emsp;O comando `git branch` cria uma nova branch a partir de um commit específico. Você pode usar o hash do commit para criar uma nova branch a partir do último commit sem o erro.</p>

```
git branch hotfix-<ERROR_NAME> <COMMIT_ID>
```

<p align = "justify"> &emsp;O comando `git reset` move a branch atual para um commit específico. Você pode usar o hash do commit para mover a branch atual para o último commit sem o erro. O `--force` é usado para forçar o reset, mesmo que você tenha commits não salvos.</p>

```
git reset <COMMIT_ID>

ou

git reset --force <COMMIT_ID>
```

### <p align="justify">&emsp; Acima tem duas formas, uma mais recomendada e outra menos recomendada porém mais imediata para emergências. Contudo a melhor forma de resolver problemas na main é não os deixando chegar lá.</p>

### O que é uma branch?
<p align = "justify"> &emsp;Uma branch é uma ramificação independente no Git que permite desenvolver funcionalidades ou correções de forma isolada do ramo principal (geralmente chamado de "master" ou "main"). Entretanto, é possível criar branches com quaisquer nomes, comumente com os nomes das funcionalidades especificas em desenvolvimento.</p>

### Criando e alterando branches

- **Criar uma branch:** Use o comando `git branch nome_da_branch` para criar uma nova branch.
```
git branch nome_da_branch
```
- **Alternar para uma branch:** Use o comando `git checkout nome_da_branch` para mudar para a branch desejada.
```
git checkout nome_da_branch
```
- **Excluir uma branch:** Use o comando `git branch -d nome_da_branch` para remover uma branch que não é mais necessária.
```
git branch -d nome_da_branch
```

### Criando a partir de outra

- **Certifique-se de estar na branch de origem:**

```
git checkout nome-da-branch-de-origem
```
- **Crie uma nova branch a partir da branch de origem:**

```
git checkout -b nome-da-nova-branch
```
Isso cria uma nova branch e a seleciona automaticamente.

- **Faça as alterações necessárias e adicione-as ao controle de versão:**

```
git add .
git commit -m "Mensagem do commit"
```

- **Publique a nova branch no repositório remoto:**

```
git push origin nome-da-nova-branch
```

<h2 id="merges">Merges e Conflitos</h2>

**Merging de branches**

<p align="justify">&emsp; O comando `git merge nome_da_branch` é usado para mesclar o conteúdo de uma branch em outra. Isso integra as alterações feitas em uma branch à branch de destino.</p>

### **Resolvendo conflitos de merge**

<p align="justify">&emsp; Quando o Git não pode mesclar automaticamente as alterações de duas branches devido a conflitos, você precisará resolver manualmente os conflitos. Isso envolve editar os arquivos com conflitos, adicioná-los ao estágio (usando `git add`) e, em seguida, criar um novo commit.</p>

### **Rebase vs. Merge**

<p align="justify">&emsp; O `rebase` é uma alternativa ao merge. Ele reorganiza o histórico de commits, "movendo" suas alterações para o topo da branch de destino, resultando em um histórico linear. O `merge` cria um novo commit de mesclagem, mantendo o histórico original.</p>

<h2 id="fluxo">Fluxo de Trabalho Básico</h2>

### Criando e trabalhando em uma nova branch

<p align="justify">&emsp; Use `git checkout -b nova_branch` para criar e alternar para uma nova branch em um único comando. Isso é útil ao iniciar uma nova funcionalidade ou correção.</p>

### Fazendo commits em uma branch

<p align="justify">&emsp; Depois de alternar para uma branch, você pode fazer commits normais usando `git commit `para salvar as alterações. Os commits são específicos para a branch em que você está trabalhando.</p>

### Merging de uma branch
<p align="justify">&emsp; Quando sua funcionalidade ou correção estiver pronta, você pode mesclá-la de volta à branch principal (por exemplo, `master` ou `main`) usando `git merge`. Isso incorpora suas alterações ao ramo principal do projeto.</p>

<p align="justify">&emsp; Trabalhar com branches no Git permite um desenvolvimento organizado e colaborativo, onde várias funcionalidades ou correções podem ser desenvolvidas simultaneamente sem conflitos constantes.</p>

<h2 id="capitulo4">Github</h2>
<h2 id="repositorios">Trabalhando com Repositórios</h2>

<p align="justify">&emsp; Repositórios no GitHub são a base de todo o desenvolvimento colaborativo. É onde você armazena, compartilha e colabora em projetos. </p>

### Criando um Novo Repositório

Passos para criar um novo repositório no GitHub:
1. Acesse o GitHub e faça login na sua conta.

1. No canto superior direito, clique no botão "+" e escolha "Novo repositório".

1. Preencha as informações do repositório:
    - **Nome do Repositório:** Escolha um nome significativo para o seu projeto.
    - **Descrição:** Descreva o propósito do repositório.
    - **Visibilidade:** Pode ser público ou privado, dependendo das suas necessidades.
    - **Inicializar com um README:** É uma boa prática marcar essa opção para criar um arquivo README inicial.
1. Clique no botão "Criar repositório."
1. Vinculando repositório:
    1. Iniciando um novo repositório na linha de comando:
        ```bash
            git init
            git add README.md
            git commit -m "first commit"
            git branch -M main # Ou a branch padrao pré configurada, normalmente "master"
            git remote add origin `HTTPS DO REPOSITÓIO`
            git push -u origin main
        ```
    1. Enviando a um repositório existente a partir da linha de comando:
        ```bash
            git remote add origin `HTTPS DO REPOSITÓIO`
            git branch -M main # Ou a branch padrao pré configurada, normalmente "master"
            git push -u origin main
        ```

### Configurações do Repositório

Personalizando as configurações do repositório:

Após criar o repositório, você pode personalizar suas configurações da seguinte forma:

- **Configurações:** Nesta seção, você pode definir configurações importantes, como opções de colaboração, acesso e configurações de segurança. Por exemplo, você pode adicionar colaboradores, definir permissões de acesso, habilitar a proteção de ramos e muito mais.

- **Integrações:** Configure integrações com outras ferramentas e serviços para automatizar fluxos de trabalho e aumentar a produtividade. O GitHub oferece uma ampla variedade de integrações, como integração contínua, rastreamento de problemas e implantação automática.

- **Notificações:** Personalize as notificações que você deseja receber sobre atividades no repositório.

- **Colaboradores:** Adicione pessoas ou equipes como colaboradores, permitindo que eles contribuam para o repositório.

- **Segurança:** Configure medidas de segurança, como verificação de Dependabot para atualizações de pacotes.

- **Opções do GitHub Pages:** Se desejar hospedar uma página da web a partir do seu repositório, você pode configurá-la aqui.

- **Transferir repositório:** Se necessário, você pode transferir a propriedade do repositório para outra conta.

### Clonando um Repositório

Para clonar um repositório do GitHub para sua máquina local:

- Abra o terminal (no caso do Linux ou macOS) ou use o Git Bash (no caso do Windows).

- Navegue até o diretório onde você deseja clonar o repositório.

- No GitHub, vá até o repositório que deseja clonar e clique no botão "Código."

- Copie a URL do repositório (por exemplo, "https://github.com/seunome/seurepo.git").

No terminal, digite o seguinte comando:
```
git clone URL_do_Repositório
```

Agora você possui uma cópia local do repositório e pode começar a trabalhar em seus arquivos.

### Issues e Pull Requests

### **Issues:**

<p align="justify">&emsp;As issues são usadas para rastrear problemas, sugestões, tarefas e melhorias em um repositório. Elas são úteis para manter o controle das discussões e do progresso do desenvolvimento. Para criar uma issue, siga estes passos:</p>

- No repositório, vá até a guia "Issues."

- Clique no botão "Nova issue."

- Preencha os detalhes, incluindo um título descritivo e um corpo explicando o problema ou sugestão.

- Clique em "Criar issue."

### **Pull Requests:**

<p align="justify">&emsp;Os pull requests são usados para propor alterações em um repositório. Eles são fundamentais para a colaboração e revisão de código. Para criar um pull request, siga estes passos:</p>

- Faça as alterações desejadas em uma branch no seu repositório.

- No GitHub, vá até o repositório e clique na guia "Pull Requests."

- Clique no botão "Novo pull request."

- Escolha a base (a branch de destino) e a branch com suas alterações.

- Preencha os detalhes do pull request, incluindo um título e uma descrição.

- Clique em "Criar pull request."

<p align="justify">&emsp;Agora outros colaboradores podem revisar suas alterações, fazer comentários e, quando estiverem prontos, mesclar as alterações no repositório principal.</p>

<p align="justify">&emsp;Trabalhar com repositórios no GitHub é fundamental para o desenvolvimento colaborativo. Você pode criar, configurar e colaborar em projetos de software de forma eficaz, controlando seu código e facilitando a comunicação entre membros da equipe.</p>


### .gitignore: Ignorando Arquivos Indesejados

<p align="justify">&emsp;O arquivo `.gitignore` é uma parte fundamental de qualquer repositório Git. Ele permite que você especifique quais arquivos e diretórios devem ser ignorados pelo Git. A importância do `.gitignore` reside no fato de que ele ajuda a manter o repositório limpo e a evitar o rastreamento acidental de arquivos que não devem fazer parte do controle de versão.</p>

Os tipos de arquivos que você geralmente deseja ignorar no `.gitignore` incluem:

- Arquivos de compilação.
- Arquivos temporários.
- Arquivos de sistema.
- Dependências de terceiros (por exemplo, bibliotecas).

Ao criar um arquivo `.gitignore`, você pode especificar padrões de correspondência para os arquivos a serem ignorados. Por exemplo:

```
# Ignorar arquivos de compilação
*.o
*.out

# Ignorar arquivos de configuração
config.ini

# Ignorar diretórios gerados
build/
```
<p align="justify">&emsp;O uso adequado do `.gitignore` ajuda a manter o repositório organizado e evita que arquivos desnecessários sejam incluídos nos commits.</p>

<p align="justify">&emsp;Existem sites que constroem o `.gitignore` automaticamente para seu projeto, como por exemplo, o <a href="https://www.toptal.com/developers/gitignore">toptal</a>.</p>

<h2 id="colaboracao">Colaboração no GitHub</h2>

### **Colaboradores e Permissões**

<p align="justify">&emsp;O GitHub permite adicionar colaboradores a um repositório e definir permissões específicas para eles. Isso ajuda a controlar quem pode contribuir e de que forma.</p>

Adicionando Colaboradores

- Acesse o repositório no GitHub.
- Clique em "Settings" no menu do repositório.
- Na guia "Manage access," você pode adicionar colaboradores pelo nome de usuário ou endereço de e-mail.

### **Permissões**

As permissões padrão no GitHub incluem:

- Read: Pode visualizar o repositório.
- Write: Pode fazer commits e enviar alterações.
- Admin: Tem controle total, incluindo permissões de acesso e exclusão.

### **Forking de Repositórios**

<p align="justify">&emsp;Forking é uma funcionalidade essencial no GitHub que permite criar uma cópia independente de um repositório. Isso é útil quando você deseja contribuir para projetos de terceiros.</p>

Como fazer Fork de um Repositório

- Acesse o repositório que deseja forkar.
- Clique no botão "Fork" no canto superior direito.
- Isso criará uma cópia do repositório em sua conta.

<p align="justify">&emsp;Uma vez que você tenha um fork do repositório, você pode trabalhar nas suas alterações. Aqui estão os passos gerais para trabalhar em colaboração:</p>

1. Clone o fork para o seu ambiente de desenvolvimento local.
    ```
    git clone URL_do_Seufork
    ```
1. Crie uma branch para a funcionalidade que deseja desenvolver.
    ```
    git checkout -b minha_branch
    ```
1. Faça suas alterações no código.
1. Adicione e faça commit das suas alterações.
    ```
    git add .
    git commit -m "Minha mensagem de commit"
    ```
1. Faça push das alterações para o seu fork.
    ```
    git push origin minha_branch
    ```
1. No GitHub, crie um Pull Request para o repositório original.


### **Trabalhando em Colaboração**

Usar o Git e o GitHub em um ambiente de equipe requer algumas práticas recomendadas para garantir uma colaboração eficiente e evitar conflitos desnecessários. Abaixo temos algumas boas práticas para utilizar o Git e GitHub em um ambiente de grupo:

1. **Crie um fluxo de trabalho consistente:**
   - Estabeleça um fluxo de trabalho Git claro, como o Gitflow, para padronizar como as ramificações são criadas, integradas e implantadas.

1. **Use Branches:**
   - Crie branches para recursos, correções de bugs e experimentos. Mantenha a branch `main` (ou `master`) para código de produção estável.

1. **Mantenha a `main` Limpa:**
   - Evite commits diretos na branch `main`. Use branches de feature ou hotfix e faça pull requests para incorporar alterações na `main`.

1. **Faça Pull Regularmente:**
   - Mantenha seu repositório local atualizado fazendo pull regularmente da branch `main`.

1. **Use Pull Requests (PRs):**
   - Antes de mesclar código, crie pull requests para revisão. Isso facilita a revisão de código e a detecção de problemas antes da integração.

1. **Revisão de Código:**
   - Encoraje a revisão de código entre membros da equipe para garantir a qualidade e a consistência do código.

1. **Comentários Significativos:**
   - Faça comentários significativos nas Pull Requests e nos commits para facilitar a compreensão do que está sendo alterado.

1. **Integração Contínua:**
   - Configure integração contínua para automatizar testes e construções sempre que houver novos commits.

1. **Resolva Conflitos Rapidamente:**
   - Se ocorrerem conflitos durante a mesclagem, resolva-os imediatamente para evitar problemas posteriores.

1. **Use Tags para Versões:**
    - Marque versões estáveis com tags. Isso facilita o rastreamento de versões específicas do código.

1. **Ignore Arquivos Gerados:**
    - No arquivo `.gitignore`, liste arquivos gerados automaticamente (por compiladores, IDEs, etc.) para evitar que eles sejam incluídos acidentalmente no repositório.

1. **Documentação:**
    - Mantenha documentação atualizada, incluindo instruções sobre como configurar e executar o projeto.

1. **Use Issues para Rastreamento:**
    - Use issues para rastrear tarefas, bugs e melhorias. Isso facilita o acompanhamento do progresso.

1. **Seja Descritivo nos Commits:**
    - Escreva mensagens de commit descritivas que expliquem claramente o propósito da alteração.

1. **Mantenha o Repositório Organizado:**
    - Mantenha um repositório organizado com uma estrutura lógica de pastas e arquivos.

### **Revisão de Código**

<p align="justify">&emsp;Um dos aspectos mais importantes da colaboração no GitHub é a revisão de código. Quando você cria um Pull Request, outros colaboradores podem analisar suas alterações e fazer comentários.</p>

- Os revisores podem fazer sugestões ou aprovar as alterações.
- O autor do Pull Request pode fazer alterações com base nos comentários.

<p align="justify">&emsp;Essa abordagem ajuda a manter a qualidade do código e a promover a colaboração eficaz entre membros da equipe ou da comunidade.</p>


<h2 id="seguranca">Segurança</h2>


<p align="justify">&emsp;A segurança é uma consideração fundamental ao usar o GitHub. Proteger seu acesso e suas credenciais é essencial para manter seus repositórios e dados seguros. Nesta seção, abordaremos tópicos relacionados à segurança no GitHub.</p>

### **Introdução**

<p align="justify">&emsp;A segurança no GitHub abrange várias áreas, desde o acesso à autenticação até o gerenciamento de permissões. É importante garantir que seu ambiente GitHub seja seguro para evitar vulnerabilidades e garantir a integridade de seus projetos.</p>

### **Chave SSH**

<p align="justify">&emsp;As chaves SSH são uma maneira segura de autenticar-se no GitHub. Elas são usadas para estabelecer uma conexão segura entre seu computador e o GitHub. Abaixo estão instruções para configurar chaves SSH no Windows, Linux e macOS.</p>

**[No Windows](https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account?platform=windows)**

1. Gerando uma Chave SSH:

    - Abra Git Bash.
    - Cole o texto abaixo, substituindo o endereço de e-mail pelo seu GitHub.
        ```
        ssh-keygen -t ed25519 -C "your_email@example.com"
        ```
    - No prompt, digite uma senha segura.
    - Copie a chave pública SSH para a sua área de transferência.
        ```
        cat "caminho da chame publica"
        # ~/.ssh/id_ed11111.pub EXEMPLO
        ```
    - Na página "Settings" do github, clique em "SSH and GPG keys" (Chaves SSH e GPG) no menu lateral esquerdo.
    - Clique em "New SSH key" (Nova chave SSH).
    - No campo "Title" (Título), dê um nome descritivo para sua chave.
    - No campo "Key" (Chave), cole a chave pública que você copiou anteriormente.
    - Clique em "Add SSH key" (Adicionar chave SSH) para salvar a chave.

**[No Linux](https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account?platform=linux)**

1. Gerando uma Chave SSH:

    - Abra um terminal no Linux.
    - Cole o texto abaixo, substituindo o endereço de e-mail pelo seu GitHub.

        ```
        ssh-keygen -t ed25519 -C "your_email@example.com"
        ```
    - Siga as instruções para configurar uma senha para a chave, se desejar.

1. Copiando a Chave Pública para o GitHub:

    - Use `cat ~/.ssh/sua_chave_publica.pub` para exibir a chave pública.
    - Copie a chave e adicione-a às configurações do SSH no GitHub.
    Acesse sua conta no GitHub (github.com) e navegue até "Settings" (Configurações) no menu de perfil.
    - Copie a saída do comando, que é a chave pública.
    - Na página "Settings" do github, clique em "SSH and GPG keys" (Chaves SSH e GPG) no menu lateral esquerdo.
    - Clique em "New SSH key" (Nova chave SSH).
    - No campo "Title" (Título), dê um nome descritivo para sua chave.
    - No campo "Key" (Chave), cole a chave pública que você copiou anteriormente.
    - Clique em "Add SSH key" (Adicionar chave SSH) para salvar a chave.

**[No macOS](https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account?platform=mac)**

<p align="justify">&emsp;O processo para gerar e adicionar chaves SSH no macOS é semelhante ao do Linux. Você pode seguir as instruções acima para o Linux no macOS.</p>


<h2 id="multiplos">Multiplos usuários git na mesma máquina</h2>

1. Crie Chaves SSH para cada conta
1. Publique as chaves nos respectivos Gihub
1. Crie um arquivo de configuração e determine as informações host

### **Criando chaves ssh - relembrando**

- **Crie as chaves ssh para cada usuário:**

Não se esqueça de diferenciar os nomes das chaves geradas

```
ssh-keygen -t rsa -C "email" -f "nome-chave-usuario-1"
ssh-keygen -t rsa -C "email" -f "nome-chave-usuario-2"
...
```

- No prompt, digite uma senha segura.
    - Copie a chave pública SSH para a sua área de transferência.
        ```
        cat "caminho da chame publica"
        # ~/.ssh/id_ed11111.pub EXEMPLO
        ```
    - Na página "Settings" do github, clique em "SSH and GPG keys" (Chaves SSH e GPG) no menu lateral esquerdo.
    - Clique em "New SSH key" (Nova chave SSH).
    - No campo "Title" (Título), dê um nome descritivo para sua chave.
    - No campo "Key" (Chave), cole a chave pública que você copiou anteriormente.
    - Clique em "Add SSH key" (Adicionar chave SSH) para salvar a chave.

- **Certifique-se de as chaves publicas e privadas estarem na pasta `.ssh`**

Caso ela não exita crie e salve as chaves nela.

- **No diretório `.ssh` crie o arquivo `config`**

```
touch config
```

- **Edite o arquivo `config`:**

```
open config
```

- **Configure os respectivos dados HOST:**

```
#Informações da conta 1
Host github.com-conta1
    HostName github.com
    User git
    IdentityFile ~/.ssh/github-conta1

#Informações da conta 2
Host github.com-conta2
    HostName github.com
    User git
    IdentityFile ~/.ssh/github-conta2
```

- **Clonando repositorio:**

Agora esta tudo configurado! Basta clonar o respositório desejado:

```
git clone git@github.com-{seu-username}:{user-name-do-repositorio}/{nome-do-repositorio}.git

# EXEMPLO
git clone git@github.com-conta1:usuario-1/TestRepo.git
```


<h2 id="apendice">Apêndice </h2>

### **Guia prático de marckdown**

[Link para o repositório completo](https://github.com/JohKemPo/Github-Guide/blob/main/Markdown%20.md)

<p align="justify">&emsp;O Markdown foi criado por John Gruber e Aaron Swartz em 2004, com o objetivo de permitir a escrita de texto com formatação fácil de ler e escrever, que pode ser convertido em HTML e outros formatos.</p>

### **Material complementar**

<p align="justify">&emsp;Material de consulta em geral sobre personalização de readme e dicas</p>

- [github-readme-stats](https://github.com/anuraghazra/github-readme-stats)
- [skill-icons](https://github.com/tandpfun/skill-icons)
- [pretty-readme-badges](https://github.com/VishwaGauravIn/pretty-readme-badges)
- [Badges4-README.md-Profile](https://github.com/alexandresanlim/Badges4-README.md-Profile)
- [github-readme-stats](https://github.com/anuraghazra/github-readme-stats)
- [github-profile-summary-cards](https://github.com/vn7n24fzkq/github-profile-summary-cards)
- [github-profile-trophy](https://github.com/ryo-ma/github-profile-trophy)
- [github-readme-streak-stats](https://github.com/DenverCoder1/github-readme-streak-stats)
- [readme-activity-graph](https://github.com/Ashutosh00710/github-readme-activity-graph)
- [Markdown Tutorial](https://github.com/luong-komorebi/Markdown-Tutorial/blob/master/README_pt-BR.md)
- [Criar e realçar blocos de código](https://docs.github.com/pt/get-started/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks)
- [padrões-de-commits](https://github.com/iuricode/padroes-de-commits)
- [Conventional Commits Pattern](https://medium.com/linkapi-solutions/conventional-commits-pattern-3778d1a1e657)
- [Git Branch](https://blog.betrybe.com/git/git-branch/)
- [Conventional Commits Specification](https://www.conventionalcommits.org/en/v1.0.0/#summary)
- [Github status readme](https://github.com/anuraghazra/github-readme-stats)
- [Markdown tutorial](https://github.com/luong-komorebi/Markdown-Tutorial)
- [Badges readme](https://github.com/alexandresanlim/Badges4-README.md-Profile)
