---
date: 2024-07-19
authors: [gabrielbdornas]
draft: false
comments: true
categories:
  - Webnar Automatiza.MG
---

# Webnar Automatiza.MG #9

Aqui na equipe Automatiza.MG Sexta-feira é dia de conhecimento!
Dia de Webnar Automatiza.MG.
Nesses encontros, mergulhamos no universo da tecnologia, desvendando os segredos de ferramentas como Git, GitHub, Python, Power Automate e muito mais.
É a nossa chance de se atualizar, compartilhar conhecimento e aprimorar nossas habilidades! :rocket::rocket:

<!-- more -->

Não perca essa oportunidade de contribuir para o crescimento de nossa equipe, seja participando como ouvinte ou como tutor!

No encontro do dia 19/07/2024 entendemos o funcionamento da biblioteca Mermaid.

![type:video](https://www.youtube.com/embed/N7oEjDQQ7hk)

## Mostrando utilização do Mermaid

??? "Código demonstrado também no [Issue 181](https://github.com/automatiza-mg/handbook/issues/181)"

    ```mermaid
    flowchart TB
        1([Início]) --> 2
        2[Fazer login SEI] --> 3
        3{Login realizado com sucesso?}
        3 --"Sim"--> 3.1
      3 --"Não"--> 1
      3.1["`This **is** _Markdown_`"]
      3.1 --> 4([Fim])

      5["`Item 1
            Item 2`"]

    subgraph subgraph1
            direction TB
      top1[top] --> bottom1[bottom]
        end
    ```

## Referências

- [Mermaid Flowcharts - Basic Syntax](https://mermaid.js.org/syntax/flowchart.html).
