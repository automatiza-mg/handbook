---
comments: true
---

# Linha do Tempo Projeto FHEMIG

O [projeto FHEMIG](https://github.com/automatiza-mg/projeto-fhemig) consiste em uma séria de ações para automatizar processos na Fundação Hospitalar do Estado de Minas Gerais. Principais entregas:

- [Automatizar processo Promoção e Progressão](https://github.com/automatiza-mg/projeto-fhemig/issues/6).
- [Automatizar fluxo de análise de inconsistência relatório de custos](https://github.com/automatiza-mg/projeto-fhemig/issues/4).

## Visão mensal detalhada

??? "Julho 2024"

    ```mermaid
    timeline
        15/07 a 21/07 : Primeiro contato equipe custos Fhemig.
                      : Levantamento relatórios custos necessários Pentaho.
                      : Primeiro contato equipe RH, promoção e progressões.
        22/07 a 28/07 : Busca relatórios custo no Pentaho.
                      : Desenho fluxo promoção e progressão.
        29/07 a 04/08 : Solicitação acesso base de dados SQL relatórios custos.
                      : Análise relatórios BO promoção e progressão.
    ```

??? "Agosto 2024"

    ```mermaid
    timeline
        05/08 a 11/08 : Aguardando acesso base de dados SQL relatórios custos.
                      : Aguardando análise campos BO promoção e progressão.
        12/08 a 18/08 : Fhemig solicitou Prodemge liberação faixa IP para acesso base de dados SQL relatórios custos. Finalização script que realiza apontamentos de inconsistência.
                      : Análise BO feita e constatação de dados discordantes com os do Sisap.
        19/08 a 25/08 : Prodemge liberou faixa IP para acesso base de dados SQL relatórios custos. Criação de usuário para conexão com os bancos feitas no DBeaver.
        26/08 a 30/08 : Acesso as querys e adequação das mesmas feitas para que utilize somente a base de dados `sigh_slave`.
    ```

??? "Setembro 2024"

    ```mermaid
    timeline
        02/09 a 08/09 : Readequação script apontamento com os relatórios obtidos pela conexão e modificações solicitadas pela coordenadora de Custos. Projeto finalizado e aguardando próximo apontamento para uso/teste.
    ```
