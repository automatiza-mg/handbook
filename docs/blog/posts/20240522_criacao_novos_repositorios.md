---
date: 2024-05-222
authors: [gabrielbdornas]
comments: true
categories:
  - DCD
---

# Criando novos repositórios GitHub

Acriação de novos repositórios no GitHub é tão simples como apertar um botão.
Neste post explicarei algumas alternativas que vão simplificar, ainda mais, este processo.
Vamos que vamos 🚀🚀🚀

<!-- more -->

Para criar um novo repositório GitHub basta acessar a aba `Repositories` da organização/user GitHub desejado e selecionar a opção `New repository` no canta superior direito da tela.
Como exemplo, incluo abaixo, a tela da organização [automatiza-mg](https://github.com/orgs/automatiza-mg/repositories):

![image](https://github.com/automatiza-mg/handbook/assets/49699290/e4d20ecd-895c-409b-9d75-3ac4e5af7336)

A tela a seguir servirá para configurações básicas deste novo repositório:

![image](https://github.com/automatiza-mg/handbook/assets/49699290/2119aec3-a310-4d05-9cc3-3d096e6d29f2)

Repositório criado é hora de começarmos a incluir nossos arquivos.
Foi exatamente pensando nisso que o GitHub criou os templates de repositórios.
Com eles, é possível, criar repositórios já com os arquivos mínimos desejados para nosso futuro projeto.
Pensando nisso, criei o nosso [repositorio-template](https://github.com/automatiza-mg/repositorio-template).
Sua utilização é tão simples quanto a mostrada inicialmente, com o benefício de já criarmos um repositório com:

- Arquivo `.gitignore`, que auxilia na utilização local da ferramenta `git`.
- Arquivo `CHANGELOG.md`, que auxilia na documentação, resumida, das modificações ocorridas no projeto.
- Arquivo `README.md`, que poderá ser utilizada como documentação inicial sobre aquele repositório.
- Pasta `.github/workflows` com GitHub actions para integração do novo repositório com nosso [planner](https://github.com/orgs/automatiza-mg/projects/1)

Legal, mas como utilizá-lo?
Simples.
Vá até a página do [repositorio-template](https://github.com/automatiza-mg/repositorio-template) e clique em `Use this template` no canto superior direito da tela:

![image](https://github.com/automatiza-mg/handbook/assets/49699290/e8ac327f-ab56-4474-b861-23b2ca4161d0)

Depois realize as configurações iniciais:

![image](https://github.com/automatiza-mg/handbook/assets/49699290/86fe4779-3bc8-4dee-acdd-508380005fa1)

Prontinho.
Repositório criado e pronto para ser utilizado.
Caso queira levar o mesmo para seu computador basta fazer o clone[^1] com o endereço do novo repositório criado[^2]:

![image](https://github.com/automatiza-mg/handbook/assets/49699290/61968a19-b9d7-4b5d-a8c4-9fce747421bd)

[^1]: `git clone <endereco-novo-repositorio>`
[^2]: Máquinas da Cidade Administrativa podem não aceitar endereços `SSH`.



