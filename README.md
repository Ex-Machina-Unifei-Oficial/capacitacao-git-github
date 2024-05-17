# Capacitação Git e Github

## O que é o Git?

Git é um sistema de controle de versões. O Git é utilizado, principalmente, para o trabalho em equipe. Através do Git, é possível notificar modificações feitas em um projeto para a equipe toda, comparar essas modificações e selecionar versões de um projeto conforme o mesmo é atualizado. Todas as versões e alterações ficam armazenadas. Versões idênticas não são salvas mais de uma vez, o que garante uma organização melhor do projeto. Sendo assim, que é armazenado no Git são os estados de um arquivo.
O criador do Git é Linus Torvalds, o mesmo criador do Linux.  

## Instalação

[Guia de Instalação Git](https://overjoyed-cabinet-d4d.notion.site/Guia-de-Instala-o-Git-4c60c9a975cc490ea2ae715c9f2bc38f)

## O que é o Github?

O GitHub é uma plataforma de hospedagem de código-fonte e colaboração baseada na web. Ele permite que os desenvolvedores armazenem e gerenciem seus projetos de software usando o sistema de controle de versão Git. O GitHub fornece uma interface intuitiva e recursos poderosos para facilitar o trabalho colaborativo em equipes de desenvolvimento.

Ao usar o GitHub, os desenvolvedores podem criar repositórios para seus projetos, que são como pastas para armazenar e organizar o código-fonte. Esses repositórios podem ser públicos, permitindo que qualquer pessoa veja e contribua com o código, ou privados, acessíveis apenas para colaboradores autorizados.

Uma das principais vantagens do GitHub é a capacidade de rastrear as alterações feitas no código ao longo do tempo. Os desenvolvedores podem criar "commits" para registrar as modificações feitas em seus arquivos e ramos (branches) para trabalhar em diferentes versões do código simultaneamente. Além disso, o GitHub oferece recursos de "pull request", onde os desenvolvedores podem revisar e discutir as alterações antes de mesclá-las ao código principal.

O GitHub também possui recursos de gerenciamento de problemas (issues) que permitem aos desenvolvedores acompanhar e resolver bugs, solicitações de recursos e outras tarefas relacionadas ao projeto. Além disso, a plataforma oferece recursos para integração contínua (CI) e implantação contínua (CD), permitindo a automação de testes e implementações em diferentes ambientes.

O GitHub se tornou uma plataforma amplamente utilizada na comunidade de desenvolvimento de software, com milhões de desenvolvedores e organizações hospedando seus projetos na plataforma. Além disso, o GitHub fornece suporte para colaboração em equipe, facilitando a contribuição de vários desenvolvedores em um mesmo projeto.

## Configurando Acessos

### Token

[Criando um token de acesso pessoal](https://docs.github.com/pt/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)

### SSH

[Conectar-se ao GitHub com o SSH](https://docs.github.com/pt/authentication/connecting-to-github-with-ssh)

## Primeiro Respositório

### Via Github App

No GitHub desktop, no canto superior esquerdo:

1. Clique em "File";

2. Depois, "New repository".

### Via Github Web

Para criar um repositório no Github:

1. Entre em sua conta na plataforma;

<p align="left">
    <img src="images/sign-in-github.png" tittle="Sign In no Github" height="250">
</p>

2. No canto superior direito, busque o ícone de "+" e selecione "Novo repositório";

<p align="left">
    <img src="images/repo-create.png" tittle="New Repositório" height="250">
</p>

3. Digite um nome de repositório e se desejar pode adicionar uma breve descrição no campo "Descrição";

<p align="left">
    <img src="images/create-repository-name.png" tittle="New Repositório" height="100">
</p>

4. Escolha se deseja que seu repositório seja público ou privado, se quer inicializar o projeto com um README.MD e clique em "Criar Repositório".

### Via Terminal

Para criar um novo repositório via linha de comado:

1. Acesse o local onde deseja cria seu repositório, usando o comando `cd CaminhoAteAPasta`;

2. Crie uma nova pasta `mkkdir MeuNovoProjeto`ou para windows `dir MeuNovoProjeto`;

3. Em seguida acesse a pasta `cd MeuNovoProjeto`;

4. Use o comando `git init` para inicializar o repositório;

5. Crie sua `branch` usando `git branch -m main`.

6. Verifique se sua branch está apontando para um endereço remoto `git remote -v`.

7. Crie sua branch no github e copie seu endereço.

8. Lembra daquele endereço de branch, vamos usá-lo agora para idicar para sua máquina com qual endereço esse projeto deve ser sincronizado usando o comando `git remote add origin ssh://git@endereçoDaBranch.com:1234/meuRepositorio.git`.

9. Confira novamente se sua branch aponta para um endereço remoto `git remote -v`, agora devem aparecer os endereços de fetch e push assim: 
```
$git remote -v

meuRepositorio ssh://git@endereçoDaBranch.com:1234/meuRepositorio.git (fetch)

meuRepositorio ssh://git@endereçoDaBranch.com:1234/meuRepositorio.git (push)
```

10. Com tudo isso definido, pode fazer suas alterações e manda-las para o github sem medo.


## Comandos Básicos

O Git conta com uma série de comandos, alguns mais gerais e outros mais específicos. Segue abaixo uma lista com alguns dos comandos básicos que são utilizados em toda criação e manipulação de projetos Git.

Todo comando Git deve começar com a chave "git" sucedida pelo comando:

```
 git <comando> [<parâmetros_do_comando>]
```

1. `git init`
Este comando inicializa um repositório Git.
Para utilizar este comando, é necessário estar na pasta em que se deseja inicializar um repositório Git.
(Mude de diretório através do comando cd NomeDaPasta até acessar a pasta que deseja)

2. `git status`
Mostra o estado do repositório, quais arquivos constam nele e se sofreram alteração.

3. `git add`
Faz com que o arquivo passe a ser monitorado, "entrega" ele para o servidor.
Exemplo: git add .

4. `git remote add origin <URL_ou_SSH_do_projeto>`
   ou
   `git remote add nome <caminho/endereço>`
Adiciona um repositório remoto. O endereço pode ser o "caminho" nas pastas do computador ou a URL ou SSH do projeto.

4.1 `git remote rename <oldName> <newName>`
Renomeia um repositório já existente.

5. `git remote -v`
Mostra o endereço do repositório.

6. `git clone <endereço> nomeDesejado`
Este comando clona um repositório.
"Clonar" um repositório é trazer dados de um repositório remoto (na nuvem) para um repositório local.

7. `git commit -m "Mensagem"`
Utilizado para marcar que houve uma modificação e "subir" essa modificação para o repositório.
Vem acompanhado de uma mensagem que, geralmente, indica qual modificação foi realizada. É uma boa prática de programação deixar uma mensagem clara e precisa da modificação realizada.
(Ver a seção de "Conventional Commits").

8. `git push`
"Empurrar".
Envia dados para o servidor, ou seja, publica commits ou branches locais

9. `git pull`
Pega os dados de um repositório.

10. `git branch NomeDaBranch`
Cria uma branch com o nome NomeDaBranch.
("Branch", em inglês, significa "ramo".)

11. `git branch -d NomeDaBranch`
Deleta a branch NomeDaBranch.

12. `git branch`
Lista as branches do ambiente de trabalho.

13. `git checkout NomeDaBranch`
Muda para a branch existente NomeDaBranch.

14. `git checkout -b NomeDaBranch`
Cria a branch NomeDaBranch e já muda para ela.

15. `git fetch`
Carrega no repositório local todos os remotes do repositório na núvem, ou seja, atualiza o repositório local de acordo com a versão mais recente do respositório na núvem.

16. `git merge`
`git merge <nome_da_branch>`
É utilizado para fundir duas branches, a branch selecionada <nome_da_branch> com a branch atual.

### Flags/bandeiras mais comuns no Git

1. `git init`:

    - `--bare`: Cria um repositório bare, que é um repositório sem uma working directory. É usado principalmente para repositórios remotos.

2. `git clone`:

    - `--depth <depth>`: Realiza um clone superficial com um histórico de commits limitado ao número especificado. Isso pode ser útil para economizar tempo e espaço.
    - `--branch <branch>`: Clona um branch específico ao invés do branch padrão (geralmente main ou master).

3. `git add`:

    - `-A` ou `--all`: Adiciona todos os arquivos novos, modificados e deletados para a área de staging.
    -`-p` ou `--patch`: Permite que você adicione partes específicas de um arquivo para a área de staging, interativamente.

4. `git commit`:

    - `-m <message>`: Especifica a mensagem de commit diretamente na linha de comando, sem abrir um editor de texto.
    - `--amend`: Modifica o commit mais recente. Pode ser usado para alterar a mensagem do commit ou adicionar mudanças adicionais.

5. `git status`:

    - `-s` ou `--short`: Exibe um status mais compacto.
    - `-b` ou `--branch`: Exibe informações adicionais sobre o branch atual.

6. `git log`:

    - `--oneline`: Mostra cada commit em uma única linha, com um resumo curto.
    - `--graph`: Exibe um gráfico ASCII de branches e merges.
    - `--decorate`: Adiciona nomes de branches e tags aos commits.

7. `git checkout`: 

    - `-b <branch>`: Cria e muda para um novo branch.
    - `-- <file>`: Recupera o arquivo especificado do commit mais recente ou da área de staging, descartando as mudanças locais.

8. `git merge`:
    
    - `--no-ff`: Realiza um merge sem fast-forward, sempre criando um novo commit de merge.
    - `--squash`: Combina todos os commits da branch de feature em um único commit na branch de destino, sem fazer um commit de merge.

9. `git pull`:

    - `--rebase`: Realiza um rebase ao invés de um merge, aplicando as mudanças locais sobre as mudanças remotas.

10. `git push`:

    - `--force` ou `-f`: Força o push, sobrescrevendo a história remota. Use com cautela.
    - `--set-upstream` ou `-u`: Define a branch remota como upstream para a branch atual.

11. `git rebase`:

    - `-i` ou `--interactive`: Inicia um rebase interativo, permitindo que você modifique commits individualmente.

12. `git reset`:

    - `--hard`: Reseta o índice e a working directory para o estado do commit especificado. Todas as mudanças locais serão perdidas.
    - `--soft`: Reseta apenas o índice, mantendo as mudanças na working directory.

Essas flags são apenas algumas das mais comuns e úteis para diversas operações diárias no Git. Cada comando Git possui várias outras opções que podem ser usadas para realizar operações específicas e detalhadas. Para uma lista completa de flags e suas descrições, você pode consultar a documentação oficial do Git ou usar git help <command> para mais informações sobre um comando específico.

Podem haver CONFLITOS ao realizar o merge entre duas branches. Se um conflito ocorre, é necessário selecionar qual versão deve ser mantida e qual deve ser descartada.

Nesses casos pode ser necessário usar a flag `-r` ou `--rebase` com o comando de `push`ou `pull`, com a flag `--rebase`, você pode pegar todas as alterações que foram confirmadas em um branch e reproduzi-las em outro. O rebase tem recursos poderosos para reescrever o histórico, logo em alguns casos é usado como parte da resolução de conflitos. Em ultimo caso usamos para aresolução dos conflitos a flag `-f` ou `--force` para forçar o comando.

# Comandos Git utilizados juntos

`git add .`
`git commit -m "Mensagem"`

## Conventional Commits

A convenção dos Conventional Commits consiste em seguir um formato específico para a mensagem de commit, que geralmente é composta por três partes principais: tipo, escopo e descrição. A estrutura básica da mensagem de commit é a seguinte:

```
<tipo>(<escopo>): <descrição>
```

1. `Tipo`: Indica a natureza da alteração realizada. Pode ser um dos seguintes valores:

    - `feat`: Adição de uma nova funcionalidade.
    - `fix`: Correção de um bug.
    - `docs`: Alterações na documentação.
    - `style`: Alterações na formatação do código, como espaçamento, indentação, etc.
    - `refactor`: Refatoração do código, sem adição de novas funcionalidades ou correção de bugs.
    - `test`: Adição ou modificação de testes.
    - `chore`: Atualizações diversas, como alterações em scripts de build, configurações, etc.
  
2. `Escopo` (opcional): Indica a parte específica do projeto que foi modificada. Pode ser uma funcionalidade, um componente, um módulo, etc.

3. `Descrição`: Uma breve descrição da alteração realizada, usando verbos no imperativo. Deve ser clara e objetiva.

## Maneiras de contribuir com o Open Source

[Como Contribuir para o Open Source](https://opensource.guide/pt/how-to-contribute/)

## Referências

- [ChatGPT](https://chat.openai.com)
- [Getting Started Installing Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- [Uma breve história do Git](https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Uma-Breve-Hist%C3%B3ria-do-Git)
- [Criar um repositório](https://docs.github.com/pt/get-started/quickstart/create-a-repo)
- [Criando um token de acesso pessoal](https://docs.github.com/pt/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
- [Conectar-se ao GitHub com o SSH](https://docs.github.com/pt/authentication/connecting-to-github-with-ssh)
- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
- [Conventional Commits Pattern](https://medium.com/linkapi-solutions/conventional-commits-pattern-3778d1a1e657)
- [Iniciando um repositório com Git](https://www.alura.com.br/artigos/iniciando-repositorio-git?gclid=Cj0KCQjwyLGjBhDKARIsAFRNgW_W_cRNL_K8U-sTjyoPAJ1IHTQArT8X-WIvxHEGTUGf4qRUaSklnRcaAj60EALw_wcB)
