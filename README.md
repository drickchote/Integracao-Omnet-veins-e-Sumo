# Integracao-Omnet-veins-e-Sumo
Possíveis integrações do ambiente de Simulação


**Instalação do ambiente:**

Configuração 1:
*   Omnetpp 5.1.1
*   Veins 4.6
*   Sumo 0.30
*   Ubuntu 16

Configuração 2:
*   Omnetpp 5.3
*   Veins 4.7.1
*   Sumo 0.32.0
*   Ubuntu 16 ou 18

**Outra configuração possível: (não testado)**
*   Omnetpp 5.4
*   Veins 5 alpha 1 
*   sumo 1.0.0
*   inet 4
*   Ubuntu 18

**Inet:**

Inet 3.6.4 
Ubuntu 16.04 

**Problemas de Incompatibilidade:**
O inet 3.6.4 não funciona no 18.04
O inet4 não funciona com o veins 4.7, a integração estava em desenvolvimento até a presente data 21/11/2018.
O inet 3.6 não funciona com o ubuntu 18.04 pois o ubuntu não tem o pacote osgearth dentro dele.
o inet 3.99.3 e 4.0 funciona com o ubuntu 18.04 mas tem problemas com o veins 4.7 (Está previsto o acrescimo dessa compatibilidade nas próximas versões do veins), até essa data 16/11/2018 ainda não foi lançada.



**Baixando o omnetpp**
Baixar a versão desejada no site do (omnet)[https://omnetpp.org/download/]
descompactar arquivo na pasta /home/usuario/src (local opcional) 
obs. o caminho não pode ter espaço (nem no seu nome de usuario)

digite os comando:
`sudo apt-get update`

`sudo apt-get install build-essential gcc g++ bison flex perl \ 
python python3 qt5-default libqt5opengl5-dev tcl-dev tk-dev \
libxml2-dev zlib1g-dev default-jre doxygen graphviz libwebkitgtk-1.0`

`sudo add-apt-repository ppa:ubuntugis/ppa`
`sudo apt-get update`
`sudo apt-get install openscenegraph-plugin-osgearth libosgearth-dev`



`cd /home/usuario/src/omnetpp-5.3`

> (substitua "usuario" pelo seu usuario).

`. setenv` 

> adiciona /lib ao PATH de LD_LIBRARY_PATH

`echo "export PATH=$HOME/src/omnetpp-5.3/bin/:\$PATH" | sudo tee /dev/null >> ~/.bashrc `

> Substitua o 5.3 pela sua versão do omnet 

> Você também pode abrir o arquivo ~/.bashrc e colocar o PATH (caminho até a pasta bin do omnetpp) manualmente. Ou ainda dar o comanado export pelo terminal.

`./configure`

> configura o makefile, ao final da configuração você deverá receber a mensagem "Your PATH contains /home/marcos/src/omnetpp-5.*/bin. Good!"

`make`


Digite `omnepp` para testar se funciona, na primeira vez irá aparecer a opção de baixar os exemplos, eu sugiro que você baixe eles.


**Possíveis erros:**

*   "Cannot build Qt apps" (após o ./configure)     significa que o primeiro comando para os pacotes não funcionou.
*   "Warning: your path doesn't contain...": (após o ./configure)    siginifica que o PATH não foi corretamente setado no arquivo ~/.bashrc (comando com o echo)
*   "error: Cannot find OpenSceneGraph 3.2 " (após o ./configure):  o comando sudo apt-get install openscene.. não funcionou
*   Se o caminho até o ./configure tiver espaço dará um erro e não será possíve instalar.
Makefile:54: Makefile.inc: Arquivo ou diretório não encontrado (após o make): o ./configure não foi digitado ainda ou não funcionou.
*   make: *** No rule to make target 'Makefile.inc'.  Pare. (após o make): o ./configure não foi digitado ainda ou não funcionou



**Baixando o veins:**

*   Digite no terminal para baixar os pré requisitos:

`sudo apt-get install build-essential gcc g++ bison flex perl tcl-dev tk-dev blt libxml2-dev zlib1g-dev default-jre doxygen graphviz libwebkitgtk-1.0-0 openmpi-bin libopenmpi-dev libpcap-dev autoconf automake libtool libproj-dev libgdal1-dev libfox-1.6-dev libgdal-dev libxerces-c-dev qt4-dev-tools`

Download do [veins](https://github.com/sommer/veins/releases)

Descompacte a pasta em /home/usuario/src 

> (o caminho não pode ter espaços, inclusive no nome de usuário).

Abra o omnetpp, File > Open Projects From File System. E importe o veins.

**Instalando o Sumo:**

Digite esses comandos:
`sudo add-apt-repository ppa:sumo/stable`   
            
`sudo apt-get update	`	
					
`sudo apt-get install sumo sumo-tools sumo-doc`     

digite `sumo-gui` para testar


Para iniciar com o sumo recomendo o tutorial [hello_summo](https://sumo.dlr.de/wiki/Tutorials/Hello_Sumo) 







