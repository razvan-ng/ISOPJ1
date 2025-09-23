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
En aquest material he emprat la llicència 4.0 de Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International, la qual permet copiar, redistribuïr, transformar i reconstuir el material.

Per poder fer-ho s'ha de donar crèdits al autor pertinent, no es pot fer servir en fins comercials i/o per treure-li cap rendiment econòmic i en cas de que s'adapti el material presentat s'ha de compartir amb la mateixa llicència.
## Gestors d'arrencada per a instal·lacions DUALS.
## Punts de restauració.
## Configuració de la xarxa.
## Comandes generals i instal·lacions.
