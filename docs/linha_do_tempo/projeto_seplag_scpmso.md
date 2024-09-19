---
comments: true
---

# Linha do Tempo Projeto SEPLAG-Perícia Médica

O [projeto SEPLAG-Perícia](https://github.com/automatiza-mg/projeto-seplag-pericia) consiste em uma série de ações para automatizar processos da perícia médica da Superintendência Central de Perícia Médica e Saúde Ocupacional (SCPMSO) da SEPLAG. Principais entregas:

- [Benchmarking Regras Perícia](https://github.com/automatiza-mg/projeto-seplag-pericia/issues/8)
- [Preenchimento do BIM-Servidor com dados do SISAP](https://github.com/automatiza-mg/projeto-seplag-pericia/issues/1)
- [Preenchimento do BIM-Servidor com dados do SISAP (frente Power AUtomate + SISAP)](https://github.com/automatiza-mg/projeto-seplag-pericia/issues/16)
- [Conferência de RPM e arquivamento no processo SEI](https://github.com/automatiza-mg/projeto-seplag-pericia/issues/6).
- [Análise documental e preenchimento do BIM-Perito no SEI](https://github.com/automatiza-mg/projeto-seplag-pericia/issues/3).

## Visão mensal detalhada

??? "Abril 2024"

    ```mermaid
    timeline
        15/04 a 30/04 : Primeiro contato com equipes técnicas da SCPMSO.
                      : Levantamento preliminar das ferramentas necessárias.
                      : Elaboração e assinatura dos termos de confidencialidade e sigilo no SEI. 
    ```

??? "Maio 2024"

    ```mermaid
    timeline
        01/05 a 15/05 : Levantamentos de regras de outros estados - bechmarking.
                      : Acessos no SEI liberados para equipe AutomatizaMG.
        16/05 a 31/05 : Desenvolvimento dos robôs - no RPM, por CPF
                      : Busca de alternativas para exceções do RPM (telas em acessos distintos no SISAP). 
    ```

??? "Junho 2024"

    ```mermaid
    timeline
        01/06 a 15/06 : Benchmark concluído - exemplo federal como imagem-objetivo
                      : Curso plataforma Sydle
                      : Versão finalizada do script em PA para o RPM por CPF.        
        16/06 a 30/06 : Busca de soluções alternativas via POC - Sydle.
    ```

??? "Julho 2024"

    ```mermaid
    timeline
        01/07 a 31/07 : Busca de soluções alternativas - BPMS.
                      : Busca de soluções alternativas - API do CKAN.
                      : Extração de amostras do BO para checagem de data de admissão em vez do SISAP.
    ```

??? "Agosto 2024"

    ```mermaid
    timeline
        15/08 a 23/08 : Retomada das ferramentas anteriores após tentativas frustradas de soluções alternativas.
                      : Dataframe reduzido extraído do BO para correspondência entre CPF (SEI) e MASP (SISAP).
        24/08 a 31/08 : Retomada das reuniões, foco redirecionado para IA dos atestados e conclusão de processos com erro no SEI
                      : Dataframe reduzido descartado pela possibilidade de capturar RPM pela nova tela do sistema SPMSO   
    ```

??? "Setembro 2024"

    ```mermaid
    timeline
        01/09 a 20/09 : Aguardando análise do resultado do primeiro teste de 50 atestados lidos pela IA
                      : Conclusão de 14,5 mil processos com erro no SEI.
    ```
