# Curso de Git e Github para iniciantes

Curso **[Git e Github para iniciantes](https://www.udemy.com/git-e-github-para-iniciantes/)** grátis do [Willian Justen de Vasconcelos](https://github.com/willianjusten) na plataforma [Udemy](https://www.udemy.com).

**Aqui ficarão apenas os conceitos e comandos básicos do git**.

## Menu de navegação

* [Configurações iniciais](#configurações-iniciais)
  * [Definindo valores](#definindo-valores)
  * [Pegando valores](#pegando-valores)
* [Iniciando um repositório](#iniciando-um-repositório)
* [Ciclo de vida dos status dos arquivos](#ciclo-de-vida-dos-status-dos-arquivos)
  * [Untracked](#-untracked)
  * [Unmodified](#-unmodified)
  * [Modified](#-modified)
  * [Staged](#-staged)
* [Visualizando logs](#visualizando-logs)
  * [Opções do `log`](#opções-do-log)
    * [`--oneline`](#--oneline)
    * [`--graph`](#--graph)
    * [`--decorate`](#--decorate)
    * [`--author`](#--author)
  * [`shortlog`](#shortlog)
* [Visualizando as mudanças](#visualizando-as-mudanças)

## Configurações iniciais

### Definindo valores

Definindo o nome de usuário:

```git
git config --global user.name "Seu nome"
```

Definindo o e-mail do usuário:

```git
git config --global user.email "seuemail@aqui.com"
```

Definindo o editor de texto principal:

```git
git config --global core.editor vim
```

### Pegando valores

Pegando o nome de usuário:

```git
git config user.name
```

Pegando o e-mail do usuário:

```git
git config user.email
```

Pegando o tudo:

```git
git config --list
```

***

## Iniciando um repositório

Pirmeiro é preciso entrar na pasta do seu projeto. O comando `cd` diz para entrar na pasta desejada. Por exemplo, para entrar na pasta *git-course* é preciso usar o comando:

```
cd git-course/
```

Agora dentro da pasta do projeto, para iniciar um repositório git deve-se usar o comando:

```git
git init
```

Se tudo estiver certo aparecerá uma mensagem semelhante a essa:

```git
Initialized empty Git repository in /aqui/sera/o/seu/diretorio/.git/
```

***

## Ciclo de vida dos status dos arquivos

### ![Cor vermelha](https://placehold.it/16/F44336?text=+) Untracked

Arquivos ![Cor vermelha](https://placehold.it/16/F44336?text=+) *UNTRACKED* são aqueles que não estão sendo monitorados pelo git. Todo arquivo que acaba de ser adicionado ao projeto estará nesse estado. Para que esses arquivos possam ser vistos pelo git é preciso adicioná-los ao repositório através do comando `git add <seuarquivo>`. Quando arquivos ![Cor vermelha](https://placehold.it/16/F44336?text=+) *UNTRACKED* são adicionados ao repositório (`git add <seuarquivo>`), eles vão direto para o estado ![Cor azul](https://placehold.it/16/2196F3?text=+) *STAGED*.

### ![Cor verde](https://placehold.it/16/4CAF50?text=+) Unmodified

Arquivos ![Cor verde](https://placehold.it/16/4CAF50?text=+) *UNMODIFIED* são aqueles que já fazem parte do repositórios e que não foram modificados, isso significa que este arquivo é a versão mais atualizada.

Quando um arquivo é *comitado*, ele sai do estado de ![Cor azul](https://placehold.it/16/2196F3?text=+) *STAGED* para o estado ![Cor verde](https://placehold.it/16/4CAF50?text=+) *UNMODIFIED*.

### ![Cor amarela](https://placehold.it/16/FFEB3B?text=+) Modified

Arquivos ![Cor amarela](https://placehold.it/16/FFEB3B?text=+) *MODIFIED* são aqueles que já fazem parte do repositório, porém que foram modificados/alterados desde o último commit.

Quando um arquivo está no estado ![Cor verde](https://placehold.it/16/4CAF50?text=+) *UNMODIFIED* ou ![Cor azul](https://placehold.it/16/2196F3?text=+) *STAGED* e sofre alguma modificação, ele volta ao estado ![Cor amarela](https://placehold.it/16/FFEB3B?text=+) *MODIFIED*.

### ![Cor azul](https://placehold.it/16/2196F3?text=+) Staged

Arquivos ![Cor azul](https://placehold.it/16/2196F3?text=+) *STAGED* são aqueles que estão prontos para serem *comitados*. Quando arquivos ![Cor azul](https://placehold.it/16/2196F3?text=+) *STAGED* são *comitados*, eles mudam para o estado ![Cor verde](https://placehold.it/16/4CAF50?text=+) *UNMODIFIED*.

***

## Visualizando logs

Para vizualisar os logs do git o comando é:

```git
git log
```

Esse comando irá retornar a *hash* do commit, o autor e e-mail do autor, a data e a mensage, como no exemplo abaixo:

```git
commit 569855f552221a545455454e454545454b5454a5
Author: Maria <maria@gmail.com>
Date:   Mon Jan 1 00:00:00 2018 -0300

     Add README.md

commit 89855d8544454c656566565f652212121e555e23
Author: Ricardo <ricardo@alves.aqui>
Date:   Fri Sep 1 10:13:26 2017 -0300

     First commit

```

### Opções do `log`

#### `--oneline`

Usando a opção `--oneline`, os commits são exibidos 1 em cada linha.

```git
git log --oneline
```

Com a opção `--oneline` apenas os o começo da hash e o comentário do commit são retornados, como no exemplo abaixo:

```git
569855f Add README.md
89855d8 First commit
```

#### `--graph`

A opção `--graph` mostra de forma gráfica os commits:

```git
git log --graph
```

O resultado será:

```git
* commit 569855f552221a545455454e454545454b5454a5 (HEAD -> master, origin/master)
| Author: Maria <maria@gmail.com>
| Date:   Mon Jan 1 00:00:00 2018 -0300
|
|     Add README.md
|
* commit 89855d8544454c656566565f652212121e555e23
| Author: Ricardo <ricardo@alves.aqui>
| Date:   Fri Sep 1 10:13:26 2017 -0300
|
|     First commit
|
```

#### `--decorate`

A opção `--decorate` mostra o branch do commit, se houve um merge e etc.

```git
git log --decorate
```

O resutado será parecido com:

```git
commit 569855f552221a545455454e454545454b5454a5 (HEAD -> master)
Author: Maria <maria@gmail.com>
Date: Mon Jan 1 00:00:00 2018 -0300

	Add README.md

commit 89855d8544454c656566565f652212121e555e23
Author: Ricardo <ricardo@alves.aqui>
Date: Fri Sep 1 10:13:26 2017 -0300

	First commit
```

#### `--author`

A opção `--author` filtra os commits pelos autores. Não é preciso colocar o nome complete do autor, apenas parte do nome já resolve:

```git
git log --author="Ric"
```

O resultado será:

```git
commit 89855d8544454c656566565f652212121e555e23
Author: Ricardo <ricardo@alves.aqui>
Date: Fri Sep 1 10:13:26 2017 -0300

	First commit
```

### `shortlog`

O comando `shortlog` exibe um log, em ordem alfabética, como o autor, o número de commits e quais forão esses commits.

```git
git shortlog
```

O resutado será:

```git
João (5):
	Add README.md
	First commit
```

Usando ainda a opção `-sn` junto com o `shortlog`, será exibido apenas o número de commits e o autor:

```git
git shortlog -sn
```

O resultado será:

```git
555 Maria 
25 João da Silva
```

***

## Visualizando as mudanças

É possível ver quais foram as mudanças nos arquivos antes de fazer um commit com o comando `diff`:

```git
git diff
```

O resultado será semelhante a:

```git
diff --git a/README.md b/README.md
index b3aa29e..21d521b 100644
--- a/README.md
+++ b/README.md
@@ -3,3 +3,6 @@
 Parte não modificada

 Parte não modificada
+ Sua mudança aqui
+ Sua mudança aqui
+ Sua mudança aqui
```

É possível também saber somente o nome do arquivo que foi modificado através da opção `--name-only`:

```git
git diff --name-only
```

O resultado será semelhante a:

```git
README.md
```

***

## Branch

Branch é um ponteiro móvel que leva a um commit.

### Listando os branches

O comando para listar os branches é:

```git
git branch
```

E o resultado será semelhante a este:

```git
* master
  outra-branch
  mais-uma-branch
```

O branch que você está no momento indicado pelo asterisco (\*).

### Criando uma nova branch

Para criar uma nova branch o comando é:

```git
git checkout <nome-da-branch>
```

Executando o comando acima, a branch é criada mas nada é retornado. Além disso, você continuará na mesma branch. Para criar uma nova branch e ir para ela o comando é:

```git
git checkout -b <nome-da-branch>
```

E será retornado.

```git
Switched to a new branch '<nome-da-branch>'
```

### Navegando pelas branches

Para navegar entre as branches o comando é exatamente igual para criar uma nova branch. Caso a branch exista, você será movido para ela, senão, uma nova branch será criada.

```git
git checkout <nome-da-branch>
```

E será retornado:

```git
Switched to a new branch '<nome-da-branch>'
```

### Deletando uma branch

Para deletar uma branch o comando é:

```git
git branch -D <nome-da-branch>
```

E será retornado algo semelhante a:

```git
Deleted branch <nome-da-branch> (was f6d1862).
```

É possível também apagar múltiplas branches, basta separar cada branch que deseja deletar com espaço:

```git
git branch -D <branch-1> <branch-2>
```

É importante lembrar que só se pode apagar branches em que você não está no momento. Por exemplo, se você estiver na branch **teste**, você só consegue apagar as outras branches. Para apagar a branch **teste**, você precisa primeiro ir para outra branch e de lá apagá-la.