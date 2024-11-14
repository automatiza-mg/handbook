---
date: 2024-11-13
authors: [henriquesiqr]
draft: False
comments: true
categories:
  - Ferramentas
---

# Buscando código da unidade no SEI

Para utilização do robô de baixar processos e documentos no SEI, presente na biblioteca de robôs do Automatiza, é necessário ter o código da unidade no SEI. Cada unidade existente no SEI possui um código específico, que é possível de ser obtido utilizando JavaScript.

<!-- more -->
!!! Info
    Não é necessário ter conhecimento na linguagem de programação Java para realizar esse procedimento, basta seguir o passo a passo descrito nesse post.

## Passo 1: Navegação no SEI
O primeiro passo para encontrar o código da unidade SEI é entrar no sistema e clicar no botão de troca de unidade:

![pag_inicial_sei](https://github.com/user-attachments/assets/4d80cc92-b328-4eaf-8476-937f5150fc79)

Depois, já com a página da troca de unidade aberta, clique com o botão direito em qualquer lugar na tela e selecione a opção "Inspecionar":

image

## Passo 2: Inspecionando a página
Nesse momento, é como se você estivesse verificando "por debaixo do capô" de um carro. Ou seja, você está vendo como essa página da Web foi construída, com todos os seus códigos em cada elemento da página. A tela ficará dividida, com a página em si do lado esquerdo e, do lado direito, os códigos e um terminal:

image

Para buscar o ID da sua unidade, você irá clicar no botão destacado abaixo, que é uma seta na diagonal em uma retângulo pontilhado:

image

A partir desse clique, ao passar o mouse sobre cada espaço da página do SEI, ele ficará destacado e no lado direito será possível ver seu código. Com isto, basta clicar na unidade SEI que deseja obter o código:

image

Com isso, você já está próximo de descobrir o ID da unidade SEI. No lado direito, você já está vendo o código desse elemento da página da Web. Observe que já é possível ver o nome da unidade no conteúdo do elemento. Entretanto, o ID fica "escondido", portanto, você terá que clicar nessa setinha que irá abrir outra linha de código:

image

Assim, após o clique, o ID irá aparecer nas linhas de código:

image

Agora basta você copiá-lo para utilizar no seu fluxo que utiliza a API do SEI.
