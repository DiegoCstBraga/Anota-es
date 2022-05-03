# Command Line 101

[Voltar para o início](./README.md)

## Sumário

1. [Atalhos de teclado](#atalhos-de-teclado)
2. [Comandos de visualização](#comandos-de-visualização)
3. [Comandos de locomoção](#comandos-de-locomoção)
4. [Comandos de criação](#comandos-de-criação)
5. [Comandos de remoção](#comandos-de-remoção)
6. [Metacaracteres](#metacaracteres)
7. [Nano](#nano)
8. [VIM](#vim)

## Adicionando o Git Bash no Windows Terminal

Adicionar executável

```bash
C:\\Program Files\\Git\\bin\\bash.exe
```

Adicionar ícone

```bash
C:\\Program Files\\Git\\mingw64\\share\\git\\git-for-windows.ico
```

[Fonte (em inglês)](https://executecommands.com/add-git-bash-to-windows-terminal-app-profile/)

## Entendendo o Command Line

```mermaid
graph LR
A(Terminal) --> B(Shell)
B --> c(Kernel)
c --> D(Hardware)
```

## Sintaxe

```mermaid
graph LR
a(Command) --> b(Option)
b --> c(Arguments)
```

## Atalhos de teclado

Limpar tela do terminal

```bash
ctrl + L
```

## Comandos de visualização

Visualizar o conteúdo do diretório

```bash
ls
```

- Azul = diretório

- Branco = arquivo
- Vermelho = arquivo compactado
- Verde Água = link

Listar diretório anterior

```bash
ls ..
```

Visualizar o diretório nativo sem se deslocar do diretório corrente

```bash
ls ~
```

Listar no formato longo

```bash
ls -l
```

Listar tudo, até arquivos e diretórios ocultos

```bash
ls -a
```

Lista mostrando o que cada informação é

```bash
ls -F
```

- arquivos simples = sem símbolo
- diretórios = /
- arquivos linkados = @

Lista os arquivos e diretórios por ordem de data de modificação

```bash
ls -t
```

Lista os arquivos e diretórios por linha

```bash
ls -F
```

Ler de maneira "Humana"

```bash
ls -1
```

Ler de maneira recursiva:

```bash
ls -R
```

Listar pelo tamanho

```bash
ls -S
```

Visualizar os arquivos e diretórios em árvore

```bash
tree
```

Visualizar apenas os diretórios em árvore

```bash
tree -d
```

Visualizar o caminho do diretório que se encontra no momento

```bash
pwd
```

Visualizar o conteúdo de um arquivo na tela

```bash
cat caminho/arquivo
```

Visualizar o conteúdo de um arquivo linha por linha

```bash
cat caminho/arquivo | more
```

Visualizar o conteúdo de um arquivo de modo livre (o conteúdo do arquivo não fica printado no terminal)

```bash
less caminho/arquivo
```

Descobrir tipo e informações de um arquivo

```bash
file filename
```

Descobrir dono, modificações e tamanho

```bash
stat filename
```

Encontrar arquivos

```bash
find <path> -type f -name "*.png"
```

Encontrar diretórios

```bash
find <path> -type d -name "desenvolvimento"
```

o *parâmetro* `-iname` faz com que ele procure tanto em maiúsculo quanto minúsculo no `find`

## Comandos de locomoção

Vai para o diretório atual

```bash
cd .
```

Vai para o diretório anterior

```bash
cd ..
```

Muda de diretório de acordo com o Caminho

```bash
cd /caminho
```

Muda para o diretório nativo do usuário

```bash
cd ~
```

Muda para o último diretório acessado

```bash
cd -
```

Para mover um arquivo para outro diretório

```bash
mv caminho_origem caminho_destino
```
  
Para renomear um arquivo ou diretório (*deve-se estar no mesmo diretório do arquivo/diretório que deseja renomear*)

```bash
mv file1.txt arquivo1.txt
```

Mover e renomear um arquivo ou diretório para outro lugar

```bash
mv caminho_origem caminho_destino/novo_nome
```

## Comandos de criação

Criar diretório

```bash
mkdir diretorio
```

Adicionando o *parâmetro* `-p`, você cria vários diretórios de acordo com o caminho

```bash
mkdir -p pasta1/pasta2
```

Para criar vários diretórios de uma só vez, basta adicionar ***espaço*** entre eles

```bash
mkdir pasta2 pasta3
```

Criar arquivos

```bash
touch file1.txt
```

Para criar vários arquivos de uma só vez, basta adicionar ***espaço*** entre eles

```bash

touch file2.txt file3.txt
```

PS: *`touch` também serve para mudar data/hora de criação de arquivo*

Copiar arquivos e pastas

```bash
cp file1.txt nome_dir
```

Para copiar mais de um arquivo ou diretório, basta adicionar o *parâmetro* `-r`

```bash
cp -r file1.txt file2.txt nome_dir
```

Informa se deseja sobrescrever um arquivo com o mesmo nome, caso já exista

```bash
cp -i
```

Faz a cópia sobrescrevendo arquivo com o mesmo nome, sem perguntar ao usuário

```bash
cp -f
```

Ao copiar, se existir um arquivo com o mesmo nome no caminho destino, mantém-se o arquivo antigo com “~” no final dele

```bash
cp -b
```

Criar um arquivo link

```bash
ln -s nome_arquivo_origem nome_link
```

## Comandos de remoção

Remover o diretório se ele estiver vazio e esteja pelo menos um nível acima

```bash
rmdir nome_diretório
```

Remover os diretórios de acordo com o caminho, respeitando a regra anterior

```bash
rmdir -p nome_caminho_diretório
```

Remove todos os arquivos dentro do diretório e o diretório, de forma recursiva e forçada

```bash
rm -rf nome_diretorio
```

Remover arquivo

```bash
rm nome_arquivo_ou_diretório
```

Remover arquivo com interação do usuário

```bash
rm -i nome_arquivo_ou_diretório
```

Excluir vários arquivos sem interagir com o usuário

```bash
rm -rf nome_arquivo
```

## Metacaracteres

- `*` - Representar qualquer quantidade de caracteres
- `?` - Substituir apenar 1 caractere
- `[]` - gerar lista de caracteres (cada colchete substitui 1 caractere na busca)
- `{}` - gerar sequência de caracteres separados por vírgula (avisa se não encontrar, utilizado quando sabe o que está procurando)

## Nano

Entrar no editor

```bash
nano nome_arquivo
```

 Atalhos de teclado

- `ctrl + o` \-> Salvar o arquivo
- `ctrl + x` \-> Sair do editor

## VIM

Entrar no editor

```bash
vi nome_arquivo
```
  
Atalhos de teclado

- `"a" ou "i"` \-> Entrar no modo de inserção
- `"o"` \-> Quebra a linha e ativa o modo de inserção
- `ESC` \-> Sair do modo de escrita
- `:w` \-> Salvar arquivo
- `:wq` \-> Salvar e sair
- `:q!` \-> Sair sem salvar
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkwODY5OTMyNV19
-->