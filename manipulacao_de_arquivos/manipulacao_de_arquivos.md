# Manipulação de Arquivos

## Comandos

### touch

Este comando é utilizado para atualizar a data e hora do ultimo acesso ou de modificação de um arquivo, caso o arquivo não exista ele irá criar um arquivo vazio.

Opções do comando:

- `-a` - Altera apenas a data do ultimo acesso.
- `-c`, `--no-create` - Não cria qualquer arquivo.
- `-m` - Altera apenas a data de modificação do arquivo.
- `-t [[CC]YY]MMDDhhmm[.ss]` - Define o tempo a ser utilizado ao invés da data e hora atual

`touch teste` - Se o arquivo "teste" não existe o touch vai criar um arquivo teste.

`touch -t 05011231 teste` - Altera a data de modificação e de acesso para as 12:31 do dia 01/05 do ano corrente.

`touch *` - Altera as datas de todos os arquivos do diretório corrente.

- Se o não for especificado qual data a ser atualizada o `touch` atualiza as duas datas do arquivo: acesso e modificação.

### mkdir

Cria diretórios

Algumas opções do comando:

- `-m` ou `--mode` - Define as permissões do diretório.
- `-p` ou `--parents` - Cria hierarquia de diretórios.

`mkdir teste` - Cria o diretório teste dentro do diretório atual.

`mkdir teste/linux` - Cria o diretório teste e dentro dele o subdiretório linux.

### cp

O comando `cp` faz cópias de arquivos e diretórios.

`cp arquivo1 arquivo2` - Copia o arquivo1 para o arquivo2 no mesmo diretório.

`cp arquivo1 /tmp` - Copia o arquivo1 para o diretório /tmp.

`cp /tmp/arquivo1 .` - Copia o arquivo1 localizado no diretório /tmp, para o diretório atual (o ponto significa diretório atual).

Opções do comando `cp`:

- `-r` - Copia arquivos e subdiretórios recursivamente.
- `-b` - Gera cópias de segurança se o arquivo de destino já existir.
- `-f` - Substitui os arquivos existentes sem pedir confirmação.
- `-i` - Pede permissão antes de substituir arquivos existentes.
- `-v` - Lista os arquivos copiados.
- `-d` - Preserva os links ao copiar os arquivos.
- `-p` - Preserva todos os atributos do arquivo, como dono, grupos, permissões e data.
- `-a` - Faz o mesmo que o `-dpR` combinados.

É possível utilizar os curingas, para especificar mais de um arquivo:

- `cp arquivo*.txt /tmp` - O * substitui um grupo qualquer de caracteres, sem especificar qual ou quantos, pode também ser zero, esse comando copia os arquivos do diretório atual que comecem com arquivo e tem extensão txt para o diretório /tmp.
- `cp arquivo?.txt /tmp` - O ? substitui um caractere (Qualquer caractere), esse comando copia os arquivos do diretório atual que comecem com arquivo e tenham qualquer caractere na oitava posição e tenham a extensão txt para o diretório /tmp.
- `cp arquivo[1-3].txt /tmp` - O [] substitui um único caractere em uma faixa de valores, esse comando copia os arquivos arquivo1.txt, arquivo2.txt e arquivo3.txt, se eles existirem, para o diretório /tmp.

### mv

O comando `mv` move os arquivos de um diretório para outro, diferente do `cp`, o `mv` apaga os arquivos da origem após transferi-lo para a origem. O comando `mv` serve também para renomear os arquivos.


