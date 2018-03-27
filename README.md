# Curso de Git e Github para iniciantes

Curso **[Git e Github para iniciantes](https://www.udemy.com/git-e-github-para-iniciantes/)** grátis do [Willian Justen de Vasconcelos](https://github.com/willianjusten) na plataforma [Udemy](https://www.udemy.com)

## Configurações iniciais


### Definindo valores

Definindo o nome de usuário:

´´´git
git config --global user.name "Seu nome"
´´´

Definindo o e-mail do usuário:

´´´git
git config --global user.email "seuemail@aqui.com"
´´´

Definindo o editor de texto principal:

´´´git
git config --global core.editor vim
´´´

### Pegando valores

Pegando o nome de usuário:

´´´git
git config user.name
´´´

Pegando o e-mail do usuário:

´´´git
git config user.email
´´´

Pegando o tudo:

´´´git
git config --list
´´´

## Iniciando um repositório

Pirmeiro é preciso entrar na pasta do seu projeto. O comando ´cd´ diz para entrar na pasta desejada. Por exemplo, para entrar na pasta *git-course* é preciso usar o comando:

´´´
cd git-course/
´´´

Agora dentro da pasta do projeto, para iniciar um repositório *git* deve-se usar o comando:

´´´git
git init
´´´

Se tudo estiver certo aparecerá uma mensagem semelhante a essa:

´´´git
Initialized empty Git repository in /aqui/sera/o/seu/diretorio/.git/
´´´
