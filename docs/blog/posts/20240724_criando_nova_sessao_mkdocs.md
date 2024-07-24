---
date: 2024-07-24
authors: [gabrielbdornas, augustacora]
draft: True
comments: true
categories:
  - DCD
---

# Criando nova sessão Mkdos :simple-materialformkdocs:

Neste encontro discutimos a utilização da ferramenta [mkdocs-material](https://squidfunk.github.io/mkdocs-material/), mais especificamente como criar novas sessões em um site já existente.

<!-- more -->

![type:video](https://www.youtube.com/embed/tsVfmCxWZT8)

## Criar a estrutura da pasta

- Criar a pasta `projetos` dentro do diretório `doc`.
- Criar o arquivo `index.md` dentro da pasta `projetos`.

# Configurar o MKDocs

- Adicionar a nova sessão à navegação no arquivo `mkdocs.yml`, propriedade `nav`.
- Definir o título da sessão como "Nossos Projetos".
- Definir o caminho para o arquivo `projetos/index.md` da pasta `projetos` como o link da sessão.

    ```yml linenums="1" hl_lines="8-12"
    # mkdocs.yml file

    nav:
    - Início: index.md
    - Biblioteca de robôs:
      - robos/index.md
    - Curso: https://www.ead.planejamento.mg.gov.br/course/view.php?id=98
    - Nossos projetos:
      - projetos/index.md
      - FJP:
          - projetos/fjp/index.md
          - Lançamento Taxação SISAP: projetos/fjp/lancamento_taxacao_sisap.md
    - Blog:
      - blog/index.md
    ```

## Criar o conteúdo da página

- Adicionar um título à página `index.md` da pasta `projetos`.
- Adicionar um texto explicativo sobre a nova sessão "Nossos Projetos".
- Incluir um arquivo para cada projeto dentro da pasta `projetos`.

## Testar e validar

- Iniciar o servidor local do MKDocs com o comando `mkdocs serve`.
- Acessar o site no navegador web.
- Verificar se a nova sessão "Nossos Projetos" está presente na navegação.
- Clicar na sessão para verificar se o conteúdo da página `index.md` está correto.
- Testar os links para os projetos realizados via Automações PMG.

## Comitar as alterações

- Adicionar os arquivos modificados ao repositório Git.
- Criar um commit com uma mensagem descritiva.
- Fazer o push das alterações para o repositório remoto.
- Criar um PR para aprovação e merge na branch `main`.

## Observações

- A opção `navigation.tabs` não foi utilizada nesta implementação, pois conflitava com a opção `navigation.sections`.
- É importante testar as páginas existentes e criadas para garantir a compatibilidade da nova implementação.
- A documentação do [mkdocs-material](https://squidfunk.github.io/mkdocs-material/) deve sempre ser consultada para mais informações sobre as opções de configuração disponíveis.

## Referência

- Documentação [mkdocs-material](https://squidfunk.github.io/mkdocs-material/)
- Após todos estes pontos discutidos, chegamos [neste código](https://github.com/automatiza-mg/automatizacoes/tree/8fc0f1c264e00dde1da15b7daf804187a8da7bc0).
