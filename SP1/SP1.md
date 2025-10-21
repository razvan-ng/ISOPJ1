---
layout: default
title: "SPRINT 1: INSTAL·LACIÓ I CONFIGURACIÓ INICIAL."
---

## VIRTUALITZACIÓ I INSTAL·LACIÓ DEL SO UBUNTU.
Iniciem Virtualbox i creem una màquina virtual.


![inici virtualbox](/assets/Virtualitzacio i instal·lació del SO Ubuntu/1.png)

Configurem els paràmetres de la màquina virtual segons els requisits mínims d'Ubuntu, els quals han de ser:
- 25GB disc dur
- 4GB RAM

![requisits](/assets/Virtualitzacio i instal·lació del SO Ubuntu/requisits.png)

Com farem un dual boot, assignem 80GB i 8GB de RAM.

![paràmetres](/assets/Virtualitzacio i instal·lació del SO Ubuntu/2.png)

Configurem la xarxa de la màquina virtual a "Xarxa NAT" per què la màquina virtual tingui accés a Internet i pugui ser visible entre les màquines virtuals del host.

Per fer-ho anem a la secció "Eines" situada la primera al llistat. Anem a la secció "NAT Networks", creem una xarxa NAT i modifiquem la IP al nostre gust.

![NAT](/assets/Virtualitzacio i instal·lació del SO Ubuntu/3.png)

Una vegada fet arranquem la màquina virtual i triem l'arxiu ISO de l'instal·lador.

![ISO](/assets/Virtualitzacio i instal·lació del SO Ubuntu/4.png)

Iniciarà l'instal·lador i escullim "Try or Install Ubuntu"

![inici install](/assets/Virtualitzacio i instal·lació del SO Ubuntu/5.png)

Seleccionem idioma preferit i fem click a "Install Ubuntu"

![inici install](/assets/Virtualitzacio i instal·lació del SO Ubuntu/6.png)

Una vegada arribem a l'apartat de típus d'instal·lació triem "Something else" per fer un particionat personalitzat.

![inici install](/assets/Virtualitzacio i instal·lació del SO Ubuntu/7.png)

Creem una nova taula de partició a "New Partition Table" per poder particionar el disc i fem click a continuar.

![inici install](/assets/Virtualitzacio i instal·lació del SO Ubuntu/8.png)

Particionem el disc segons les nostres necessitats. La màquina virtual emprada té un disc de 80GB i 8 GB de RAM. Amb aquesta memòria no és necessari una partició swap molt gran, així que li donem 4GB per anar be. Les particions / i /home són de 25GB i 15GB respectivament ja que només s'utilitzaran programes lleugers i documents de text.

<img width="1308" height="912" alt="image" src="https://github.com/user-attachments/assets/89fa206a-6346-47cb-a715-4e8079e8fe41" />

A continuació triem zona horària i configurem el nostre usuari. Esperem a que finalitzi el procés d'instal·lació.

<img width="1308" height="912" alt="image" src="https://github.com/user-attachments/assets/2cf5a3e1-9df6-4428-94e4-deb1fec45953" />

## LLICENCIAMENT.

Ubuntu és una distribució **GNU/Linux** de programari **lliure i de codi obert**.  
El seu llicenciament garanteix les quatre llibertats fonamentals:

1. **Utilitzar** el programari per a qualsevol finalitat.  
2. **Estudiar** i adaptar-lo (accés al codi font).  
3. **Redistribuir** còpies.  
4. **Millorar-lo** i compartir les modificacions.  

### Tipus de llicències presents a Ubuntu
- **GPL (General Public License):** llicència copyleft que obliga a mantenir la llibertat en obres derivades.  
- **LGPL (Lesser GPL):** pensada per biblioteques; permet combinar amb programari propietari.  
- **Permissives (MIT, BSD, Apache):** donen flexibilitat i permeten integrar amb codi privatiu.  

### Aspectes legals
Tot i que està protegit per **drets d’autor**, les llicències asseguren que qualsevol usuari pugui fer ús, estudiar, redistribuir i modificar el programari dins el marc legal.  

## GESTORS D'ARRENCADA PER A INSTAL·LACIONS DUALS.
Iniciem la màquina virtual amb la ISO de Windows a l'unitat virtual.

<img width="1031" height="859" alt="image" src="https://github.com/user-attachments/assets/27caee92-53f0-4878-8733-ab8623f0904e" />

Acceptem les condicions. Ens deixara triar entre dues opcions; triem la personalitzada per poder fer el dual boot.

<img width="1031" height="859" alt="image" src="https://github.com/user-attachments/assets/70f0f2c2-45cf-4211-b321-d3306425d97a" />

Seleccionem l'espai sense assignar i premem sobre "Siguiente".

<img width="1031" height="859" alt="image" src="https://github.com/user-attachments/assets/7e790ffe-bdf5-4444-b389-4babc917ac89" />

Esperem a que es completi l'instal·lació.

<img width="1031" height="859" alt="image" src="https://github.com/user-attachments/assets/674020d7-0864-4d12-a7ae-a4aaabecda28" />

Configurem el sistema segons les nostres preferències a les pantalles següents.

<img width="1031" height="859" alt="image" src="https://github.com/user-attachments/assets/6b9d8b7b-fc63-494b-ba4a-55bc77274147" />

Una vegada estiguem a l'escriptori, Windows s'haurà instal·lat. Ara haurem de tornar a instal·lar el GRUB ja que l'instal·lador de Windows elimina el gestor d'arrencada i no podrem iniciar Ubuntu.

<img width="1031" height="859" alt="image" src="https://github.com/user-attachments/assets/5b42f818-5eb7-43a2-b03d-a95db2989e7e" />

Amb F2 mentres la màquina estigui arrancant entrarem a la BIOS de la màquina virtual. A l'apartat Boot Manager triem Ubuntu per entrar al Linux.

<img width="645" height="565" alt="image" src="https://github.com/user-attachments/assets/85fe854e-9b63-41c8-9b32-1fa84436b2ef" />

Entrem al nostre navegador al [següent link](https://help.ubuntu.com/community/Boot-Repair) per descarregar el Boot Repair, un programa què ens facilitarà la feina de restaurar el GRUB.

Obrim una terminal i inserim aquestes comandes per instal·lar Boot-Repair.

<img width="889" height="191" alt="image" src="https://github.com/user-attachments/assets/63f85793-2892-4046-a730-c76a1d4b53af" />

<img width="756" height="250" alt="image" src="https://github.com/user-attachments/assets/607bf37f-1a05-4989-bfac-d93e585c83c2" />

Una vegada executada l'última comanda s'iniciarà el programa automaticament. Primer farà un escaneig dels discs.

<img width="756" height="214" alt="image" src="https://github.com/user-attachments/assets/461e58aa-5808-4339-bac6-032fd2389bdb" />

Un cop hagi acabat ens donarà dos opcions, triarem la recomanada.

<img width="476" height="339" alt="image" src="https://github.com/user-attachments/assets/4959eb70-5cf3-42bc-883f-70d46efc74fa" />

Esperem a que ens reinstali GRUB automàticament i ens arregli l'arrencada.

<img width="476" height="161" alt="image" src="https://github.com/user-attachments/assets/b87c6721-e81b-4bd2-a0f2-37daa43cfe0b" />

Un cop acabi ens preguntarà si volem que pugi un informe a pastebin, li diem que no (si ho voleu apreteu si).

<img width="476" height="161" alt="image" src="https://github.com/user-attachments/assets/fd4e295d-d946-4efc-8051-26d7f106c1d7" />

Al cap d'un moment ens surtirà una pantalla conforme el boot s'ha restaurat satisfactòriament, reiniciem i ja ens bootejarà amb el GRUB.

<img width="1047" height="400" alt="image" src="https://github.com/user-attachments/assets/dc62a676-8e81-41de-b133-6cb0b81f47d6" />

Un cop s'hagi reiniciat ens surtirà el GRUB.

<img width="1052" height="880" alt="image" src="https://github.com/user-attachments/assets/8f533da8-7dd9-4b15-b8a0-1d5b3c54857e" />

## PUNTS D'INSTAL·LACIÓ.
Per fer punts de restauració a l'Ubuntu utilitzarem el Timeshift. L'instal·lem amb sudo apt-get install timeshift

<img width="788" height="503" alt="image" src="https://github.com/user-attachments/assets/a2431a41-cad2-421e-b9f3-33a02d332f7a" />

Fem servir el fdisk per visualitzar les particions i els discs disponibles al sistema. (fdisk -l

<img width="866" height="629" alt="image" src="https://github.com/user-attachments/assets/8efa21f1-720d-4e79-84e5-c24b229c9fc7" />

Busquem el disc addicional que hem instal·lat i el sel·lecionem. En aquest cas es el /dev/sdb. (fdisk /dev/sdb)

<img width="788" height="187" alt="image" src="https://github.com/user-attachments/assets/024d9d3f-2462-47f1-95a7-35f56dcde6f7" />

Amb la comanda "n" fem una partició, anem apretant enter fins que ens digui que la partició s'ha creat (volem els valors predeterminats).

<img width="788" height="440" alt="image" src="https://github.com/user-attachments/assets/2d401971-e25d-49e0-829a-b88f97ae3fdf" />

Consultem amb fdisk -l que la partició s'hagi creat satisfactòriament.

<img width="788" height="440" alt="image" src="https://github.com/user-attachments/assets/d0b98122-9063-462e-8aad-8fe3d6363364" />

Li donem format ext4 a la partició creada amb la comanda mkfs.ext4 /dev/sdb1

<img width="788" height="440" alt="image" src="https://github.com/user-attachments/assets/bac5bc08-b8e0-4923-88d8-71c82ff73482" />

Un cop feta la partició creem arxius aleatoris per provar que el programari funciona. A la nostra carpeta d'usuari creem un arxiu hola (touch hola) i una carpeta adeu (mkdir adeu) amb superusuari. Comprovem amb ls que s'han creat.

<img width="788" height="440" alt="image" src="https://github.com/user-attachments/assets/407454db-820d-480a-8ced-974c93cdbaaa" />

Havent creat els arxius, iniciem el Timeshift i sel·lecionem el típus de punt de restauració que volem.

<img width="788" height="440" alt="image" src="https://github.com/user-attachments/assets/663c62ea-bedc-4a56-93c1-2e1bd67ec1dc" />

Triem la ubicació on volem que els snapshots es guardin, en aquest cas en el disc que acabem de particionar.

<img width="788" height="440" alt="image" src="https://github.com/user-attachments/assets/20bf6a6c-323f-4aed-9409-54fc6257889c" />

A continuació eligim la periodicitat en la qual volem que es facin els snapshots. Triem que ho faci amb cada arrencada de l'equip (tarda 10 minuts des de que arranquem el equim fins que la fa).

<img width="788" height="440" alt="image" src="https://github.com/user-attachments/assets/a52b10c4-8e30-4847-baf3-89f928002fd5" />

També haurem de dirli que exclogui el root però que inclogui la carpeta home de l'usuari.

<img width="797" height="613" alt="image" src="https://github.com/user-attachments/assets/df37f126-7190-4229-bf21-f234dc1bf280" />

Un cop configurat el programa ens apareixerà la pantalla d'inici buida ja que no hem fet cap snapshot encara. El podem fer nosaltres manualment per comprovar que el programa funcioni.

<img width="839" height="684" alt="image" src="https://github.com/user-attachments/assets/9dc072b0-fe3d-44e9-b749-3413caffaa45" />

<img width="880" height="704" alt="image" src="https://github.com/user-attachments/assets/05c7158c-904f-4167-9977-a5a78b73003b" />

Un cop acabat ens apareixerà la instantània que acabem de crear. 

<img width="880" height="704" alt="image" src="https://github.com/user-attachments/assets/0c169ae3-dbde-4deb-b14c-b689ee2ca03e" />

Eliminem els arxius que hem creat anteriorment per comprovar que ens restauraría els fitxers en un cas real.

<img width="880" height="254" alt="image" src="https://github.com/user-attachments/assets/02110fd1-5c21-4ee9-825a-09244f0c4b23" />

Estant al Timeshift, tenint sel·lecionat el snapshot que volem restaurar, apretem sobre "Restore" i ens apareixerà els arxius que ens restablirà, crearà o borrarà per tal que el sistema estigui igual.

<img width="593" height="488" alt="image" src="https://github.com/user-attachments/assets/7ec74f64-a24d-46d1-a276-4876df702bd3" />

Esperem a què acabi la recuperació (ens pot reiniciar el equip) i ja ho tindrem llest. 

<img width="1308" height="912" alt="image" src="https://github.com/user-attachments/assets/c49b4b0e-e5f4-48bd-b98d-e9e4708b1a07" />

## CONFIGURACIÓ DE LA XARXA.

Mitjançant la comanda "ip a" ens apareixeran llistats totes les NIC que tinguem instal·lades a l'ordinador, amb la nostra ip privada, MAC, etc. La meva IP privada és 192.168.203.152/24.

<img width="756" height="333" alt="image" src="https://github.com/user-attachments/assets/1ff72831-e7b7-48d1-846f-39bd689cd148" />

Per defecte (i el ideal en instal·lacions casolanes) els dispositius es configuren en el servei d'assignació IP DHCP, en el què el propi router assigna automàticament una adreça IP a un dispositiu en funció de les IPs disponibles. La principal característica és que un mateix dispositiu se li pot assignar IPs privades distintes si aquest no està configurat per tenir-ne una fixa i això pot suposar un problema en instal·lacions on hi hagin servidors. Podem configurar una IP privada mitjançant interfícia gràfica als ajustaments de l'Ubuntu. 

<img width="756" height="523" alt="image" src="https://github.com/user-attachments/assets/b4fb0de4-2714-4392-ab9e-777b894fbc85" />

Comprovem que haguem configurat correctament els paràmetres fent un ping a una pàgina web. 

<img width="756" height="250" alt="image" src="https://github.com/user-attachments/assets/39052335-2263-48e3-a515-799e75ddfc80" />

Podem també configurar aquests paràmetres mitjançant netplan. El busquem a la seva ubicació a /etc/netplan. Allà trobarem el .yaml.

<img width="756" height="250" alt="image" src="https://github.com/user-attachments/assets/e1dee6a5-240f-43af-908e-cf97c0f02c74" />

Configurarem els paràmetres d'IP fixa i DNS igual que ho vam fer amb l'interfície gràfica, indicant-li que no volem que faci servir DHCP, indicant-li una IP fixa i un servidor DNS. (sudo nano /etc/netplan/01-network-manager-all.yaml).

<img width="756" height="534" alt="image" src="https://github.com/user-attachments/assets/712ea2ee-a4b9-4a7b-9926-5e25f965ecf0" />

Guardem amb Ctrl + X i Enter. Apliquem els canvis amb sudo netplan apply i ho comprovem als ajustaments.

<img width="756" height="291" alt="image" src="https://github.com/user-attachments/assets/01b40085-393e-42eb-9e6e-f8031bc6f46a" />

<img width="756" height="291" alt="image" src="https://github.com/user-attachments/assets/dd216660-0b37-4b53-9a4e-fe3de58fa8f3" />

Comprovem la connectivitat fent un ping a una pàgina web i que aquest tingui 0% de packet loss.

<img width="756" height="291" alt="image" src="https://github.com/user-attachments/assets/d3edff33-ad3f-499f-806c-a4ce9a990802" />


## COMANDES GENERALS I INSTAL·LACIONS.

Els programes a GNU/Linux es poden insta·lar de diferents maneres; apt, dpkg, mitjançant repositoris, amb la tenda d'aplicacions, etc.

### Tenda d'aplicacions

Les distros com Ubuntu, Debian, Fedora, etc, tenen una tenda d'aplicacions que podem fer servir per instal·lar aplicacions sense la necessitat d'escriure comandes a la terminal. És útil per a usuaris novells.

Busquem el programa App Center del nostre sistema operatiu, en el meu cas Ubuntu.

<img width="161" height="167" alt="image" src="https://github.com/user-attachments/assets/0146be3c-a07a-440a-8b7e-59c91a907c71" />

<img width="1384" height="904" alt="image" src="https://github.com/user-attachments/assets/72a881bd-ac8c-4fc7-b606-346d1fd2e164" />

Busquem qualsevol programa que vulguem instal·lar i fem click a sobre seu per veure la pantalla de l'aplicació.

<img width="1384" height="904" alt="image" src="https://github.com/user-attachments/assets/e0cf8781-ad2d-4fe9-9090-2c971b2d40cd" />

<img width="1384" height="904" alt="image" src="https://github.com/user-attachments/assets/a3367efa-89cd-418e-867a-55df3d8b324c" />

Premem sobre el botó d'Install, posem la nostra contrasenya i esperem a que es completi l'instal·lació.

<img width="381" height="406" alt="image" src="https://github.com/user-attachments/assets/73cd38d0-7f64-46b2-908a-560923f58e0d" />

<img width="1384" height="904" alt="image" src="https://github.com/user-attachments/assets/4899688e-bdad-4a4e-a739-3495d9915f21" />

Comprovem que s'hagi instal·lat el programa al caixer d'aplicacions.

<img width="381" height="245" alt="image" src="https://github.com/user-attachments/assets/f60326c1-e4e2-4efe-93ea-285d1488d514" />

Podem desinstal·lar el programa fent click a la fletxa del costat del botó "Open" a la App Center.

<img width="1384" height="904" alt="image" src="https://github.com/user-attachments/assets/1948bb7e-2e97-4ad9-89bc-825c6e0fd0f2" />

Comprovem que s'hagi desinstal·lat.

<img width="381" height="245" alt="image" src="https://github.com/user-attachments/assets/40225f34-44ee-451f-9373-8ad57b4f4a0c" />

### Amb comanda apt install.

Obrim una terminal i amb permissos de superusuari fem apt install nom_paquet. Quan ens digui si volem continuar premem enter (la lletra que surti en majúscula és la predeterminada "Y/n".

<img width="806" height="428" alt="image" src="https://github.com/user-attachments/assets/d7482c3e-6889-4f2d-8205-8899ac1faf10" />

El busquem al calaix d'aplicacions i comprovem que s'hagi instal·lat correctament.

<img width="615" height="466" alt="image" src="https://github.com/user-attachments/assets/4348a7db-e5c1-445f-9132-0020a4eb39d6" />

Ara, podem desinstal·lar el programa i les seves configuracions amb apt purge nom_paquet.

<img width="801" height="328" alt="image" src="https://github.com/user-attachments/assets/6a094f78-03f6-423a-aeaa-fc58cf331701" />

I per borrar tot el que ja no necessita cap programa instal·lat ho podem fer amb apt autoremove.

<img width="809" height="360" alt="image" src="https://github.com/user-attachments/assets/b06aeae6-8b0d-46c9-af90-c4ea689ec7eb" />

Comprovem que s'hagi borrat.

<img width="809" height="360" alt="image" src="https://github.com/user-attachments/assets/51e0961e-4a3d-4af6-928c-39309ab0d7cc" />

### Amb el paquet .deb.

Busquem i descarreguem el paquet que desitjem instal·lar, en el meu cas el tinc a Downloads.

<img width="381" height="245" alt="image" src="https://github.com/user-attachments/assets/b653abf4-38ab-4104-8eb0-a783dfa57754" />

Obrim una terminal i entrem dins del directori on es troba l'arxiu .deb. Amb la comanda sudo dpkg -i instal·lem el paquet.

<img width="718" height="321" alt="image" src="https://github.com/user-attachments/assets/1fa39adc-fccf-4186-be3e-c3cd0b61124b" />

Addicionalment, podem comprovar si hem instal·lat un paquet amb dpkg --get-selections | grep nom_paquet. (El nom del paquet pot estar incomplet.)

<img width="641" height="237" alt="image" src="https://github.com/user-attachments/assets/d01fef7b-8aed-4320-a47f-97ec52bc10b9" />

Desinstal·lem el paquet amb dpkg -r nom.

<img width="672" height="145" alt="image" src="https://github.com/user-attachments/assets/f0427f6b-b915-4b55-8ad6-0d62aa983e33" />

Comprovem que s'ha desinstal·lat.

<img width="501" height="74" alt="image" src="https://github.com/user-attachments/assets/c72618af-8709-4b73-a339-53f215f712e6" />


### Instal·lació amb repositoris.

Per aquest apartat instal·larem el Google Chrome. Afegim la direcció del repositori a la font d'arxius.

<img width="822" height="61" alt="image" src="https://github.com/user-attachments/assets/fe4e54d2-c013-43d8-9f85-14e0df1a5477" />

Després, descarreguem la clau pública del repositori i la afegim a les claus.

<img width="829" height="75" alt="image" src="https://github.com/user-attachments/assets/096e9e57-a312-48aa-bfb9-1ffd8202513d" />

Actualitzem l'índex de repositoris amb apt update.

<img width="829" height="260" alt="image" src="https://github.com/user-attachments/assets/f583ddaa-2084-4015-81cf-e80033a1cd24" />

Instal·lem el paquet de Google Chrome amb apt install google-chrome-stable.

<img width="829" height="322" alt="image" src="https://github.com/user-attachments/assets/d0609dc8-d2ad-4fb4-aecb-b7435bee0082" />

Comprovem que s'hagi instal·lat.

<img width="632" height="654" alt="image" src="https://github.com/user-attachments/assets/ace13bb0-8bfa-497c-892b-47261d6acd44" />

El desinstal·lem i comprovem que s'hagi desinstal·lat correctament.

<img width="821" height="373" alt="image" src="https://github.com/user-attachments/assets/54784254-2177-48d4-9bb0-8813b078b488" />

<img width="813" height="319" alt="image" src="https://github.com/user-attachments/assets/f41debc6-b061-425e-b8c9-4e8430908cff" />
