# Curso de Git e Github para iniciantes

Curso **[Git e Github para iniciantes](https://www.udemy.com/git-e-github-para-iniciantes/)** grátis do [Willian Justen de Vasconcelos](https://github.com/willianjusten) na plataforma [Udemy](https://www.udemy.com)

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

## Iniciando um repositório

Pirmeiro é preciso entrar na pasta do seu projeto. O comando `cd` diz para entrar na pasta desejada. Por exemplo, para entrar na pasta *git-course* é preciso usar o comando:

```
cd git-course/
```

Agora dentro da pasta do projeto, para iniciar um repositório *git* deve-se usar o comando:

```git
git init
```

Se tudo estiver certo aparecerá uma mensagem semelhante a essa:

```git
Initialized empty Git repository in /aqui/sera/o/seu/diretorio/.git/
```

## Ciclo de vida dos status dos arquivos

Ciclo de vida dos status dos arquivos são:

* [![Cor vermelha](https://placehold.it/16/F44336?text=+) Untracked](#-untracked)
* [![Cor verde](https://placehold.it/16/4CAF50?text=+) Unmodified](#-unmodified)
* [![Cor amarela](https://placehold.it/16/FFEB3B?text=+) Modified](#-modified)
* [![Cor azul](https://placehold.it/16/2196F3?text=+) Staged](#-staged)

### ![Cor vermelha](https://placehold.it/16/F44336?text=+) Untracked

Arquivos ![Cor vermelha](https://placehold.it/16/F44336?text=+) *UNTRACKED* são aqueles que não estão sendo monitorados pelo *git*. Todo arquivo que acaba de ser adicionado ao projeto estará nesse estado. Para que esses arquivos possam ser vistos pelo *git* é preciso adicioná-los ao repositório através do comando `git add <seuarquivo>`. Quando arquivos ![Cor vermelha](https://placehold.it/16/F44336?text=+) *UNTRACKED* são adicionados ao repositório (`git add <seuarquivo>`), eles vão direto para o estado ![Cor azul](https://placehold.it/16/2196F3?text=+) *STAGED*.

### ![Cor verde](https://placehold.it/16/4CAF50?text=+) Unmodified

Arquivos ![Cor verde](https://placehold.it/16/4CAF50?text=+) *UNMODIFIED* são aqueles que já fazem parte do repositórios e que não foram modificados, isso significa que este arquivo é a versão mais atualizada.

Quando um arquivo é *comitado*, ele sai do estado de ![Cor azul](https://placehold.it/16/2196F3?text=+) *STAGED* para o estado ![Cor verde](https://placehold.it/16/4CAF50?text=+) *UNMODIFIED*.

### ![Cor amarela](https://placehold.it/16/FFEB3B?text=+) Modified

Arquivos ![Cor amarela](https://placehold.it/16/FFEB3B?text=+) *MODIFIED* são aqueles que já fazem parte do repositório, porém que foram modificados/alterados desde o último commit.

Quando um arquivo está no estado ![Cor verde](https://placehold.it/16/4CAF50?text=+) *UNMODIFIED* ou ![Cor azul](https://placehold.it/16/2196F3?text=+) *STAGED* e sofre alguma modificação, ele volta ao estado ![Cor amarela](https://placehold.it/16/FFEB3B?text=+) *MODIFIED*.

### ![Cor azul](https://placehold.it/16/2196F3?text=+) Staged

Arquivos ![Cor azul](https://placehold.it/16/2196F3?text=+) *STAGED* são aqueles que estão prontos para serem *comitados*. Quando arquivos ![Cor azul](https://placehold.it/16/2196F3?text=+) *STAGED* são *comitados*, eles mudam para o estado ![Cor verde](https://placehold.it/16/4CAF50?text=+) *UNMODIFIED*.