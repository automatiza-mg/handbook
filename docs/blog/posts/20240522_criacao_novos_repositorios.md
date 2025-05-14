---
date: 2024-05-22
authors: [gabrielbdornas]
comments: true
categories:
  - DCD
---

# Criando novos repositórios GitHub

Acriação de novos repositórios no GitHub é tão simples como apertar um botão.
Neste post explicarei algumas alternativas que vão simplificar, ainda mais, este processo.
Além disso teremos total integração de nosso novo repositório com projeto [planner](https://github.com/orgs/automatiza-mg/projects/1).
Vamos que vamos 🚀🚀🚀!!!!

<!-- more -->

## Criação convencional

Para criar um novo repositório GitHub basta acessar a aba `Repositories` da organização/user GitHub desejado e selecionar a opção `New repository` no canta superior direito da tela.
Como exemplo, incluo abaixo, a tela da organização [automatiza-mg](https://github.com/orgs/automatiza-mg/repositories):

![image](https://github.com/automatiza-mg/handbook/assets/49699290/e4d20ecd-895c-409b-9d75-3ac4e5af7336)

A tela a seguir servirá para configurações básicas deste novo repositório[^1]:

![image](https://github.com/automatiza-mg/handbook/assets/49699290/2119aec3-a310-4d05-9cc3-3d096e6d29f2)

Repositório criado é hora de começarmos a incluir nossos arquivos.
Foi exatamente pensando nisso que o GitHub criou os templates de repositórios.
Com eles, é possível, criar repositórios já com os arquivos mínimos desejados para nosso futuro projeto.
Neste sentido, criei o nosso [repositorio-template](https://github.com/automatiza-mg/repositorio-template).
Sua utilização é tão simples quanto a mostrada inicialmente, com o benefício de já criarmos um repositório com:

- Arquivo `.gitignore`, que auxilia na utilização local da ferramenta `git`.
- Arquivo `CHANGELOG.md`, que auxilia na documentação, resumida, das modificações ocorridas no projeto.
- Arquivo `README.md`, que poderá ser utilizada como documentação inicial sobre aquele repositório.
- Pasta `.github/workflows` com GitHub actions para integração do novo repositório com nosso [planner](https://github.com/orgs/automatiza-mg/projects/1).

## Criação turbinada

Legal, mas como utilizá-lo?
Simples.
Vá até a página do [repositorio-template](https://github.com/automatiza-mg/repositorio-template) e clique em `Use this template` no canto superior direito da tela:

![image](https://github.com/automatiza-mg/handbook/assets/49699290/e8ac327f-ab56-4474-b861-23b2ca4161d0)

Depois realize as configurações iniciais:

![image](https://github.com/automatiza-mg/handbook/assets/49699290/86fe4779-3bc8-4dee-acdd-508380005fa1)

Prontinho.
Repositório criado e pronto para ser utilizado.
Caso queira levar o mesmo para seu computador basta fazer o clone[^2] com o endereço do novo repositório criado[^3]:

![image](https://github.com/automatiza-mg/handbook/assets/49699290/61968a19-b9d7-4b5d-a8c4-9fce747421bd)

## Actions reutilizáveis

Bom, estamos quase lá.
Para que nossos actions reutilizáveis funcionem precisamos cadastrar secrets nas configurações do projeto.
Acesse as configurações gerais do GitHub utilizando o usuário admin [dcd-github-admin](https://github.com/dcd-github-admin)[^4]:

![image](https://github.com/automatiza-mg/handbook/assets/49699290/00c3902b-bbfc-4ff6-8b67-65577418ccad)

![image](https://github.com/automatiza-mg/handbook/assets/49699290/901b50c2-3f14-4346-a331-94ea52fb1ddf)

Vá até `Developer settings` no canto inferior esquerdo da página:

![image](https://github.com/automatiza-mg/handbook/assets/49699290/e8007a75-1e7f-4263-a7b0-02fe2b263523)

Selecione a opção para criação de um token clássico:

![image](https://github.com/automatiza-mg/handbook/assets/49699290/045540b2-f4b8-4da5-89b1-d71052ea723e)

![image](https://github.com/automatiza-mg/handbook/assets/49699290/3085d73d-db06-4b6e-af42-61add612b447)

E inclua as configurações necessárias para o novo token:

![image](https://github.com/user-attachments/assets/7a242431-2932-47b8-8274-3c113bf6e489)



Como padrão:

  - Campo `Note` deverá ser preenchido no padrão `organizacao-repo-name`.
  - Campo `Expiration` deverá ser preenchido como `No expiration`.
  - Opções `repo` e `project` deverão ser marcadas antes de clicar em `Generate token` no final da página.

**O token criado é mostrado apenas uma vez, então não se esqueça de anotar**.

Agora, basta voltar nas configurações do novo repositório criado e cadastrar um novo `Secret`.

![image](https://github.com/automatiza-mg/handbook/assets/49699290/8829faa1-fc0f-471a-a15e-e80eaee087ab)

![image](https://github.com/automatiza-mg/handbook/assets/49699290/c68a017e-508b-419b-972a-f11be1257e57)

Para integração com nosso planner precisamos cadastrar o `Secret` `GH_TOKEN`[^5]:

![image](https://github.com/automatiza-mg/handbook/assets/49699290/a7730cd2-5422-4534-b667-a3218d514682)

Por fim, cadastra o `Secret` `PROJECT_NUMBER`, conforme print abaixo[^6]:

![image](https://github.com/automatiza-mg/handbook/assets/49699290/f8c2b564-1ea1-4b03-93e9-40482b01d45e)

## Prontinho

Bom, você poderia ter parado na criação do novo repositório via template. Mas como somos muito organizados e queremos manter todo nosso trabalho sincronizado no [planner](https://github.com/orgs/automatiza-mg/projects/1) vamos sempre preferir perder 5 minutinhos configurando nossos [actions](#actions-reutilizaveis), certo? 😀😀😀

[^1]: Tente, ao máximo, criar repositórios públicos. Pense sempre se haverá alguma informação sensível e, caso haja, matenha o repositório privado.
[^2]: `git clone <endereco-novo-repositorio>`
[^3]: Máquinas da Cidade Administrativa podem não aceitar endereços `SSH`.
[^4]: Credenciais disponíveis no nosso dataset de [acessos](https://github.com/automatiza-mg/acessos/blob/main/data/acessos.csv). Caso seja solicitado autenticação em dois fatores peça auxílio para algum colega que já acessa este usuário. Para entender melhor porque utilizar este usuário leia o post [Criação de usuário para adminstração geral GitHub]('criação-de-usuário-para-adminstração-geral-github')
[^5]: Orientações também disponíveis [aqui](https://github.com/o-futuro-ja-comecou/github-actions-reutilizaveis?tab=readme-ov-file#adicionar-projeto-em-um-novo-issue).
[^6]: Número do projeto planner é `1`, conforme pode ser observado no final da [url do projeto](https://github.com/orgs/automatiza-mg/projects/1).
