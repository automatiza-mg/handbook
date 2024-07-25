---
date: 2024-07-25
authors: [gabrielbdornas]
draft: false
comments: true
categories:
  - Git
---

# Como modificar um commit

Às vezes, depois de fazer um commit, você percebe que cometeu um erro na mensagem ou que a mensagem não está clara o suficiente. Felizmente, o Git fornece maneiras de corrigir isso. Vamos explorar duas maneiras de modificar mensagens de commit: usando `git commit --amend` para o último commit e `git rebase -i` para commits anteriores.

<!-- more -->

![type:video](https://www.youtube.com/embed/)

## Modificando a mensagem do último commit

Se você precisa alterar a mensagem do commit mais recente, o comando `git commit --amend` é a ferramenta certa. Aqui está como você pode fazer isso:

- Abra o terminal e navegue até o seu repositório Git.
- Execute o comando `git commit --amend`.

```sh
git commit --amend
```

- O editor padrão será aberto com a mensagem do último commit. Edite a mensagem conforme necessário.
- Salve e feche o editor para aplicar a nova mensagem.

## Exemplo `git commit --amend`

Suponha que você fez um commit com a seguinte mensagem:

```sh
git commit -m "Corrigindo bug no login"
```

Mas você queria incluir mais detalhes na mensagem. Para modificar, você faria:

```sh
git commit --amend
```

O editor padrão abrirá com:

```
Corrigindo bug no login
```

Você pode editar para:

```
Corrigindo bug no login que ocorria ao inserir senha incorreta
```

Depois de salvar e fechar o editor, a mensagem do commit será atualizada.

## Modificando a mensagem de commits anteriores

Para alterar a mensagem de commits que não sejam o mais recente, você pode usar `git rebase -i`. Este comando permite reescrever o histórico de commits de maneira interativa.

- Execute o comando `git rebase -i HEAD~n`, onde `n` é o número de commits que você deseja revisar.

```sh
git rebase -i HEAD~3
```

- O editor padrão será aberto com uma lista de commits recentes. Cada linha começará com a palavra `pick` seguida pelo hash do commit e a mensagem do commit.

```
pick e6f1bde Corrigindo bug no login
pick a3c6f8e Adicionando testes unitários
pick f7c3a4d Atualizando README
```

- Mude `pick` para `reword` para o commit cuja mensagem você deseja modificar.

```
reword e6f1bde Corrigindo bug no login
pick a3c6f8e Adicionando testes unitários
pick f7c3a4d Atualizando README
```

- Salve e feche o editor. Outro editor abrirá para cada commit selecionado para permitir que você altere a mensagem do commit selecionado. Faça as alterações necessárias, salve e feche o editor.

## Exemplo `git rebase -i`

Suponha que você quer modificar a mensagem do segundo commit na lista acima. Após alterar `pick` para `reword`, o editor abrirá novamente com a mensagem original do commit:

```
Corrigindo bug no login
```

Você pode alterar para:

```
Corrigindo bug no login que ocorria ao inserir senha incorreta
```

Depois de salvar e fechar o editor, a rebase continuará aplicando os commits subsequentes, preservando suas alterações.

## Cuidado ao modificar commits enviados ao GitHub (`git push`)

Modificar a mensagem de commits que já foram enviados ao GitHub pode causar problemas. Quando você altera a mensagem de um commit, o Git cria um novo commit com um novo hash. Se esse commit já foi enviado para um repositório remoto e compartilhado com outros colaboradores, isso pode resultar em um histórico de commits divergente.

Por exemplo, se você usar `git commit --amend` ou `git rebase -i` e depois fizer um `git push --force` para enviar as alterações ao GitHub, os outros colaboradores terão um histórico de commits diferente do seu. Isso pode causar confusão e conflitos, tornando a colaboração mais difícil.

Portanto, é recomendável evitar a modificação de commits que já foram compartilhados com outras pessoas. Se você realmente precisa alterar a mensagem de um commit já enviado, comunique-se com sua equipe e certifique-se de que todos estejam cientes das mudanças. Além disso, use `git push --force` com cuidado e apenas se for absolutamente necessário.

## Conclusão

Modificar a mensagem de um commit no Git é um processo simples, mas poderoso. O uso de `git commit --amend` permite corrigir rapidamente o último commit, enquanto `git rebase -i` oferece a flexibilidade de editar mensagens de commits anteriores. Esses comandos são ferramentas valiosas para manter um histórico de commits limpo e significativo.

## Referências

- [How to modify existing, unpushed commit messages?](https://stackoverflow.com/questions/179123/how-to-modify-existing-unpushed-commit-messages)
