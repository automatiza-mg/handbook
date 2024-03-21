---
date: 2023-10-25
authors: [gabrielbdornas]
comments: true
categories:
  - Ferramentas
---

# Guia de estilo de nossas páginas

Neste post definiremos algumas regras simples, mas muito efetivas, para manter o padrão entre as páginas deste ou qualquer outro site sob nossa responsabilidade.
Criados com auxílio da ferramenta [MkDocs](https://www.mkdocs.org/) e um de seus temas mais famosos, [Material](https://squidfunk.github.io/mkdocs-material/)[^2], estes conteúdos estão, quase que exclusivamente, em arquivos de texto no formato [Markdown](https://www.markdownguide.org/basic-syntax/) (`.md`).

<!-- more -->

Neste sentido, proponho as seguintes regras durante a elaboração de conteúdo nos arquivos `.md`:

## Blog post

- Escritos em arquivos `.md` dentro de uma pasta principal `docs/blog/posts`:

```yml
- docs
  - blog
    - posts
      - yyyymmaa_nome_post_reduzido.md
```

- Nome da arquivo do post deverá sempre iniciar com data no padrão `yyyymmaa`[^3].
- Imagens deverão ser incluídas em formato `.webp` na [conta](https://github.com/automatiza-mg/acessos) [Cloudinary](https://cloudinary.com/users/login) da diretoria.
- Vídeos deveráo ser incluídos no canal [YouTube](https://www.youtube.com/channel/UCZU69STFD8lrtuZ5rdl0fuA) da diretoria.
- Posts não finalizados deverão ser marcados com a [propriedade `draft: true`](https://squidfunk.github.io/mkdocs-material/setup/setting-up-a-blog/?h=blog#writing-your-first-post:~:text=Create%20a%20new%20file%20called):

> If you mark a post as a draft, a red marker appears next to the post date on index pages. When the site is built, drafts are not included in the output. This behavior can be changed, e.g. for rendering drafts when building deploy previews.


## Cabeçalhos

- Somente primeira letra maiúscula[^1].
- Título da página definido com [heading level 1](https://www.markdownguide.org/basic-syntax/#:~:text=%23-,Heading%20level%201,-%3Ch1%3EHeading%20level) (`#`).
- Demais cabeçalhos da página definidos com [heading level 2](https://www.markdownguide.org/basic-syntax/#:~:text=%23%23-,Heading%20level%202,-%3Ch2%3EHeading%20level) (`##`).
- Não utilizar heading level 3 em diante.

## Listas

- Somente primeira letra maiúscula[^1].
- Finalizados com pontos (`.`) e não com ponto e vírgula (`;`).

## Navbar

- Inclusão de itens na navbar ocorrerá sempre pela propriedade `nav` do arquivo `mkdocs.yml`:
- Isso visa garantir a inclusão de acentos e caracteres especiais nos títulos das páginas.

```yml
# Arquivo mkdocs.yml na raiz do repositório

--8<-- "mkdocs.yml:nav"
```

## Nomenclatura de arquivos e pastas

- Arquivos e pastas serão sempre nomeados no padrão [snake small case](https://en.wikipedia.org/wiki/Snake_case).
- Arquivos e pastas deverão ser criados, preferencialmente, dentro da pasta `docs`.

## Parágrafos

- Somente primeira letra maiúscula[^1].
- Para simplificar o processo de revisão dos arquivos `.md`, incluir cada frase em uma linha.
- A separação entre parágrafos deverá ser feita com a utilização de uma linha em branco entre um bloco de frases ou parágrafos.

## Robôs

- Especificamente para páginas de robôs do site [Automatiza.MG](https://automatiza-mg.github.io/automatizacoes/robos/).
- Criado em arquivo `index.md` dentro de uma pasta principal que deverá ser criada com a seguinte estrutura:

```yml
- docs
  - robos
    - nome_robo
      - assets
        - fluxo.md
        - arquivo_auxiliar_1.csv
        - arquivo_auxiliar_2.pdf
      - index.md
```

- Pasta `assets` deverá conter com, no mínimo `fluxo.md` do robô.
- Imagens deverão ser incluídas em formato `.webp` na [conta](https://github.com/automatiza-mg/acessos) [Cloudinary](https://cloudinary.com/users/login) da diretoria.
- Vídeos deveráo ser incluídos no canal [YouTube](https://www.youtube.com/channel/UCZU69STFD8lrtuZ5rdl0fuA) da diretoria.

## Tags

- Tags são categorias padronizadas para facilitar a busca de conteúdo em cada site.
- Deverão ser evitadas tags com duas palavras. Tente utilizar apenas uma palavra, sempre que possível, englobando todas as características principais de um grupo de robôs[^4].

[^1]: Com exceção de nomes próprios e ou siglas.
[^2]: Use e abuse da documentação do tema [Material](https://squidfunk.github.io/mkdocs-material/) para criar páginas cada vez mais atrativas.
[^3]: Ano com quatro dígitos, mês e dia com do dois. Exemplo `20231025`.
[^4]: O [Issue número 5](https://github.com/automatiza-mg/automatizacoes/issues/5) do repositório [automatizações](https://github.com/automatiza-mg/automatizacoes) contém discussão inicial para a criação de guia de estilo para tags.
