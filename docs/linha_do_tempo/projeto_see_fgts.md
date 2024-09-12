---
comments: true
---

# Linha do Tempo Projeto FGTS-SEE

O [projeto FGTS da SEE](https://github.com/automatiza-mg/projeto-see-fgts) consiste na automatização do processo de geração e entrega das chaves eletrônicas (tipo tokens) aos professores que têm direito a receber parcelas do FGTS, segundo acordo da AGE. 

A estruturação do desenvolvimento deste projeto está explicitada nos documentos do repositório próprio:  

- [Etapas](https://github.com/automatiza-mg/projeto-see-fgts/blob/main/etapas.md)
- [Fluxo](https://github.com/automatiza-mg/projeto-see-fgts/blob/main/fluxo.md)
- [Métricas](https://github.com/automatiza-mg/projeto-see-fgts/blob/main)


## Visão mensal detalhada

??? "Julho 2024"

    ```mermaid
    timeline
        03/07 a 09/07 : Primeiro contato equipe FGTS da SEE.
                      : Definido que o projeto será atendido no formato de imersão.
        10/07 a 14/07 : Leitura da documentação prévia
                      : Mapeamento das dúvidas iniciais
        15/07 a 18/07 : Primeiras reuniões com a equipe técnica
        19/07 a 23/07 : Estruturação das etapas do trabalho
                      : Testes nas bases para exclusão de processos e inconsistências no PIS
                      : Ajustes no código do PA já utilizado pela equipe 
    ```

??? "Agosto 2024"

    ```mermaid
    timeline
        01/08 a 09/08 : Recepção e testes no relatório do B.O.
        10/08 a 18/08 : Aguardando disponibilização da máquina virtual na SEE
        19/08 a 23/08 : Busca de fontes alternativas para filtrar emails inválidos
                      : Inserção de motivos de erro em cópia do código utilizado
                      : Configuração e primeiro acesso na máquina virtual da SEE
        24/08 a 31/08 : Inserção de envio de emails em código para chaves geradas              
    ```