---
comments: false
tags:
  - projetos
---

# Projeto CET - Infrações e Controle do Condutor

- **Data:** 31/10/2023
- **Participantes**: Débora, Larissa, André
## Pauta
- Verificação de viabilidade do Power Automate em auxiliar no redesenho de 3 subprocessos mapeados e apoiados pelo LABMG (Fici, Defesa e Jari)
- fases projetadas no âmbito desse projeto:
    - 1. uso de automatização no curto prazo
    - 2. melhoria em cada um dos 3 subsistemas envolvidos
    - 3. sugestão de unificação dos 3 em um único sistema
- Pontos para consideração:
    - fluxos duplicados que correm em paralelo (documentos físicos que são protocolados e digitalizados na CAMG)
    - cidadão preenche FICI manualmente
    - pessoal do CET cadastra infração e inidiciado no SEI e no sistema próprio
    - semanas e salários poupados
- Capacidade de processamento atual: 2.500 análises mensais X 30mil processos semestrais (média de 5 mil mensais = acúmulo de um passivo mensal de 2,5 mil?)
- Ocorrência aproximada de cada subsistema:
    - 1. FICI: 80 a 100 por dia
    - 2. Defesa: centenas (gargalo)
    - 3. JARI (após penalidade)

## Dúvidas
- Power automate consegue captar valor de campo de documento digitalizado (imagem? não era pdf originalmente)
- Conseguimos ter acesso ao sistema para testar numa oficina mão-na-massa?

## Ideias
- Usar pacote da IA licensiada da Microsoft para captarmos os valores dos campos dos formulários digitalizados (nome, placa, número processo, data, etc)
- 

## Ações
- André verificar alcance do Power Automate para captar as infos necessárias e lançar no SEI e ou sistema
- Solicitar acesso ao sistema do CET para testes após confirmação de como captarmos as infos (item anterior)
- Retorno dia 09/11

## Materiais de referência
- [Fluxos descritos](https://miro.com/app/board/uXjVMHcQbII=/?share_link_id=682495063444);
- [Modelos de defesa](https://cecad365.sharepoint.com/sites/LAB.mg/Documentos%20Compartilhados/Forms/AllItems.aspx?newTargetListUrl=%2Fsites%2FLAB%2Emg%2FDocumentos%20Compartilhados&viewpath=%2Fsites%2FLAB%2Emg%2FDocumentos%20Compartilhados%2FForms%2FAllItems%2Easpx&id=%2Fsites%2FLAB%2Emg%2FDocumentos%20Compartilhados%2FGeneral%2F4%2E%20Laborat%C3%B3rio%20de%20Inova%C3%A7%C3%A3o%2F01%2E%20Projetos%20de%20Transforma%C3%A7%C3%A3o%2F1%2E%20Projetos%20em%20andamento%2FMelhoria%20de%20Servi%C3%A7os%20de%20Tr%C3%A2nsito%5FControle%20do%20Condutor%20%2D%20CET%2F03%2ECocriar%2F6%2E%20Automatiza%C3%A7%C3%A3o&viewid=11fbe8df%2D9f8b%2D40d9%2Da150%2D7bc4253aca91)
- [Prints do sistema CET](https://cecad365.sharepoint.com/sites/LAB.mg/Documentos%20Compartilhados/Forms/AllItems.aspx?newTargetListUrl=%2Fsites%2FLAB%2Emg%2FDocumentos%20Compartilhados&viewpath=%2Fsites%2FLAB%2Emg%2FDocumentos%20Compartilhados%2FForms%2FAllItems%2Easpx&id=%2Fsites%2FLAB%2Emg%2FDocumentos%20Compartilhados%2FGeneral%2F4%2E%20Laborat%C3%B3rio%20de%20Inova%C3%A7%C3%A3o%2F01%2E%20Projetos%20de%20Transforma%C3%A7%C3%A3o%2F1%2E%20Projetos%20em%20andamento%2FMelhoria%20de%20Servi%C3%A7os%20de%20Tr%C3%A2nsito%5FControle%20do%20Condutor%20%2D%20CET%2F03%2ECocriar%2F3%2E%20Prints&viewid=11fbe8df%2D9f8b%2D40d9%2Da150%2D7bc4253aca91)

