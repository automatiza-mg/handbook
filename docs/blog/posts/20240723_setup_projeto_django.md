---
date: 2024-07-23
authors: [gabrielbdornas]
draft: true
comments: true
categories:
  - Ferramentas
---

# 🚀 Como Configurar um Projeto Django: Passo a Passo

Vamos aprender como fazer o setup de um projeto Django. Especificamente, vamos ver como instalar um projeto Django existente em sua máquina para começar a trabalhar.
O [Django](https://www.djangoproject.com/) é um framework Python que nos oferece um painel administrativo robusto, que pode substituir planilhas gigantes e possibilitar a criação de relatórios e dashboards.
No entanto, nosso foco hoje é a instalação e configuração de um projeto já pronto.

<!-- more -->

![type:video](https://www.youtube.com/embed/sKZJpcMSuSs)

## Clonando o Repositório

Primeiro, precisamos clonar o repositório do projeto.
Vamos utilizar como referência o projeto [Sima](https://github.com/automatiza-mg/sima).
No terminal, execute:

```bash
git clone git@github.com:automatiza-mg/sima.git
```

Entre na pasta do projeto:

```bash
cd sima
```

## Criando e Ativando o Ambiente Virtual

Crie um ambiente virtual para isolar as dependências do projeto:

```bash
python3 -m venv venv
```

Ative o ambiente virtual. No Linux ou Mac:

```bash
source venv/bin/activate
```

No Windows:

```bash
source venv/Scripts/activate
```

## Instalando Dependências

Com o ambiente virtual ativado, instale as dependências do projeto listadas no `requirements.txt`:

```bash
pip install -r requirements.txt
```

## Configurando o Banco de Dados

Depois de instalar as dependências, você precisa configurar o banco de dados. Verifique o estado das migrações:

```bash
python manage.py migrate
```

Isso criará as tabelas no banco de dados, que no nosso caso é o SQLite, armazenado em um arquivo chamado `db.sqlite3`.

## Criando o Superusuário

Para acessar o painel administrativo do Django, você precisa criar um superusuário. Execute:

```bash
python manage.py createsuperuser
```

Siga as instruções para definir o username e senha.

## Iniciando o Servidor

Agora, inicie o servidor Django:

```bash
python manage.py runserver
```

Acesse o painel administrativo em [http://127.0.0.1:8000/admin](http://127.0.0.1:8000/admin) e faça login com o superusuário criado.

## Explorando o Painel Administrativo

No painel administrativo, você pode começar a gerenciar dados.
Por exemplo, adicione novos registros como órgãos e projetos diretamente pela interface.

---

Com isso, seu projeto Django estará pronto para ser usado e melhorado. Se você tiver dúvidas, deixe um comentário abaixo!

Dê uma olhadinha também no post que mostra [como criar tabelas em um projeto Django](./20240718_criando_nova_tabela_django.md)

Um abraço e até a próxima! 👋

---
