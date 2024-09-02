---
date: 2024-07-09
authors: [henriquesiqr]
draft: false
comments: true
categories:
  - DCD
---

# Listando os principais comandos utilizados na Git Bash

Para a utilização do terminal de comando, é necessária a memorização de diversos comandos para a plena utilização de todas as funcionalidades. Entretanto, sobretudo para usuários iniciantes, o autodesenvolvimento na ferramenta é extremamente complicado sem o auxílio de uma "cola", que ajuda a destravar a utilização do terminal durante as primeiras utilizações.
Obviamente, o conhecimento e fluidez na utilização da Git Bash só ocorre com o tempo e a prática, porém, uma lista com os comandos básicos pode ser um bom "empurrãozinho" para ajudar a tornar esse momento menos espinhoso.
Para isso, explico neste post alguns dos comandos básicos para guiar a navegação no terminal.

<!-- more -->
Antes de colocar a lista dos principais comandos, é importante ressaltar que a utilização do "--help" na frente de qualquer comando faz com que o Git Bash dê uma ajuda explicando a sintaxe e os retornos daquele comando.

Lista principais comandos:

## Utilizando a navegação dentro do próprio PC
* pwd (“Print Working Directory”) -> Mostra em qual diretório está trabalhando no momento.
* cd [nome_diretorio] (“change directory”) -> Altera o diretório em que está trabalhando para a pasta indicado no [nome_pasta]
* cd .. -> Retorna ao diretório anterior
* ls -> Lista o conteúdo da diretório que está trabalhando no momento.
* ls -la -> Lista o conteúdo da diretório que está trabalhando no momento, inclusive o que está oculto. Comando importante para verificar, por exemplo, se o “.git” está ativo naquele diretório.
* rm -rf  [nome_documento] -> Remove arquivo/diretório/pasta permanentemente.
* touch [nome_arquivo.extensao_arquivo] -> Cria um arquivo (ex: touch artigo.docx).
* mkdir [nome_pasta] -> Cria uma pasta

## Utilizando o git e github no terminal
* git init -> Inicializa o git no diretório em que se está trabalhando no momento. Ou seja, a partir da inicialização do git, é possível o versionamento.
* git clone [link_repositorio] -> Clona o repositório do GitHub na máquina local.
* git status -> É possível verificar se a navegação está na versão mais recente do diretório/repositório. Além disso, mostra se existe mudanças a serem commitadas.
* git log -> Mostra a lista de commits daquele repositório.
* git add -> Adiciona alteração realizadas em documentos ao git.
* git commit –m “[Mensagem do commit]” -> Realiza o commit com a mensagem que explica qual alteração foi feita.
* git push -> Utilizado para “empurrar” as alterações realizadas ao github. Obs: é necessário indicar o repositório (via de regra: “origin”) e a branch (ex: “main”). Ou seja, um push comumente fica redigido como: git push origin main.
* git pull -> Atualiza o repositório na máquina com a versão mais atual. Também é necessário indicar repositório e branch, ex: git pull origin main.
* git restore -> Utilizado para restaurar versões de arquivos.
* git checkout [branch] -> Alterna entre as branches do repositório.
* git checkout -b “nome_branch” -> Cria e nomeia uma nova branch.
* git switch "nome_branch" -> Também alterna entre as branches do repositório.
