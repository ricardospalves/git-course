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
  * [Opções do `log`](#Opções-do-log)
    * [`--oneline`](#--oneline)
    * [`--graph`](#--graph)
    * [`--decorate`](#--decorate)
    * [`--author`](#--author)
  * [`shortlog`](#shortlog)

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