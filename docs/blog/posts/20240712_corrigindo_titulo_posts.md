---
date: 2024-07-12
draft: false
authors: [andrelamor]
comments: true
categories:
  - Tira Dúvidas
---

# Como editar títulos dos posts no MKDocs

Uma das possibilidades de erro ao publicarmos um post aqui no _Handbook_ é cometer um deslize na grafia de alguma palavra (_typo_). Isso pode ocorrer pela ausência de corretor automático de português no seu editor de texto. Às vezes, são muitos detalhes para publicar, tanto no conteúdo, quanto na forma de operar a linha de comando, que passamos batido em um errinho de português, né? A questão aqui, diferente de uma correção nas demais partes do texto do seu post, o que é escrito no **título** determina o endereço (URL) da página onde a postagem vai ficar, então a correção demanda uma operação a mais na linha de comando, com o `deploy gh-pages` do Mkdocs. Vamos ver como fazer?

<!-- more -->

## Como funciona a publicação automatizada dos posts

Quando fazemos uma postagem nos blogs do Github, usando Mkdocs, o actions dos repositórios nos dá uma ajudinha na publicação, porque eles já carregam todas as instruções necessárias para transformar os arquivos do formato `markdown`(.md) apra o formato `html` que, na prática, são os próprios _posts_ publicados. Estes arquivos contendo as instruções se cahmam `publish_github_pages.yml`e estão:

- No repositório do [Handbook](https://github.com/automatiza-mg/handbook/blob/main/.github/workflows/publish_github_pages.yml)

- No repositório do [Automatiza](https://github.com/automatiza-mg/automatizacoes/blob/main/.github/workflows/publish_github_pages.yml)

A construção da documentação da página do post no formato `html` é um processo que se denomina **deploy**, e pode ser visto no histórico de commits da branch `gh-pages`, seja no [Handbook](https://github.com/automatiza-mg/handbook/commits/gh-pages/) ou no [Automatiza](https://github.com/automatiza-mg/automatizacoes/commits/gh-pages/).

Como geralmente trabalhamos somente na branch `main`, elaborando e editando os conteúdos, não percebemos o que rola nos bastidores, mas o github-actions está lá automatizando parte das nossas ações de publicação! Se vc notar bem, a autoria dos `commits` quase sempre é do _bot_, identificado pelo ícone do OCTOCAT. 

Entretanto, quando precisamos corigir algum erro de grafia no título do post, aparece nosso nome como autor do deploy (olha só nesse [exemplo](https://github.com/automatiza-mg/automatizacoes/commit/f2705a153703fbdd4b75ca0ab548c2d9a43f3771)). Mas, como fazer isso?  

## Como corrigir o título de um post com `mkdocs gh-deploy`

Sem o passo 4 abaixo, ó só: 
![image](https://github.com/user-attachments/assets/92555f75-0369-48eb-b99f-c241c81a9466)

1. Abra o arquivo a ser corrigido no teu editor de texto de preferência e efetue a modificação necessária

2. Para confirmar se a alteração ficou certinha, com o (venv) ligado, dá um `mkdocs serve` e veja lá no [http://127.0.0.1:8000/blog/](http://127.0.0.1:8000/blog/)[^1] do teu ambiente local se era isso mesmo

3. Se estiver ok, manda lá na linha de comando os procedimentos de `git add` e `git commit` habituais

4. Aqui vem a novidade, antes do `git push`, ANTEÇÃO! Chama um `mkdocs gh-deploy` pra nós, please. O que esse trem vai fazer? O que os arquivos `publish_github_pages.yml` fazem automaticamente pra gente lá nos repostiórios, quando enviamos conteúdos pra publicar. Mas, André, por que o actions do Github não resolve essa parada pra mim? Porque a URL do post já existe, ele vai procurar esse mesmo endereço e não vai entender, vai ficar perdido...tadinho do nosso OCTOCAT! Depois desse comando de **deploy**, vc vai perceber que rola um tanto de trem na linha de comando...

5. ...mas como saber se **deploy** tá pronto pra ser commitado:
Cheque se o texto abaixo aparece
````
INFO    -  Documentation built in 7.95 seconds
INFO    -  Copying 'C:\Users\Andre\Documents\SIGES-SEPLAG\handbook\site' to 'gh-pages' branch and pushing to GitHub.
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 342 bytes | 171.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/automatiza-mg/handbook
   ed4a5ff..ada76b8  gh-pages -> gh-pages
INFO    -  Your documentation should shortly be available at: https://automatiza-mg.github.io/handbook/

````
 ![image](https://github.com/user-attachments/assets/f69cfcc8-7cac-4eb2-ad5b-a97347faa8b4)

Bem, se a linha de comando terminar de processar e o cursor voltar a piscar, faz aquele `git push origin main` maroto, e vê lá se ficou bão agora... se der certo, vai aparecer teu nickname do github como autor de um dos commits nos históricos das branches `gh-pages`, blz?
![image](https://github.com/user-attachments/assets/461e1698-4f19-43d9-a785-41eba97e1a54)

[^1]: Já reparou que esse link é perene? Manjou a possibilidade de favoritar esse endereço pra toda vez que vc quiser ver as alterações antes de commitar? Dá um like aí embaixo se vc gostou dessa dica, vai...
