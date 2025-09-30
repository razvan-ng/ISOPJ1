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

Amb la comanda sudo fdisk -l, hem de buscar el nostre disc dur, en aquest cas es el /dev/sda

<img width="836" height="587" alt="image" src="https://github.com/user-attachments/assets/4ea0f325-5e6f-42b5-995b-ebee96f8d29b" />







## Punts de restauració.
## Configuració de la xarxa.
## Comandes generals i instal·lacions.
