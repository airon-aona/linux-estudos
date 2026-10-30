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



