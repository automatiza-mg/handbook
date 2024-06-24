---
date: 2024-06-21
authors: [gabrielbdornas]
comments: true
categories:
  - Webnar Automatiza.MG
---

# Webnar Automatiza.MG #5

Aqui na equipe Automatiza.MG Sexta-feira é dia de conhecimento!
Dia de Webnar Automatiza.MG.
Nesses encontros, mergulhamos no universo da tecnologia, desvendando os segredos de ferramentas como Git, GitHub, Python, Power Automate e muito mais.
É a nossa chance de se atualizar, compartilhar conhecimento e aprimorar nossas habilidades! :rocket::rocket:

<!-- more -->

Não perca essa oportunidade de contribuir para o crescimento de nossa equipe, seja participando como ouvinte ou como tutor!

No encontro do dia 21/06/2024 focamos, basicamente, em Praticar os comandos do Terminal, Git a utilização do GitHub.

![type:video](https://www.youtube.com/embed/FmKzT5Lr_kg)

## Terminal cheat sheet

```sh
# Não se esqueça de utilizar --help em caso de dúvidas
# Não se esqueça de usar tab para ajudar a completar caminho de arquivos/pastas
# Setas (cima e baixo) ajudam a buscar comandos já utilizados

# print working directory
# mostra o caminho do diretório atual
# hint: Ótimo para nos localizar
$ pwd

# list
# lista arquivos e pastas do diretório altual
# hint: ls -la lista, inclusive, arquivos "escondidos" (iniciados com .)
$ ls

# change directory
# movimentação entre diretórios
# cd <nome-pasta> - entra em uma pasta
# cd .. - sai de uma pasta
# hint: cd (sozinho) te leva para home (~/)
$ cd

# make directory
# cria diretórios
# hint: mkdir nome-nova-pasta
$ mkdir

# cria arquivos, independente de sua extensão
# hint: touch nome_novo_arquivo.ext
$ touch

# visualiza conteúdo de um arquivo
# hint: cat nome_arquivo.ext
$ cat

# apaga arquivos e pastas
# CUIDADO conteúdo é automaticamente removido sem passar pela lixeira
# hint: rm nome_arquivo.ext remove um arquivo / rm -rf nome-pasta remove uma pasta
$ rm
```

## Git cheat sheet

??? note "**Clique para ver um fluxo git**"

    ```mermaid
    graph TD;
    1((Início))-->2;
    2{git iniciado no projeto?}
    2 --> |não| 3[git init]
    3 --> 11[Cria repositório Github]
    11 --> 12[git remote add <nome_remote> <endereço_remote>]
    12 --> 4
    2 --> |sim| 2.1[git pull origin main]
    2.1 --> 4
    4[git status]
    4 --> 5{Commitar na branch main?}
    5 --> |sim| 6[git add <file_name>]
    6 --> 7[git commit -m <commit_message_entre_aspas>]
    7 --> 5
    5 --> |não| 8{Criar nova branch?}
    8 --> |sim| 9[git pull origin main]
    8 --> |não| 16((Fim))
    9 --> 10[git checkout -b <nova_branch_nome>]
    10 --> 13{Commitar?}
    13 --> |sim| 14[git add <file_name>]
    14 --> 15[git commit -m <commit_message_entre_aspas>]
    13 --> |não| 17{Abrir PR Github?}
    15 --> 13
    17 --> |sim| 18[git push <nome_remote> <nova_branch_nome>]
    17 --> |não| 16
    18 --> 20[Abrir/aprovar PR Github]
    20 --> 21[git checkout main]
    21 --> 22[git pull origin main]
    22 --> 23{Deletar <nova_branch_nome> já mergiada?}
    23 --> |sim| 24[git branch -d <nova_branch_nome>]
    23 --> |não| 5
    24 --> 5
    ```

```sh
# origin = apelido para github
# HEAD = apelido da minha máquina
# main = apelido para versão principal do projeto

# inicia versionamento
# realizado apenas uma vez
# hint: não necessário quando clonamos um repositório GitHub
$ git init

# meu melhor amigo
# verifica o status de mudanças no repositório
# arquivos mostrados em vermelho: necessário add
# arquivos mostrados em verde: necessário commit
# sem mostrar menhum arquivo: nada modificado no repositório
$ git status

# lista commits realizados
# ordena do commit mais recente
$ git log

# adiciona arquivo para ser commitado
# git add nome_arquivo.ext
# hint: giit add . adiciona todos os arquivos disponíveis
$ git add

# gera commit (salva aquela versão)
# git commit -m "Add uma mensagem com significado daquela mudança"
# git commit (sem a flag -m) abre um arquivo
$ git commit

# volta no tempo
# vai para o futuro
# necessita do número do commit (hash)
# git checkou hasDoCommit
# hint: git checkout main vai para a versão atual
$ git checkout

# copia um repositório do GitHub na minha máquina
# hint: git clone caminho-repositório-github (https/ssh)
$ git clone

# puxa código do GitHub
# hint: git pull origin main
$ git pull

# empurra código para o GitHub
# hint: git pulsh origin main
$ git push
```

## Referências

- [practice-git GitHub repositorio](https://github.com/grayghostvisuals/practice-git).
- [git-practice](https://github.com/PIC16B/git-practice).
- [YouTube video Braico.Me | Terminal, Git & GitHub #1](https://youtu.be/bKJtCLuAp_g)
- [YouTube video Braico.Me | Terminal, Git & GitHub #2](https://youtu.be/_EmJhGWEEL0)
