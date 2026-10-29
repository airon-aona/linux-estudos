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

diretório de arquivos temporarios, em algumas distribuições esse diretório é montado em memória.

### /usr


