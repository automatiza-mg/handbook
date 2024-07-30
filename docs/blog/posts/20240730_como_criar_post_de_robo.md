---
date: 2024-07-30
authors: [raianecardoso]
draft: False
comments: true
categories:
  - DCD
---

# Como criar um post de instruções de um robô 

Ao final de um projeto, é importante documentar o trabalho realizado, tanto para a nossa gestão da informação, quanto para dar autonomia à equipe demandande. Assim, a ideia é que todos os nossos projetos sejam finalizados com três produtos/entregas, o que estamos chamando de Marco Final:

- o robô e seu código na máquina no demandante;
- um post com as orientações de como utilizar o robô; e
- uma reunião com os stakeholders apresentando os resultados do projeto: veja a nossa [apresentação padrão](https://cecad365.sharepoint.com/:p:/r/sites/LAB.mg/Documentos%20Compartilhados/General/7.%20DCD/Automatiza.MG/N%C3%BAcleo%20de%20Imers%C3%B5es/Material%20de%20refer%C3%AAncia/Apresenta%C3%A7%C3%A3o_Modelo_Marco_Final.pptx?d=w77a7a47bb6f24e478cfbaec5632b4fbb&csf=1&web=1&e=wkjkfj)! 

**Este post é específico para orientar o que deve conter no post que ficará no nosso site.** 

<!-- more -->

### Modelo de Documentação: Post de Robôs

**Nome do Robô:**
nome que identifica o robô, idealmente igual ao informado no banco de dados.

**Data de entrega:**
data que o robô é disponibilizado para o demandante.

**Versão:**
versão do robô.

**Responsável:**
pessoa da equipe responsável pelo robô, nome e e-mail.

**O que o robô faz:**
descrição em tópicos das ações/ funções executadas pelo robô. Exemplo, instrui processo sei, cria documentos, encaminha processo etc. Se for o caso, pode ser acompanhado de uma breve introdução ao processo e ao robô.

Idealmente, nesse tópico, podemos incluir um fluxo do robô, utilizando a ferramenta [mermaid](https://mermaid.js.org/). Uma boa dica é utilizar a ferramentas de inteligência artificial, como o [Chat GPT](https://openai.com/chatgpt/), inserindo no prompt o código e solicitando que ele crie o fluxo mermaid. Para melhores fluxos, inclua ao longo do robô comentários que descrevem as ações executadas. :wink:

**Subfluxos e suas funcionalidade no robô:**
lista os subfluxos do robô, se houver, e descreve brevemente as ações executadas naquele subfluxo.

**Pré-requisitos para o funcionamento do robô:**
lista o que o usuário precisa para o funcionamento do robô, como acesso à sistemas específicos, extensões instaladas, configurações de navegador ou da máquina, documentos, inserir variáveis de entrada no fluxo e outros. A ideia desse tópico é preparar o usuário e a sua máquina para que o robô seja executado.

**Resultados do robô:**
Este tópico deverá ser dividido em duas partes: 
  - a primeira, informa ao usuário que ele deve esperar ou encontrar após executar o robô. Por exemplo, uma planilha que informa o que o status do processo ou o número de um processo criado. Nesse tópico também pode ser elucidado como o usuário sabe se houve algum problema, ou não, na execução do robô.
  - já a segunda, deverá apresentar os resultados, em termos de métricas e indicadores, alcançados pela automação do processo. Isto é, tempo economizado, servidores reposicionados, dentre outros.

**Código:**
link com o código do robô a ser copiado pelo usuário. Importante lembrar de sempre colocar  a nota de que o usuário deverá abrir o link, selecionar todo o conteúdo (ctrl + a), copiá-lo (ctrl +c) e colar (ctrl+v) em um novo fluxo Power Automate Desktop. Caso o seu robô tenha subfluxos, lembre-se dos [cuidados ao códigos de subfluxo](https://automatiza-mg.github.io/automatizacoes/blog/copiando-c%C3%B3digo-de-subfluxos-de-um-rob%C3%B4/).

Prontinho! Agora é só comemorar mais essa entrega :rocket::rocket: