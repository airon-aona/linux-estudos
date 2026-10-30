# Processamento de texto

## Comandos

### grep

O comando `grep` é utilizado para buscar por padrões, palavras ou expressões regulares em arquivos de texto ou fluxo de dados.

`grep 'teste de' arquivo.txt` - Procura "teste de" dentro de arquivo.txt.

`grep ^# arquivo.txt` - Procura apenas as linhas que são iniciadas com "#".

`grep false$ arquivo.txt` - Procura linhas que terminam com a palavra false.

`grep ^s arquivo.txt | grep false$ arquivo.txt` - Para ver apenas linhas que começam com caractere "s" e terminam com "false"

`grep 'projeto.lin' arquivo.txt` - Um ponto em um padrão, representa qualquer caractere.

`grep 'projeto\.lin' arquivo.txt` - A barra invertida tira qualquer significado que um caractere possa ter.

O comando `grep` pode ter algumas opções:

- `-a` ou `--text` - Trata arquivos binários como se fossem arquivos de texto.
- `-c` - Imprime somente a contagem das linhas com a expressão.
- `-e padrao` - Define qual padrão deve ser procurado, é usado quando apenas quando a pesquisa possui mais de um padrão.
- `-i` - Ignora a diferença de maiúsculas e minúsculas.
- `-l` - Exibe o nome do arquivo ao invés da saída normal do comando `grep`.
- `-n` - Mostra o numero de cada linha em arquivo com expressão.
- `-s` ou `--no-messages` - Não exibe mensagens de erro.
- `-v` - Mostra todas as linhas de arquivo, exceto as linhas com expressão.

`grep -v ^# arquivo.txt` - Ver apenas as linhas que não iniciam com "#".

`grep -n ^$ arquivo.txt` - A expressão "^$" indica linhas vazias, e a opção `-n` retorna o numero da linha da ocorrência.

`greo -e ^DESCRIPTION$ -e all arquivo.txt` - Pode usar o apção `-e` para definir mais de um padrão, nesse exemplo procura uma linha que só tenha DESCRIPTION e a string "all" em qualquer posição.

### find

O comando `find` busca um arquivo ou diretório no sistema de arquivos, dependendo do tamanho do sistema de arquivos, esse comando pode demorar.

Você deve indicar um ponde de inicio, "/", para iniciar no diretório raiz, "./" para iniciar no diretório corrente, e assim por diante.

Sintaxe básica `find [caminho] [expressão]`

O `find` permite uma infinidade de expressões.

`find / -name teste.txt -type f` - Procura pelo arquivo teste.txt a partir do diretório raiz (indicado pelo "/"), do tipo arquivo (indicado pelo "f").

`find . -name '*.txt'` - Procura todos os arquivos com extenção .txt no diretório atual.

`find . -iname usuarios -type d` - Procura por diretórios com o nome usuarios independente se esta escrito com maiusculas ou minusculas, a partir do diretório atual.

`find -type f -not -name '*.html'` - Procura por arquivos que não terminam com .html a partir do diretório atual.

O `find` permite executar comandos com a lista de arquivos que ele encontrar:

`find . -type f -name '*.mp3' -exec cp {} /tmp/ \` - Copia todos os arquivos com extensão .mp3, a partir do diretório atual, para o diretório /tmp.

`find . -type d -name BACKUP -exec rm -r {} \` - Apaga todos os diretórios BACKUP a a partir do diretório corrente.

`find . -mtime -7 -type f` - Procura os arquivos modificados nos últimos 7 dias.

`find . -mtime +5` - Procura arquivos editados antes de 5 dias.

`find /backup/ -type f -mtime +15 -exec rm -f {} \` - Apaga os arquivos de /backup com mais de 15 dias.

`find -newer arquivo.txt` - Procura por aquivos mais novos que arquivo.txt.

`find / -size +50M` - Procura por arquivos com tamanho maior que 50mb.

### wc

O comando `wc` conta linha, palavras, bytes, caracteres de um arquivo.

Algumas opções são:

- `-c` - Conta bytes.
- `-l` - Conta linhas.
- `-L` - Mostra o comprimento da linha mais longa
- `-m` - Conta caracteres.
- `-w` - Conta palavras.

Como exemplo vamos pegar o arquivo "exemplo" com o seguinte conteúdo:

```
linha 1

linhá 2

o fim
```

`wc exemplo` retorna a seguinte resposta `5 6 25 exemplo` - O arquivo exemplo tem 5 linhas, 6 palavras (2 por linha não vazia) 25 bytes (quantidade de bytes por linha: 8, 1, 9, 1 e 6), note que é contado o byte de fim de linha (\0), e o caractere "á", da terceira linha, tem 2 bytes, isso pode ser verificado com o comando `wc -m exemplo` que vai mostra que o arquivo exemplo tem 24 caracteres.

- Caso não seja fornecido uma opção, como vimos logo a cima, o `wc` informa o numero de linhas, de palavras e de bytes do arquivo especificado.
- Caso não seja informado um arquivo o `wc` permite que o usuário digite as linhas de entrada padrão, separando as linhas com ENTER e o fim do arquivo com CTRL + D, e em seguida faz a contagem.






