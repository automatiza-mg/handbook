---
date: 2024-07-05
authors: [Isabelle-Fernandes]
comments: true
dratf: false
categories:
  - DCD
---

# Como programar o BO para emitir relatórios?

No dia a dia do servidor, os relatórios do BO (BI do SAP BusinessObjects) são ferramentas essenciais para o monitoramento de eventos e atividades,
análise de dados e tomada de decisões estratégicas. Sua frequência de emissão, inclusive diária para alguns casos, torna a exportação manual uma tarefa
repetitiva e que consome tempo valioso do servidor.
<!-- more -->

A emissão dos relatórios pode ser programada, automatizando o processo e otimizando o tempo do servidor. Esse post tem como objetivo mostrar
o passo a passo de como programar o BO para emitir o relatório automaticamente.

O BO oferece a opção de programar a exportação do relatório e enviar por e-mail, enviar para servidor FPT (uma espécie de pastinha na rede),
entre outros. Nesse post, será mostrado o passo a passo de como programá-lo para exportar e enviar via e-mail.

## Passo a passo

1. Com o botão direito do mouse, clique sobre o relatório que deseja programar. Depois, clique em programar.

    ![image](https://github.com/automatiza-mg/handbook/assets/65547646/805b3096-bddb-43c3-90a3-9b1b9d826259)

2. Clique em `Recorrência` no menu a esquerda. Neste caso, vamos programar para ser semanal. Então, em `Executar objeto:`, selecione por semana. Caso o desejo seja
diário, mensal, entre outros, selecione a opção que melhor atenda seus objetivo.

    ![image](https://github.com/automatiza-mg/handbook/assets/65547646/52c60402-1269-4787-a84e-6e53d86f66ef)

3. Nas configurações de recorrência, coloquei para exportar toda segunda-feira. Caso fosse mais de um dia da semana, só selecionar os demais dias.
Em `Data/hora inicial` e `Data/hora final` coloquei 7:00 e 7:30, respectivamente. Quer dizer que é nessa janela que será feita a exportação.

    **Dica:** O BO é atualizado todos os dias entre 00:00 até 5:00 da manhã. Então, colocar a data início depois desse horário, que é quando ele
    terá feito suas atualizações. As datas já vem preenchidas por default, com intervalo de 10 anos entre elas. Isso quer dizer que ele estará programado
    para realizar essa exportação de forma automática por 10 anos. Caso seja o desejo colocar outra data, só alterar. No exemplo abaixo, será mantida a data padrão.

    ![image](https://github.com/automatiza-mg/handbook/assets/65547646/e431e6b7-372c-418f-90f0-5491decaab84)

- 4. Em `Formatos`, desejo arquivo CSV padrão UTF-8.

    ![image](https://github.com/automatiza-mg/handbook/assets/65547646/04a0b6f4-87d4-4874-b1d4-a720f33afc30)

- 5. Após configurar `Formatos`, vá em `Destinos`. Na lista, está aparecendo *Local corporativo padrão*. Troque para *E-mail*.
Em remetente do e-mail, coloque sempre **bimg@prodemge.gov.br**. Em destinatário, coloque o endereço de e-mail que deseja que seja enviado o relatório.
Preencha o campo `Assunto` e `Mensagem` e clique em agendar.

    ![image](https://github.com/automatiza-mg/handbook/assets/65547646/3ff523ae-31d5-4b13-a7d7-bb5f34c7188c)


**Pronto! Seu BO está programado para enviar relatório automaticamente.**


### **Extra**

Caso deseje que seu relatório tenha o nome do arquivo renomeado como uma variável data, você consegue fazer. Para isso, no menu `Destinos` (do passo 5),
clique em `Usar nome específico`. Na lista `Adicionar espaço reservado`, clique em `Data`. A variável **%SI_DATE%** será exatamente a data preenchida no formato
AAAA/MM/DD e ela que dará nome ao seu arquivo. Você pode usá-la também no assunto e corpo do seu e-mail.

![image](https://github.com/automatiza-mg/handbook/assets/65547646/6ac48c99-6b85-4b73-afd6-75f8069ffd18)
