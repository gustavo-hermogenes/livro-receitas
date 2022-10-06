# Dio - Introdução ao Git e ao GitHub

## Comandos Básicos para um bom desempenho no terminal

- \>dir: listar diretórios presentes na pasta local (linux = ls)

- \>cd: navegar (mesmo para linux)

​			\> cd / *: vai para a base do C:/

​			> cd nome_da_pasta: vai para a pasta nome_da_pasta

​			> cd ..: volta um nível de pastas

- \> cls: limpa o terminal (linux = clear – ou utilizar o atalho ctr+L)

- tecla TAB ajuda a completar a linha de comando (= no linux)

- \> mkdir nome_da_pasta: cria uma pasta chamada  nome_da_pasta (= no linux)

- \> echo texto: printa de volta na tela do terminal o texto (= no linux)

- \>  output \> arquivo: pega a saída da função anterior e joga no arquivo selecionado (= no linux)

​	exemplo: echo hello > hello.txt ===== cria um arquivo hello.txt com o texto hello

- \>del: deleta arquivos

​			> del workspace: deleta os arquivo dentro da pasta workspace

- \>rmdir: deleta o diretório (no linux é só rm com a flag rf, que é recursivo para todas as pastas e force para não aparecer mensagens)

​			> rmdir workspace /S /Q: deleta todo o diretório workspace

## Encriptação

### sha1

- sha1 é um algoritmo de encriptação

- \>openssl sha1 arquivo: gera o código de 40 caracteres do arquivo

  

## Objetos no Git

**Blobs, Trees, Commits**

- \>git hash-object --stdin

​			flag: --stdin estou dizendo que estou passando um texto em vez de uma função

O sha do git contém metadados além do conteúdo. Assim, o git trabalha com o tipo do dado (por exemplo blob), o tamanho, \0 e o conteúdo em si.

**Blob** armazena criptrografia de arquivo.

**Tree** se refere a Blobs e mesmo a outras Trees, também armazenando metadados criptografados

**Commit** junta tudo, também armazenando os metadados do projeto como um todo, incluindo autor, mensagem, e data e hora da criação/modificação. 

## Iniciando o Git e Criando um Commit

- \>git init: inicia um repositório Git no local. Uma pasta .git será criada, mas ela não aparece na listagem pois é uma pasta oculta para o Git versionar os códigos.

- \>ls -a: (FLAG) -a é para mostrar arquivos ocultos, e assim o git apareceria na listagem.

Informações sobre o autor do commit no repositório:

- \> git config --global (pode citar global ou apenas para este repositório) user.email “e-mail”

- \> git config --global user.name meunome

**Gerar o commit:**

- \> git add *: pega tudo que está no working directory e passa para staged (ou git add nome_do_arquivo para dar o stage no arquivo)

- \> git commit -m “mensagem”: faz o commit e a flag -m serve para passar uma mensagem do commit atual

- \> git status: verifica o status do commit

- \> mv receita1.md ./receitas/: move o arquivo receita1.md para a pasta receitas/

## Trabalhando com o GitHub

- \> git remote add origin link-do-meu-GitHub: adiciona uma origem remota para o commit o commit em questão. Neste caso, o commit apontaria para um repositório remoto do GitHub.

- \> git remote -v: trás a lista de repositórios remotos cadastratados

- \> git push origin master: carrega o commit para o repositório remoto GitHub

- \> git config --list: lista os dados/configurações do commit, como username e e-mail

- \> git config user --global --unset propriedade_a_ser_alterada (como por exemplo user.email): faz o unset da configuração, daí basta refazer esta configuração

## Conflitos no GitHub e como resolvê-los

- \> git pull origin master: o pull serve para fazer o merge dos commits

- Para conflitos de **MERGE**. No código modificado: 

​	< < < < < < < HEAD

​	modificação que eu fiz

​	========== 

​	(a partir daqui está a outra alteração que gera o conflito)

Deve-se fazer o pull, resolver os conflitos, e depois fazer novamente o push.

## Git clone

- \> git clone url_do_repositório_que_se_deseja_clonar: clona o repositório do GitHub cujo link é url_do_repositório_que_se_deseja_clonar para o diretório local, sendo que o repositório clonado não apenas uma pasta, mas um repositório completo que que carrega os metadados e informações de commit desde o original, como autor, datas e repositórios remotos vinculados.
