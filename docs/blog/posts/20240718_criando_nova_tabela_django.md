---
date: 2024-07-18
authors: [gabrielbdornas]
draft: false
comments: true
categories:
  - DCD
---

# Criando Tabelas Django Admin

Neste encontro discutimos a utilização da ferramenta [django](https://www.djangoproject.com/), mais especificamente como criar uma nova tabela em nosso painel admin. :simple-django: :rocket: :rocket:

<!-- more -->

![type:video](https://www.youtube.com/embed/v9-fW0UfU5Q)

## Criação de Modelos

- Criar o modelo desejado em um novo arquivo `robo_models.py`:

    ```python
    from django.db import models

    class Robo(models.Model):
        nome = models.CharField(max_length=100)
        tempo_execucao = models.IntegerField(null=True)
        # Outros campos
    ```

## Escolha de Campos

- Discussão sobre o campo `tempo_execucao` para armazenar a duração da execução do robô.
- Consideração inicial de `DurationField`, mas decidiu-se por `IntegerField` para simplificação e precisão aceitável.
- Uso de `IntegerField` também garantirá que o valor inserido no formulário seja sempre um número inteiro, pois o mesmo utilizará validação automática de dados,conforme as regras definidas nos modelos.
- [Documentação django de referência](https://docs.djangoproject.com/en/5.0/intro/tutorial02/#creating-models).

    ```python
    tempo_execucao = models.IntegerField(null=True)
    ```

## Migrações

- Criar e aplicar migrações após definir os modelos.

    ```sh
    python manage.py makemigrations
    python manage.py migrate
    ```

## Painel admin

- Registrar o novo modelo no `admin.py` para aparecer na interface administrativa do Django.

    ```python
    from django.contrib import admin
    from .models import Robo

    class RoboAdmin(admin.ModelAdmin):
        pass

    admin.site.register(Robo, RoboAdmin)
    ```

## Testes e Ajustes

- Testar o funcionamento do servidor e verificar se a nova tabela aparece no admin.
    ```sh
    python manage.py runserver
    ```

## Boas Práticas

- Fazer commit das mudanças regularmente para manter o controle de versão.
    ```sh
    git add .
    git commit -m "Criar modelo Robo e registrar no admin"
    ```

## Código referência

Após todos estes pontos discutidos, chegamos [neste código](https://github.com/automatiza-mg/sima/tree/7526b74f8ab3f84bc35b95595c61e86175c44c76).
