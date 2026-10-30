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

`mv arquivo1 arquivo2` - Renomeia o arquivo1 para arquivo2.

`mv arquivo1 /tmp` - Move o arquivo1 para o diretório  /tmp.

Algumas opções do comando:

- `-f` - Move o arquivo sem pedir confirmação, mesmo que o arquivo já exista um arquivo com o mesmo nome no destino.
- `-i` - Move o arquivo mas pede permissão, caso haja um arquivo no destino com o mesmo nome.

Assim como o comando `cp`, podemos usar os curingas para especificar mais de um arquivo.

### rm

O comando `rm` exclui um arquivo ou diretório de forma permanente.

Algumas das opções do comando:

- `-f` - Apaga arquivos ou diretórios a força, sem pedir permissão e ignorando, arquivos e diretórios inexistentes.
- `-i` - Pergunta se você deseja apagar os arquivos e diretórios antes de apaga-los.
- `-r` - Exclui diretórios e todo o conteúdo dentro deles (recursivo).
- `-d` - Remove diretórios que estejam vazios.

`rm arquivo.txt` - Apaga o arquivo.txt.
`rm -fr teste` - Apaga o diretório teste e todo seu conteúdo, sem pedir permissão.

Assim como os comandos anteriores também pode usar os curingas para especificar mais de um arquivo.

### cat

O comando cat (de concatenate) é usado para exibir, criar e concatenar o conteúdo de arquivos de texto.

`cat arquivo1 arquivo2` - Mostra na tela o conteúdo do arquivo1 e arquivo2.

Para marar a rolagem do conteúdo na tela e permitir a navegação use o comando `more` ou `less` junto com o pipe ("|").

`cat arquivo1 arquivo2 | more` ou `cat arquivo1 arquivo2 | less`

Para concatenar vários arquivos temos que usar o redirecionador de saída ">".

`cat arq1 arq2 arq3 > arquivo_concatenado` - Junta o arq1, arq2 e arq3 e cria o arquivo_concatenado, se já existe um arquivo com esse nome, esse arquivo é deletado e criado novamente.

Para inserir um arquivo no final de um arquivo existente utiliza o redirecionador de saída ">>".

`cat arq4 >> arquivo_concatenado` - Adiciona o arquivo arq4 no final de arquivo_concatenado.

É possível usar o redirecionador de saída ">" para criar um arquivo.

`cat > teste` - Cria o arquivo teste, após isso, basta digitar as linhas do arquivo (tecle ENTER no final das linhas e CRTRL + D no final do arquivo).

Para numerar as linhas dos arquivo basta usar o parâmetro `n`.

`cat -n arquivo1.txt` - Exibe o numero e o conteúdo de cada linha do arquivo.

### less

Permite fazer a paginação de arquivos ou da entrada padrão.

Diferente dos editores pesados ou do comando `cat`, o `less` não precisa carregar o arquivo inteiro na memória antes de abrir, ideal para arquivos grandes como logs do sistema.

Pode ser usado para redirecionar a saída de um comando usando o pipe ("|").

`ls | less` - Faz com que a saída do diretório corrente seja paginada pelo aplicativo less.

Algumas opções para esse comando.

- `+` - Se a opção começa com esse sinal, então a opção é usada como um comando inicial para o aplicativo less
- `+num` - Mostra o arquivo a partir da linha num.
- `-N` - Numera as linhas do arquivo.
- `-f` ou `--force` - Força a abertura de um arquivo não regular.
- `+F` - Continua indefinidamente tentando ler caracteres no final de um arquivo, assume que o arquivo esta crescendo. O comportamento é semelhante ao comando `tail -f`.
- `+G` - Posiciona no final do arquivo.

### head

Serve para exibir as primeiras linhas de um arquivo de texto, ou de um comando no terminal.

Algumas opções do comando `head`:

- `-c[num[bkm]]` - Mostra os num primeiros bytes, Kbytes ou Mbytes do arquivo, o padrão é bytes.
- `-n[num]` - Mostra as num primeiras linhas do arquivo, o padrão é 10.
- `-v` - Mostra cabeçalho sobre o arquivo.

`head -c 200 teste.txt` - Mostra os primeiros 200 bytes do arquivo.

`head -n 20 teste.txt` - Mostra as primeiras 20 linhas do arquivo.

### tail

Ao contrario do `head`, o `tail` mostra as ultimas linhas do arquivo, pode ser util para monitoramento de logs e depuração.

- `-c[num[bkm]]` - Mostra os numultimos bytes, Kbytes ou Mbytes do arquivo, o padrão é bytes.
- `-n[num]` - Mostra as num ultimas linhas do arquivo, o padrão é 10.
- `-f` - Continua indefinidamente tentando ler caracteres no final de um arquivo, assumindo que o arquivo esta crescendo.

`tail -n 20 teste.txt` - Mostra as ultimas 20 linhas do arquivo teste.txt.

`tail -f /var/log/syslog` - Examina um arquivo que esta constantemente sendo atualizado, para sair basta usar CTRL + C.

## Curingas


