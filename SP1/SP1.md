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

<img width="1308" height="912" alt="Screenshot from 2025-09-23 13-11-13" src="https://github.com/user-attachments/assets/5d9cff01-f579-41d9-ae47-8f27a2a17426" />

A continuació triem zona horària i configurem el nostre usuari. Esperem a que finalitzi el procés d'instal·lació.

<img width="1308" height="912" alt="Screenshot from 2025-09-23 13-12-29" src="https://github.com/user-attachments/assets/24607212-bdd0-4d2e-87ec-29770051917a" />

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

<img width="1031" height="859" alt="Screenshot from 2025-09-30 13-51-03" src="https://github.com/user-attachments/assets/f954c816-346f-4943-a30f-95a18e2cea6a" />

Acceptem les condicions. Ens deixara triar entre dues opcions; triem la personalitzada per poder fer el dual boot.

<img width="1031" height="859" alt="Screenshot from 2025-09-30 13-52-16" src="https://github.com/user-attachments/assets/b397ba38-71de-426e-84fd-0482478b1a0f" />

Seleccionem l'espai sense assignar i premem sobre "Siguiente".

<img width="1031" height="859" alt="Screenshot from 2025-09-30 13-53-34" src="https://github.com/user-attachments/assets/db9b7335-9b4d-4bd8-9819-1772cb5800ff" />

Esperem a que es completi l'instal·lació.

<img width="1031" height="859" alt="Screenshot from 2025-09-30 13-54-09" src="https://github.com/user-attachments/assets/fd34a8f9-5ae4-4470-b32c-4f7b9611289d" />

Configurem el sistema segons les nostres preferències a les pantalles següents.

<img width="1031" height="859" alt="Screenshot from 2025-09-30 14-07-06" src="https://github.com/user-attachments/assets/01e3381f-157e-4a3c-91cb-87f2b76e48bf" />

Una vegada estiguem a l'escriptori, Windows s'haurà instal·lat. Ara haurem de tornar a instal·lar el GRUB ja que l'instal·lador de Windows elimina el gestor d'arrencada i no podrem iniciar Ubuntu.

<img width="1031" height="859" alt="Screenshot from 2025-09-30 14-12-05" src="https://github.com/user-attachments/assets/7af4a332-1cfe-4f0d-a600-3352fdb26c6e" />

Amb F2 mentres la màquina estigui arrancant entrarem a la BIOS de la màquina virtual. A l'apartat Boot Manager triem Ubuntu per entrar al Linux.

<img width="645" height="565" alt="Screenshot from 2025-09-30 14-17-03" src="https://github.com/user-attachments/assets/4010aca5-33ac-457e-bc02-a2f969fbfed5" />

Entrem al nostre navegador al [següent link](https://help.ubuntu.com/community/Boot-Repair) per descarregar el Boot Repair, un programa què ens facilitarà la feina de restaurar el GRUB.

Obrim una terminal i inserim aquestes comandes per instal·lar Boot-Repair.

<img width="811" height="486" alt="image" src="https://github.com/user-attachments/assets/2666789d-16ed-4f62-b0b4-8cd41253b7b7" />

<img width="811" height="486" alt="image" src="https://github.com/user-attachments/assets/7f407af7-6492-4967-82b2-04db7e2b3918" />

Una vegada executada l'última comanda s'iniciarà el programa automaticament. Primer farà un escaneig dels discs i un cop hagi acabat ens donarà dos opcions, triarem la recomanada.

<img width="420" height="326" alt="image" src="https://github.com/user-attachments/assets/ae6b272e-4739-47be-9f5d-119ef1435777" />

Esperem a que ens reinstali GRUB automàticament i ens arregli l'arrencada.

<img width="476" height="161" alt="Screenshot from 2025-10-07 13-54-03" src="https://github.com/user-attachments/assets/a950f0c4-a7ee-42cb-af12-25fbbd6d34b8" />

Un cop acabi ens preguntarà si volem que pugi un informe a pastebin, li diem que no (si ho voleu apreteu si).

<img width="476" height="161" alt="Screenshot from 2025-10-07 13-54-57" src="https://github.com/user-attachments/assets/7c2dd0bb-ff97-4847-8038-94229249d4eb" />

Al cap d'un moment ens surtirà una pantalla conforme el boot s'ha restaurat satisfactòriament, reiniciem i ja ens bootejarà amb el GRUB.

<img width="1047" height="400" alt="Screenshot from 2025-10-07 13-55-40" src="https://github.com/user-attachments/assets/95c733ac-dac2-44c1-88e5-8eecb1f7cd00" />

Un cop s'hagi reiniciat ens surtirà el GRUB.

<img width="1052" height="880" alt="Screenshot from 2025-10-07 13-59-35" src="https://github.com/user-attachments/assets/fa2d7368-f217-4804-aab0-0ff78d3825c6" />

## PUNTS D'INSTAL·LACIÓ.
Per fer punts de restauració a l'Ubuntu utilitzarem el Timeshift. L'instal·lem amb sudo apt-get install timeshift

<img width="788" height="503" alt="Screenshot from 2025-10-07 12-50-33" src="https://github.com/user-attachments/assets/33f7f1e2-be6d-45d6-bd0f-15142a1be60b" />

Fem servir el fdisk per visualitzar les particions i els discs disponibles al sistema. (fdisk -l)

<img width="866" height="629" alt="image" src="https://github.com/user-attachments/assets/d43632bc-a0ec-416f-9161-d6ff70aa961b" />

Busquem el disc addicional que hem instal·lat i el sel·lecionem. En aquest cas es el /dev/sdb. (fdisk /dev/sdb)

<img width="788" height="187" alt="Screenshot from 2025-10-07 12-52-20" src="https://github.com/user-attachments/assets/34f729a9-3483-41fc-997b-31a33b3a679d" />

Amb la comanda "n" fem una partició, anem apretant enter fins que ens digui que la partició s'ha creat (volem els valors predeterminats).

<img width="788" height="440" alt="Screenshot from 2025-10-07 12-53-29" src="https://github.com/user-attachments/assets/38728445-764b-4dce-8f1a-bc9511937e77" />

Consultem amb fdisk -l que la partició s'hagi creat satisfactòriament.

<img width="788" height="440" alt="Screenshot from 2025-10-07 12-54-42" src="https://github.com/user-attachments/assets/119722df-c909-4a58-9dc6-30a0edc4d2f4" />

Li donem format ext4 a la partició creada amb la comanda mkfs.ext4 /dev/sdb1

<img width="788" height="440" alt="Screenshot from 2025-10-07 12-55-47" src="https://github.com/user-attachments/assets/d1ef10a2-fd4d-4851-9c08-44b21ea4e8cb" />

Un cop feta la partició creem arxius aleatoris per provar que el programari funciona. A la nostra carpeta d'usuari creem un arxiu hola (touch hola) i una carpeta adeu (mkdir adeu) amb superusuari. Comprovem amb ls que s'han creat.

<img width="788" height="440" alt="Screenshot from 2025-10-07 12-56-33" src="https://github.com/user-attachments/assets/099cd6ad-7707-4a2d-81b2-94d51e3a2e5a" />

Havent creat els arxius, iniciem el Timeshift i sel·lecionem el típus de punt de restauració que volem.

<img width="788" height="440" alt="Screenshot from 2025-10-07 13-03-08" src="https://github.com/user-attachments/assets/b66d39ae-365b-45c7-adb8-3211a6353772" />

Triem la ubicació on volem que els snapshots es guardin, en aquest cas en el disc que acabem de particionar.

<img width="788" height="440" alt="Screenshot from 2025-10-07 13-04-09" src="https://github.com/user-attachments/assets/9999dcec-981e-4dc1-a8d1-28d159f26d5f" />

A continuació eligim la periodicitat en la qual volem que es facin els snapshots. Triem que ho faci amb cada arrencada de l'equip (tarda 10 minuts des de que arranquem el equim fins que la fa).

<img width="788" height="440" alt="Screenshot from 2025-10-07 13-04-22" src="https://github.com/user-attachments/assets/0e35a36a-fd35-4391-af02-38129d76d699" />

També haurem de dirli que exclogui el root però que inclogui la carpeta home de l'usuari.

<img width="797" height="613" alt="Screenshot from 2025-10-07 13-30-22" src="https://github.com/user-attachments/assets/14b61acf-872b-43e0-ac45-c99af5160d58" />

Un cop configurat el programa ens apareixerà la pantalla d'inici buida ja que no hem fet cap snapshot encara. El podem fer nosaltres manualment per comprovar que el programa funcioni.

<img width="839" height="684" alt="Screenshot from 2025-10-07 13-05-10" src="https://github.com/user-attachments/assets/a5de3eb7-dd57-4fba-973d-f1f3d3449b90" />

<img width="880" height="704" alt="Screenshot from 2025-10-07 13-05-20" src="https://github.com/user-attachments/assets/82316b6e-baf2-464e-b9f4-d358c5449c16" />

Un cop acabat ens apareixerà la instantània que acabem de crear. 

<img width="880" height="704" alt="Screenshot from 2025-10-07 13-07-38" src="https://github.com/user-attachments/assets/59b5ebd2-c71a-4171-963e-bf9808ed940d" />

Eliminem els arxius que hem creat anteriorment per comprovar que ens restauraría els fitxers en un cas real.

<img width="880" height="254" alt="Screenshot from 2025-10-07 13-09-29" src="https://github.com/user-attachments/assets/8abb0dbf-a4e6-4553-8f09-fce17027077c" />

Estant al Timeshift, tenint sel·lecionat el snapshot que volem restaurar, apretem sobre "Restore" i ens apareixerà els arxius que ens restablirà, crearà o borrarà per tal que el sistema estigui igual.

<img width="593" height="488" alt="Screenshot from 2025-10-07 13-41-27" src="https://github.com/user-attachments/assets/a73c1e6a-8ed7-4130-b9a1-aff9a674990e" />

Esperem a què acabi la recuperació (ens pot reiniciar el equip) i ja ho tindrem llest. 

<img width="1308" height="912" alt="Screenshot from 2025-10-07 14-03-33" src="https://github.com/user-attachments/assets/482899e2-7f69-4933-b474-7f5c8fa1c062" />

## CONFIGURACIÓ DE LA XARXA.

Mitjançant la comanda "ip a" ens apareixeran llistats totes les NIC que tinguem instal·lades a l'ordinador, amb la nostra ip privada, MAC, etc. La meva IP privada és 192.168.203.152/24.

<img width="756" height="333" alt="Screenshot from 2025-10-07 13-42-59" src="https://github.com/user-attachments/assets/08aa2f0b-8d7b-420b-968a-e7c4edfffe9c" />

Per defecte (i el ideal en instal·lacions casolanes) els dispositius es configuren en el servei d'assignació IP DHCP, en el què el propi router assigna automàticament una adreça IP a un dispositiu en funció de les IPs disponibles. La principal característica és que un mateix dispositiu se li pot assignar IPs privades distintes si aquest no està configurat per tenir-ne una fixa i això pot suposar un problema en instal·lacions on hi hagin servidors. Podem configurar una IP privada mitjançant interfícia gràfica als ajustaments de l'Ubuntu. 

<img width="756" height="523" alt="Screenshot from 2025-10-07 13-44-01" src="https://github.com/user-attachments/assets/3c397a29-c08f-4f98-9359-7bc049e0f1f0" />

Comprovem que haguem configurat correctament els paràmetres fent un ping a una pàgina web. 

<img width="756" height="250" alt="Screenshot from 2025-10-07 13-44-23" src="https://github.com/user-attachments/assets/3689d483-a6c3-4746-b11e-ca986b43bf6a" />

Podem també configurar aquests paràmetres mitjançant netplan. El busquem a la seva ubicació a /etc/netplan. Allà trobarem el .yaml.

<img width="756" height="250" alt="Screenshot from 2025-10-07 13-45-22" src="https://github.com/user-attachments/assets/3d132b5b-e10f-4ec3-b16d-97e5851431ea" />

Configurarem els paràmetres d'IP fixa i DNS igual que ho vam fer amb l'interfície gràfica, indicant-li que no volem que faci servir DHCP, indicant-li una IP fixa i un servidor DNS. (sudo nano /etc/netplan/01-network-manager-all.yaml).

<img width="756" height="534" alt="Screenshot from 2025-10-07 13-49-14" src="https://github.com/user-attachments/assets/f3f209cc-42a4-4186-b677-ac50d3b4f6c4" />

Guardem amb Ctrl + X i Enter. Apliquem els canvis amb sudo netplan apply i ho comprovem als ajustaments.

<img width="756" height="291" alt="Screenshot from 2025-10-07 13-51-17" src="https://github.com/user-attachments/assets/0ad90731-3b0b-4281-ab2d-7882ef1c49fa" />

<img width="756" height="291" alt="Screenshot from 2025-10-07 13-51-53" src="https://github.com/user-attachments/assets/5b7b3565-cfc0-4333-94fb-bbbf32cf271b" />

Comprovem la connectivitat fent un ping a una pàgina web i que aquest tingui 0% de packet loss.

<img width="756" height="291" alt="Screenshot from 2025-10-07 13-52-37" src="https://github.com/user-attachments/assets/5cad852f-c9a7-4023-a5f1-fba034f92438" />


## COMANDES GENERALS I INSTAL·LACIONS.

Els programes a GNU/Linux es poden insta·lar de diferents maneres; apt, dpkg, mitjançant repositoris, amb la tenda d'aplicacions, etc.

### Tenda d'aplicacions

Les distros com Ubuntu, Debian, Fedora, etc, tenen una tenda d'aplicacions que podem fer servir per instal·lar aplicacions sense la necessitat d'escriure comandes a la terminal. És útil per a usuaris novells.

Busquem el programa App Center del nostre sistema operatiu, en el meu cas Ubuntu.

<img width="161" height="167" alt="Screenshot from 2025-10-20 12-53-28" src="https://github.com/user-attachments/assets/666cac00-7ed0-4440-97d2-0c142b2cb3c9" />

<img width="1384" height="904" alt="Screenshot from 2025-10-20 12-54-24" src="https://github.com/user-attachments/assets/de6cd413-9207-4cd4-9957-bb9853a95538" />

Busquem qualsevol programa que vulguem instal·lar i fem click a sobre seu per veure la pantalla de l'aplicació.

<img width="1384" height="904" alt="Screenshot from 2025-10-20 12-56-20" src="https://github.com/user-attachments/assets/894adecc-3a70-4623-85a0-b7c000d7e7de" />

<img width="1384" height="904" alt="Screenshot from 2025-10-20 12-56-32" src="https://github.com/user-attachments/assets/ed4702a1-1833-4e72-a2b7-05783b03dd20" />

Premem sobre el botó d'Install, posem la nostra contrasenya i esperem a que es completi l'instal·lació.

<img width="381" height="406" alt="Screenshot from 2025-10-20 12-57-18" src="https://github.com/user-attachments/assets/e62c8350-a02f-4a16-8092-49ef9b940313" />

<img width="1384" height="904" alt="Screenshot from 2025-10-20 12-57-49" src="https://github.com/user-attachments/assets/846cd9a6-c2e4-4cd0-a1f0-b5abead9cadf" />

Comprovem que s'hagi instal·lat el programa al calaix d'aplicacions.

<img width="381" height="245" alt="Screenshot from 2025-10-20 12-58-25" src="https://github.com/user-attachments/assets/99343c54-ae3c-4db6-91ec-fd1d5d1412bd" />

Podem desinstal·lar el programa fent click a la fletxa del costat del botó "Open" a la App Center.

<img width="1384" height="904" alt="Screenshot from 2025-10-20 12-59-23" src="https://github.com/user-attachments/assets/185f3179-3935-498b-b186-29cabf605cdc" />

Comprovem que s'hagi desinstal·lat.

<img width="381" height="245" alt="Screenshot from 2025-10-20 12-59-39" src="https://github.com/user-attachments/assets/ca0b20b5-17b2-47cf-9983-d92df6b2c606" />

### Amb comanda apt install.

Obrim una terminal i amb permissos de superusuari fem apt install nom_paquet. Quan ens digui si volem continuar premem enter (la lletra que surti en majúscula és la predeterminada "Y/n".

<img width="806" height="428" alt="Screenshot from 2025-10-20 12-35-05" src="https://github.com/user-attachments/assets/afe37781-06f1-4175-ad70-a0e4c821760a" />

El busquem al calaix d'aplicacions i comprovem que s'hagi instal·lat correctament.

<img width="615" height="466" alt="Screenshot from 2025-10-20 12-36-13" src="https://github.com/user-attachments/assets/8213baeb-8fbe-4fc2-aa23-fe9c9800e314" />

Ara, podem desinstal·lar el programa i les seves configuracions amb apt purge nom_paquet.

<img width="801" height="328" alt="Screenshot from 2025-10-20 12-37-16" src="https://github.com/user-attachments/assets/e6b6d986-1ff6-491d-8354-6895511706c6" />

I per borrar tot el que ja no necessita cap programa instal·lat ho podem fer amb apt autoremove.

<img width="809" height="360" alt="Screenshot from 2025-10-20 12-37-57" src="https://github.com/user-attachments/assets/92c31963-a11d-45bd-9a09-11b43998a392" />

Comprovem que s'hagi borrat.

<img width="809" height="360" alt="Screenshot from 2025-10-20 12-38-52" src="https://github.com/user-attachments/assets/26e8681e-b333-4a29-9b2e-bc30534b2ab8" />

### Amb el paquet .deb.

Busquem i descarreguem el paquet que desitjem instal·lar, en el meu cas el tinc a Downloads.

<img width="381" height="245" alt="Screenshot from 2025-10-20 13-08-40" src="https://github.com/user-attachments/assets/3412fe83-4247-44f8-9ece-df8502845cc5" />

Obrim una terminal i entrem dins del directori on es troba l'arxiu .deb. Amb la comanda sudo dpkg -i instal·lem el paquet.

<img width="718" height="321" alt="Screenshot from 2025-10-20 12-31-29" src="https://github.com/user-attachments/assets/aeefea78-75f2-4c27-a93f-1cf4df27d845" />

Addicionalment, podem comprovar si hem instal·lat un paquet amb dpkg --get-selections | grep nom_paquet. (El nom del paquet pot estar incomplet.)

<img width="641" height="237" alt="Screenshot from 2025-10-20 12-32-36" src="https://github.com/user-attachments/assets/02b96516-b46b-4de9-a86a-0467ce7b565c" />

Desinstal·lem el paquet amb dpkg -r nom.

<img width="672" height="145" alt="Screenshot from 2025-10-20 12-33-19" src="https://github.com/user-attachments/assets/2b2607f2-b34d-4219-9565-3a47ae6cc885" />

Comprovem que s'ha desinstal·lat.

<img width="501" height="74" alt="Screenshot from 2025-10-20 12-33-47" src="https://github.com/user-attachments/assets/41c8eb5f-acd5-4f69-8ab6-d6129efb3e2a" />


### Instal·lació amb repositoris.

Per aquest apartat instal·larem el Google Chrome. Afegim la direcció del repositori a la font d'arxius.

<img width="822" height="61" alt="Screenshot from 2025-10-20 12-40-39" src="https://github.com/user-attachments/assets/98eb7737-bfd0-4404-83ef-f34dd0871784" />

Després, descarreguem la clau pública del repositori i la afegim a les claus.

<img width="829" height="75" alt="Screenshot from 2025-10-20 12-41-33" src="https://github.com/user-attachments/assets/45da2fe2-ec8b-4644-9f75-44cb4a7f23b8" />

Actualitzem l'índex de repositoris amb apt update.

<img width="829" height="260" alt="Screenshot from 2025-10-20 12-42-21" src="https://github.com/user-attachments/assets/af0bfd1e-2158-4c86-9cc4-9e78f37ebfc9" />

Instal·lem el paquet de Google Chrome amb apt install google-chrome-stable.

<img width="829" height="322" alt="Screenshot from 2025-10-20 12-43-20" src="https://github.com/user-attachments/assets/e3c5ea87-5c0c-4034-8f4f-bd5bc2b7e4ce" />

Comprovem que s'hagi instal·lat.

<img width="632" height="654" alt="Screenshot from 2025-10-20 12-43-55" src="https://github.com/user-attachments/assets/858a4b15-6b56-4c4b-b11f-3c5556ad3721" />

El desinstal·lem i comprovem que s'hagi desinstal·lat correctament.

<img width="821" height="373" alt="Screenshot from 2025-10-20 12-44-48" src="https://github.com/user-attachments/assets/ffba2f33-baf8-4cf3-ba34-ccb951f4f8ac" />

<img width="813" height="319" alt="Screenshot from 2025-10-20 12-45-33" src="https://github.com/user-attachments/assets/fcb82927-2a93-42b1-945a-68626b91050f" />
