---
date: 2024-07-05
authors: [gabrielbdornas]
draft: true
comments: true
categories:
  - Webnar Automatiza.MG
---

# Como utilizar Power Automate web para chamadas de APIs

Neste post, vamos explorar como utilizar o Power Automate Desktop para chamar APIs e extrair informações relevantes. Usaremos como exemplo a API nativa do Portal de Dados Abertos do Estado de Minas Gerais, construída na plataforma open source CKAN.

<!-- more -->

![type:video](https://www.youtube.com/embed/QZFgOFXQ9Ew)

**1. Compreendendo a API:**

* **Conjunto de dados:** Utilizaremos o conjunto de dados "Cirurgias 2024" como exemplo.
* **Documentação:** A documentação da API está disponível no portal, detalhando como acessá-la.
* **Consulta:** No nosso caso, usaremos uma query RL para o RL, que acionará a API.
* **Exemplo de consulta:** Para recuperar o registro com ID 1, utilizaremos a seguinte consulta: `SELECT * FROM cirurgias WHERE id = 1`.

**2. Construindo o Fluxo no Power Automate Desktop:**

* **Criação do fluxo:**
    * Acesse o Power Automate Desktop e crie um novo fluxo instantâneo com gatilho manual.
    * Desative o "New Design" (opcional).
* **Ação HTTP:**
    * Adicione a ação "HTTP" e configure-a conforme as instruções da documentação da API.
    * **Método:** GET
    * **URL:** [https://dados.mg.gov.br/](https://dados.mg.gov.br/)
    * **Query:** SQL (no nosso caso, a consulta `SELECT * FROM cirurgias WHERE id = 1`)
* **Verificação do fluxo:**
    * Salve o fluxo e execute-o para verificar se a API está sendo chamada com sucesso.
    * O resultado deve ser um JSON contendo as informações do registro recuperado.

**3. Extraindo Informações do Resultado da API:**

* **Variáveis:**
    * Crie uma variável chamada "body" para armazenar o corpo da resposta da API.
    * Crie variáveis adicionais para armazenar cada campo de interesse do registro (por exemplo, "unidade", "porte").
* **Expressões:**
    * Utilize expressões para extrair os valores dos campos desejados do JSON.
    * Por exemplo, para extrair o valor do campo "unidade", utilize a seguinte expressão: `variable(body)[`result`][`records`][0][`unidade`]`.
* **Teste e refinamento:**
    * Teste as expressões para garantir que os valores corretos estejam sendo extraídos.
    * Refine as expressões e adicione variáveis conforme necessário para extrair todos os campos desejados.

**4. Considerações Adicionais:**

* **Licença:** A ação HTTP no Power Automate Desktop requer uma licença premium.
* **Autenticação:** APIs mais complexas podem exigir autenticação adicional, como tokens de acesso ou chaves API.
* **Manipulação de Dados:** O Power Automate Desktop oferece diversas ferramentas para manipular e analisar os dados extraídos da API.

**Conclusão:**

Este tutorial demonstra como chamar APIs e extrair informações relevantes utilizando o Power Automate Desktop. O exemplo do Portal de Dados Abertos de Minas Gerais serve como base para aplicações em diversos outros cenários. Com prática e conhecimento da API em questão, é possível automatizar tarefas complexas e integrar dados de diversas fontes.

**Recursos Adicionais:**

* [Vídeo de referência](URL como usar api no power automate desktop ON YouTube youtube.com): Este vídeo demonstra o processo passo a passo de chamar a API do Portal de Dados Abertos de Minas Gerais no Power Automate Desktop.
* Documentação do Power Automate Desktop [URL inválido removido]: A documentação oficial do Power Automate Desktop oferece informações detalhadas sobre todas as ações e funcionalidades disponíveis.
* Portal de Dados Abertos de Minas Gerais [URL inválido removido]: O portal oferece diversos conjuntos de dados públicos e documentação para suas APIs.

**Lembre-se:** Este tutorial serve como ponto de partida. É fundamental consultar a documentação da API específica que você deseja utilizar para obter informações detalhadas sobre seus recursos e requisitos.

## Referências
