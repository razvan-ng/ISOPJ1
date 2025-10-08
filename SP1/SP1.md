---
layout: default
title: "SPRINT 1: INSTAL·LACIÓ I CONFIGURACIÓ INICIAL."
---

## Virtualització i instal·lació del SO Ubuntu.
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

## Llicenciament.

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

## Gestors d'arrencada per a instal·lacions DUALS.
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

## Punts de restauració.
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

## Configuració de la xarxa.

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


## Comandes generals i instal·lacions.
