# Navegação Linux

## Estrutura de Diretórios - Filesystem Hierarchy Standard FHS

### /

Diretório raiz do sistema de arquivos

### /bin

Contém comandos utilizados pelo usuário e pelo administrador.

### /boot

Arquivos necessários para a inicialização do sistema, incluindo a imagem do kernel Linux (vmlinuz) e o initramfs. Contém o gerenciador de boot (como o GRUB), seus arquivos de configuração (como o grub.cfg) e os arquivos de mapa de setores necessários para carregar o sistema operacional.

### /dev

Abstração do kernel onde ficam arquivos para acesso aos dispositivos do sistema; os arquivos são descritores que facilitam os acessos aos dispositivos. É um pseudo-filesystem, e não existe no disco

### /etc

Arquivos necessários para a configuração do sistema são necessários para a carga do sistema. Também encontram os arquivos de configuração das interfaces de rede.

Tipicamente possui dois subdiretórios:

- /etc/X11 - Arquivos para configuração da interface gráfica (X Window System)
	
- /etc/skel - Esqueletos da configuração de usuários. Arquivos "modelo" para usuários, que são replicados para o diretório home de cada novo usuário quando criados no sistema.

### /home

Nesse diretório que ficam os diretórios home de cada usuário. Localizam scripts de carga de perfil e do shell bash de cada usuário.

### /lib 

Arquivos de biblioteca essenciais ao sistema, utilizados pelos programas em /bin e módulos do kernel. Comum existir /lib[Arquitetura]. /lib64 e /lib32

### /mnt

Diretório vazio, usado como ponto de montagem de dispositivos na máquina, usado pelo administrador para montar discos.

### /media

Diretório vazio, usado como ponto de montagem de dispositivos na máquina, cdrom, dvd, pendrives, etc.

### /proc

Informações do kernel e dos processos. É um pseudo-filesystem e não existe realmente no disco. Abstrações e descritores de tudo quanto é há no kernel do sistema. É possível não só ler os dados, mas fazer alterações do kernel, alterando o conteúdo do /proc. Seria o "registro" do sistema.

### /opt

Ficam instalados programas que não pertencem à distribuição Linux.

### /root

Diretório do superusuario root, pode ou não existir dependendo da distribuição.

### /run

Armazena dados desde a última carga; é zerado ou apagado no inicio do processo de boot.

### /sbin

Contém arquivos acessados normalmente apenas pelo superusuário, essenciais para a administração da máquina.

### /tmp

Diretório de arquivos temporários, em algumas distribuições esse diretório é montado em memória.

### /usr

Arquivos pertencentes ao usuário, seu conteúdo pode ser distribuído via rede para diversos sistemas da mesma distribuição sem problemas, é a segunda maior hierarquia de diretórios e tem alguns subdiretórios:

- /usr/bin - Ferramentas e comandos auxiliares do usuário, interpretadores de programação como perl, python, etc.
- /usr/include - Cabeçalhos e bibliotecas da linguagem C.
- /usr/lib e /usr/lib64 - Bibliotecas de aplicações de usuários.
- /usr/libexec - Binários que não são executados normalmente por usuários.
- /usr/local - Hierarquia de diretórios para instalação de aplicativos locais do sistema. Possui vários subdiretórios como: bin, etc, include, lib, man, sbin, share e src.
- /usr/sbin - Inclui ferramentas não essenciais, mas exclusivas da administração do sistema.
- /usr/share - São arquivos de somente leitura de arquitetura independente; podem ser compartilhados por distribuições de Linux iguais, independentemente da arquitetura. O diretório man, por exemplo, é onde ficam os manuais dos comandos e fica em /usr/share.
- /usr/src - Pode conter arquivos de código fonte de programas.

### /var

É guardada informações variáveis do sistema, como logs, arquivos de e-mail, etc. Possui subdiretórios importantes:
- /var/cache - Mantém informações de cache das aplicações, como cálculos, etc.
- /var/lib - Mantém informações de estado das aplicações.
- /var/log - Mantém informações de log do sistema, como messages, lastlog, wtmp.
- /var/mail - Mantém o diretório de contas de e-mail dos usuários.
- /var/opt - Mantém os arquivos variáveis das aplicações.
- /var/spool - Mantém dados de processos que mantêm filas, como impressão e saída de e-mail.
- /var/tmp - Mantém os arquivos temporários das aplicações que precisam ser mantidos entre o reboot do sistema.

## Comandos

### pwd

O comando ` pwd ` (Print Working Directory) informa o diretório absoluto corrente e mostra o caminho completo desde a raiz do sistema.
Tem algumas opções:

- ` -L ` ou ` --logical ` - Retorna o conteúdo da variável PWD mesmo se conter links simbólicos.
- ` -P ` ou ` --physical ` - Evita todos os links simbólicos.

O comando pwd sem o ` -L ` o link simbólico é indicado, com a opção ` -P ` o pwd resolve o link simbólico indicando para o diretório original.

### ls

O comando ` ls ` serve para listar arquivos e diretórios em algum lugar do sistema:

- ` ls ` - lista o conteúdo do diretório atual.
- ` ls [caminho] ` - lista o conteúdo do diretório especificado.

O ` ls ` aceita algumas opções:

- ` -l ` - Exibe em formato de lista detalhada, mostra permissões, número de links, tamanho em bytes, dono, grupo, data de modificação e nome.
- ` -a ` - Mostra todos os arquivos, incluindo os arquivos ocultos (arquivos que começam com um ponto, como `.bashrc`).
- ` -h ` - Torna os tamanhos dos arquivos fáceis de ler (KB, MB, GB); é usado junto com o `-l` (`ls -lh`).
- ` -t ` - Ordena os arquivos pela data de modificação, do mais recente ao mais antigo.
- ` -s ` - Ordena os arquivos, pelo tamanho, do maior para o menor.

Pode combinar as opções assim como feito em `ls -lh`, exemplos:

- `ls -la` - Lista todos os arquivos, inclusive os ocultos, em lista detalhada.
- `ls -lah` - Lista todos os arquivos, inclusive os ocultos, em lista detalhada com os tamanhos legíveis.

Podemos também usar opções em um diretório que não é o atual utilizando `ls [opção] [caminho]`.

### cd

O comando ` cd ` (Change Directory) serve para navegar entre os diretórios.

`cd [caminho]`

Temos algumas opções:

- `cd` ou `cd ~/` - Ir para o diretório home.
- `cd /` - Ir para o diretório raiz.
- `cd nome_do_diretorio` - Ir para um diretório filho do atual.
- `cd ..` - Ir para o diretório pai do atual.
- `cd ../nome_do_diretorio` - Ir para um diretório do mesmo nível (irmão) do atual.
- `cd -` - Voltar para o último diretório visitado antes do atual.
- `cd [caminho completo]` - Você pode fornecer o caminho completo do diretório a que quer ir.

---
## Referencias

[Filesystem Hierarchy Standard FHS](https://www.certificacaolinux.com.br/diretorios-e-arquivos/)

[Comando PWD](https://www.certificacaolinux.com.br/comando-linux-pwd/)

[Comando ls](https://guialinux.uniriotec.br/ls/)
