## _IDE_ Arduino/ESP8266 no _GNU_/Linux 

Este pequeno tutorial descreve os passos necessários para configuração e instalação do ambiente de desenvolvimento _Arduino_
em sistemas operacionais _GNU_/Linux. Permitindo o uso da _IDE_ do Arduino na codificação e gravação direta das placas que possuam o _ESP8266_.

***
######Os passos consistem em:
* Instalar o _JAVA_.
* Descarregar e instalar a _IDE_ do Arduino.
* Configurar permissões e grupos.(nada complicado!)
* Cofigurar a _IDE_ do Arduino para trabalhar com o _ESP_.

---

```
Todos os procedimentos efetuados neste tutorial foram executados em uma distribuição GNU/Linux
Xubuntu 16.04.1 LTS
```

######Instalando o _JAVA_

* Adicione repositório da _ORACLE_
```
Linux terminal:~$ sudo add-repository ppa:webupd8team/java
```
* Atualize a base
```
Linux terminal:~$ sudo apt-get update
```
* Instale o Java
```
Linux terminal:~$ sudo apt-get install oracle-java8-installer
```
---

######Descarregar e instalar a _IDE_ do Arduino

[Link para arquiteturas de 32 bits](https://www.arduino.cc/download.php?f=/arduino-nightly-linux32.tar.xz)

[Link para arquiteturas de 64 bits](https://www.arduino.cc/download.php?f=/arduino-nightly-linux64.tar.xz)

Novamente no terminal

* Acesse seu diretório de downloads
```
Linux terminal:~$ cd ~/Downloads/
```
* Descompacte o arquivo
```
Linux terminal:~$ tar -xvf arduino*.tar.gz
```
* Para uso global mova o diretório resultante da descompactação para /opt/
```
Linux terminal:~$ sudo mv arduino* /opt
```
* Acesse o diretório /opt/arduino*/
```
Linux terminal:~$ cd /opt/arduino*/
```
* Adicione permissão de execução para o script de instalação
```
Linux terminal:~$ chmod +x install.sh
```
* Finalmente execute o script
```
Linux terminal:~$ ./install.sh
```
---

######Configurar permissões e grupos.(nada complicado)

>Ao longo da instalação será adicionado um atalho na área de trabalho, que será ulitizado para "chamar" o arquivo executável. Caso o processo de instalação tenha sido executado pelo super usuário através do comando "sudo", o atalho não poderá ser    executado por um usuário não "root", dessa forma teremos que mudar as permissões de execução de tal arquivo, da seguinte forma:

* Acessar a área de trabalho:
```
Linux terminal:~$ cd ~/Área\ de\ Trabalho/
```
* Alterar as permissões do atalho:
```
Linux terminal:~$ sudo chmod 755 arduino*.desktop
```

>Quase concluído, a sua IDE do Arduino já está instalada, só que para ter acesso a algumas configurações, como escolha da porta para comunicação com as placas, seu usuário terá que fazer parte dos seguintes grupos: "dialout" e "tty".

* Adicionar o seu usuário ao grupo "tty":
```
Linux terminal:~$ sudo usermod -a -G tty nomeDoSeuUsuario
``` 
* Adicionar o seu usuário ao grupo "dialout":
```
Linux terminal:~$ sudo usermod -a -G dialout nomeDoSeuUsuario
```
---

######Cofigurar a _IDE_ do Arduino para trabalhar com o _ESP_.

>Concluído a etapa anterior agora vamos adicionar uma URL no gerenciador de placas da IDE Arduino, para que ela possa descarregar as bibliotecas necessárias para podermos programar diretamente no ESP.

* Na IDE Arduino no menu
  * Arquivo->Preferências, ou simplesmente digite: Ctrl+,(tecla control mais vírgula).
  * Em Preferências no campo URLs Adicionais de Gerenciadores de Placas, _cole_ o link:
    http://arduino.esp8266.com/stable/package_esp8266com_index.json
  * Clique em OK.

* Vá agora ao menu Ferramentas->Placas e no menu suspenso selecione
   * Gerenciador de Placas...

* No campo Refine sua busca... Digite: ESP

* Selecione a opção onde aparece as bibliotecas esp8266 by ESP8266 Community, escolha versão mais recente e clique em instalar.

>Pronto! Sua Arduino IDE está pronta para programar seus módulos ESPs diretamente se você navegar pelo menu Ferramentas->Placa: -> , abaixo no menu suspenso estará listado diversos modelos de placas com ESP embarcado. Após selecionar alguma placa que contenha ESP, no menu Arquivo->Exemplos também será listado diversos exemplos de aplicações compatíveis com o módulo selionado.

----

*Referências*

[Instalando o _JAVA Oracle_](http://www.webupd8.org/2012/09/install-oracle-java-8-in-ubuntu-via-ppa.html)

[Instalando _IDE_ do Arduino no Ubuntu](http://ubuntuhandbook.org/index.php/2015/11/install-arduino-ide-1-6-6-ubuntu/)

[Bibliotecas, exemplos, documentação e afins](https://github.com/esp8266/Arduino)

[Resolução de problemas _IDE_ do Arduino](https://www.arduino.cc/en/Guide/Troubleshooting#toc1)

*Links úteis*

[Fórum do fabricante dos módulos ESPs](http://bbs.espressif.com/)
