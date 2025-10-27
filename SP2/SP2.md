---
layout: default
title: "SPRINT 2: INSTAL·LACIÓ, CONFIGURACIÓ DE PROGRAMARI DE BASE I GESTIÓ DE FITXERS"
---

## SISTEMES DE FITXERS I PARTICIONS
### Mida sector
Unitat mínima física on es guarden les dades en un disc. La mida per defecte és 512 bytes i no es pot modificar.

### Mida block (linux) o clúster (windows)
Unitat mínima lògica on es guarden les dades a nivell de sistema operatiu. La mida per defecte és 4096 bytes (equivalents a 8 sectors) i si que es pot modificar a l'hora de formatejar la partició. Cada partició del disc pot tenir una mida de block i sistema de fitxers diferents. 

### Fragmentació interna
Ocurreix quan els blocks són massa grans per al que és vol guardar i es desaprofita espai al disc. Per exemple; si tenim un arxiu que ocupa 2000kb farà servir 2 blocks, malbaratant la meitat dels blocks/clústers. 

Si vull guardar arxius petits el que m'interessa és modificar la mida del block per a no malbaratar espai.
Si vull guardar arxius grans m'interessa ampliar la mida del clúster al màxim. Si no ho fem tindrem menys rendiment ja que l'arxiu està més fragmentat.

### Fragmentació externa
Quan un arxiu no està guardat de manera consecutiva en la memòria i els seus accessos són més lents i baixa el rendiment. En Windows tenim l'eina de Desfragmentador de fitxers, en Linux no tenim cap eina similar ja que no és recomana fer-ho.

### Sistemes de fitxers
Windows: NTFS, fat32, etc. Linux: ext4.

Existeixen molts típus. Aquests estan optimitzats per tasques especiífiques i a vegades ens pot condicionar.

### Típus de formateig
#### Baix nivell
Quan el disc està de fàbrica. Ens esborra tot; fitxers, sistema de fitxers i ens intenta arreglar sectors defectuosos. Per fer això són necessaris programes específics.

#### Mig nivell
No borra arxius i si troba sectors defectuosos els marca però no els arregla. Es poden recuperar les dades esborrades.

#### Alt nivell
No esborra els arxius, només esborra el sistema de fitxers. Es poden recuperar les dades esborrades. Si es troben sectors defectuosos els ignora completament.

### Gestió de particions
Una partició és un tros físic del disc dur. Amb el GParted podem gestionar particions però no podem modificar la mida del block.

Un volum és una capa d'abstracció que es col·loca a sobre de les particions i/o discs. 

#### GPARTED
#### Comandes

## GESTIÓ DE PROCESSOS
## GESTIÓ D'USUARIS, GRUPS I PERMISOS
## CÒPIES DE SEGURETAT I AUTOMATIZACIÓ DE TASQUES
## QUOTES D'USUARI


