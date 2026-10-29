# Navegação Linux
---

[Referencia:](https://www.certificacaolinux.com.br/diretorios-e-arquivos/)

## Estrutura de Diretórios - Filesystem Hierarchy Standard FHS

### /

Diretório raiz do sistema de arquivos

### /bin

Contêm comandos utilizados pelo usuário e pelo administrado.

### /boot

Arquivos necessários à carga do sistema. Imagem do Kernel, initramfs e alguns arquivos do Grub. Contém tudo que é necessário para iniciar o sistema, exceto arquivos de configuração e gerenciador de boot. Inclui o setor master de carga (Master Boot Sectors) e arquivos de mapa de setor

### /dev

Abstração do kernel onde ficam arquivos para acesso aos dispositivos do sistema, os arquivos são descritores que facilitam os acessos aos dispositivos. É um pseudo-filesystem, e não existe no disco

### /etc

Arquivos necessários para a configuração do sistema, são necessários para a carga do sistema. Também encontram os arquivos de configuração das interfaces de rede.

Tipicamente possui dois subdiretórios:

- /etc/X11 - Arquivos para configuração da interface gráfica (X Window System)
	
- /etc/skel - Esqueletos da configuração de usuários. Arquivos "modelo" para usuários, que são replicados para o diretório home de cada novo usuário quando criados no sistema.

### /home

Nesse diretório que ficam os diretórios home de cada usuário. Localizam scripts de carga de perfil e do shell bash de cada usuário.

### /lib 

Arquivos de biblioteca essenciais ao sistema, utilizados pelos programas em /bin e módulos Kernel. Comum existir /lib[Arquitetura]. /lib64 e /lib32

### /mnt

Diretório vazio, usado como ponto de montagem de dispositivos na máquina, usado pelo administrador para montar discos.

### /media

Diretório vazio, usado como ponto de montagem de dispositivos na máquina, cdrom, dvd, pendrives, etc.

### /proc

Informações do kernel e dos processos. é um pseudo-filesystem e não existe realmente no disco. Abstrações e descritores de tudo quanto é há no kernel do sistema. É possivel não só ler os dados, mas fazer alterações do kernel, alterando o conteudo do /proc. Seria o "registro" do sistema.

### /opt

Ficam instalados programas que não pertencentes a distribuição linux.

### /root

Diretório do superusuario root, pode ou não existir dependendo da distribuição.

### /run

Armazena dados desde a ultima carga, é zerado ou apagado, no inicio do processo de boot.

### /sbin

Contem arquivos acessados normalmente apenas pelo superusuario, essenciais para a administração da máquina.

### /tmp

Diretório de arquivos temporarios, em algumas distribuições esse diretório é montado em memória.

### /usr

Arquivos pertencentes ao usuário, seu conteúdo pode ser distribuído via rede para diversos sistemas da mesma distribuição sem problemas, é a segunda maior hierarquia de diretórios e tem alguns subdiretórios:

- /usr/bin - Ferramentas e comandos auxiliares do usuário, interpretadores de programação como perl, python, etc.
- /usr/include - Cabeçalhos e bibliotecas da linguagem C.
- /usr/lib e /usr/lib64 - Bibliotecas de aplicações de usuários.
- /usr/libexec - Binarios que não são executados normalmente por usuários.
- /usr/local - Hierarquia de diretórios para instalação de aplicativos locais do sistema. Possui vários subdiretórios como: bin, etc, include, lib, man, sbin, share e src.
- /usr/sbin - Inclui ferramentas não essenciais, mas exclusivas da administração do sistema.
- /usr/share - São arquivos de somente leitura de arquitetura independente, podem ser compartilhados por distribuições de linux iguais, independente da arquitetura. O diretório man por exemplo é onde ficam os manuais dos comandos e fica em /usr/share.
- /usr/src - Pode conter arquivos de código fonte de programa.

### /var

É guardada informações variáveis do sistema, como logs, arquivos de e-mail, etc. Possui subdiretórios importantes:
- /var/cache - Mantém informações de cache das aplicações como calculos, etc.
- /var/lib - Mantém informações de estado das aplicações.
- /var/log - Mantém informações de log do sistema, como messages, lastlog, wtmp.
- /var/mail - Mantém o diretório de contas de e-mail dos usuários.
- /var/opt - Mantém os arquivos variáveis das aplicações.
- /var/spool - Mantém dados de processos que mantém filas, como impressão e saída e-mail.
- /var/tmp - Mantém os arquivos temporários das aplicações que precisam ser mantidos entre o reboot do sistema.
