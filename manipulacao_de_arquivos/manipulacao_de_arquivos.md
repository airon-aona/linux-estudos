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
