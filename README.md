## _IDE_ Arduino/ESP8266 no _GNU_/Linux 

Este pequeno tutorial descreve os passos necessários para configuração e instalação do ambiente de desenvolvimento _Arduino_
em sistemas operacionais _GNU_/Linux. Permitindo o uso da _IDE_ do Arduino na codificação e gravação direta das placas que possuam o _ESP8266_.

***
######Os passos consistem em:
* Instalar o _JAVA_.
* Descarregar e instalar a _IDE_ do Arduino.
* Configurar permissões e grupos.(nada complicado)
* Cofigurar a _IDE_ do Arduino para trabalhar com o _ESP_.

---

```
Todos os procedimentos efetuados neste tutorial foram executados em uma distribuição GNU/Linux
Xubuntu 16.04.1 LTS
```

######Instalando o _JAVA_

* Adicionar repositório da _ORACLE_
```
Linux terminal:~$ sudo add-repository ppa:webupd8team/java
```
* Atualize a base
```
Linux terminal:~$ sudo apt-get update
```
* Instale o Java
```
sudo apt-get install oracle-java8-installer
```
