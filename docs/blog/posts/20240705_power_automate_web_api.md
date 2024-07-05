---
date: 2024-07-05
authors: [gabrielbdornas]
draft: false
comments: true
categories:
  - Ferramentas
---

# Como utilizar Power Automate web para chamadas de APIs

Neste post, vamos explorar como utilizar o Power Automate Web para chamar APIs e extrair informações relevantes. Usaremos como exemplo a API nativa do Portal de Dados Abertos do Estado de Minas Gerais, construída na plataforma open source CKAN.

<!-- more -->

![type:video](https://www.youtube.com/embed/QZFgOFXQ9Ew)

## Compreendendo a API

- **Conjunto de dados:** Utilizaremos o conjunto de dados [Cirurgias por Porte](https://dados.mg.gov.br/dataset/cirurgias) como exemplo, recurso [Cirurgias por porte - 2024](https://dados.mg.gov.br/dataset/cirurgias/resource/1f30ddd1-c9c8-4771-a21f-97f543f21ade).
- **Documentação:** A documentação da API está disponível na própria página do recurso [Cirurgias por porte - 2024](https://dados.mg.gov.br/dataset/cirurgias/resource/1f30ddd1-c9c8-4771-a21f-97f543f21ade).
- **Consulta:** No nosso caso, adaptamos o end-point `datastore_search_sql` para buscar a cirurgia de `_id` igual a `1`[^1].


## Construindo o Fluxo no Power Automate Desktop

- **Criação do fluxo:**
    * Acesse o Power Automate Web e crie um novo fluxo instantâneo com gatilho manual.
    * Desative o "New Design" (canto superior direito).
- **Ação HTTP:** Adicione a ação "HTTP" e configure-a conforme instruções:
    - **Método:** GET
    - **URL:** `https://dados.mg.gov.br/api/3/action/datastore_search_sql`
    - **Query:** Enter key `sql` e Enter value `SELECT * FROM cirurgias WHERE _id = 1`.
- **Verificação do fluxo:** Salve o fluxo e execute-o para verificar se a API está sendo chamada com sucesso.

    ??? "O resultado deve conter um JSON com as informações do registro recuperado (body)."

          ```json
          {
            "help": "https://dados.mg.gov.br/api/3/action/help_show?name=datastore_search_sql",
            "success": true,
            "result": {
              "sql": "SELECT * from \"1f30ddd1-c9c8-4771-a21f-97f543f21ade\" WHERE _id = 1",
              "records": [
                {
                  "_id": 1,
                  "_full_text": "'0':6,10 '2':8 '2024':3 'cssfa':1 'hora':9 'janeiro':2 'port':4",
                  "unidade": "CSSFA",
                  "mes": "Janeiro",
                  "ano": "2024",
                  "porte": "PORTE I (0 A 2 HORAS)",
                  "quantidade": "0"
                }
              ],
              "fields": [
                {
                  "id": "_id",
                  "type": "int4"
                },
                {
                  "id": "_full_text",
                  "type": "tsvector"
                },
                {
                  "id": "unidade",
                  "type": "text"
                },
                {
                  "id": "mes",
                  "type": "text"
                },
                {
                  "id": "ano",
                  "type": "text"
                },
                {
                  "id": "porte",
                  "type": "text"
                },
                {
                  "id": "quantidade",
                  "type": "text"
                }
              ]
            }
          }
          ```

## Extraindo Informações do Resultado da API

- **Variáveis:**
    * Crie uma variável chamada `body` para armazenar o corpo da resposta da API.
    * Crie variáveis adicionais para armazenar cada campo de interesse do registro (por exemplo, `unidade`, `porte`).
- **Expressões:** Utilize expressões para extrair os valores dos campos desejados do JSON. Por exemplo, para extrair o valor do campo `unidade`, utilize a expressão: `variable(body)?['result']?['records']?[0]['unidade']`.
- **Teste e refinamento:** Teste as expressões para garantir que os valores corretos estejam sendo extraídos.

## Considerações Adicionais

* **Licença:** A ação HTTP no Power Automate Web requer uma licença premium. Você pode ativar esta versão como teste.
* **Autenticação:** APIs mais complexas podem exigir autenticação adicional, como tokens de acesso ou chaves API.

## Conclusão

Este tutorial demonstra o básico de como chamar APIs e extrair informações relevantes utilizando o Power Automate Web.
O exemplo do Portal de Dados Abertos de Minas Gerais serve como base para aplicações em diversos outros cenários.
**Sendo assim, este post serve como ponto de partida.
É fundamental consultar a documentação da API específica que você deseja utilizar para obter informações detalhadas sobre seus recursos e requisitos antes de partir para a montagem do fluxo no Power Automate Web**.

[^1]: `https://dados.mg.gov.br/api/3/action/datastore_search_sql?sql=SELECT * from "1f30ddd1-c9c8-4771-a21f-97f543f21ade" WHERE _id = 1`
