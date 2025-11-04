---
layout: default
title: "SPRINT 2: INSTAL·LACIÓ, CONFIGURACIÓ DE PROGRAMARI DE BASE I GESTIÓ DE FITXERS"
---

<img width="788" height="560" alt="image" src="https://github.com/user-attachments/assets/00cc1e41-e827-4f5a-a4cf-af412a7db038" />

## SISTEMES DE FITXERS I PARTICIONS
### Mida sector
Unitat mínima física on es guarden les dades en un disc. La mida per defecte és 512 bytes i no es pot modificar.

<img width="744" height="447" alt="image" src="https://github.com/user-attachments/assets/0f1845ec-7c82-415a-af5f-9b6a4c6b8843" />

### Mida block (linux) o clúster (windows)
Unitat mínima lògica on es guarden les dades a nivell de sistema operatiu. La mida per defecte és 4096 bytes (equivalents a 8 sectors) i si que es pot modificar a l'hora de formatejar la partició. Cada partició del disc pot tenir una mida de block i sistema de fitxers diferents. 

<img width="637" height="98" alt="image" src="https://github.com/user-attachments/assets/3ab9cb61-e116-4ace-a849-36cc7556d692" />

### Fragmentació interna
Ocurreix quan els blocks són massa grans per al que és vol guardar i es desaprofita espai al disc. Per exemple; si tenim un arxiu que ocupa 2000kb farà servir 2 blocks, malbaratant la meitat dels blocks/clústers. 

Si volem guardar arxius petits el que interessa és modificar la mida del block per a no malbaratar espai.
Si volem guardar arxius grans interessa ampliar la mida del clúster al màxim. Si no ho fem tindrem menys rendiment ja que l'arxiu està més fragmentat.

<img width="591" height="206" alt="image" src="https://github.com/user-attachments/assets/7bf5e0d6-c833-4467-85fc-a05128d92d9e" />

La comanda "du -b xyz", on xyz és el nom del arxiu, mostra la mida en bytes per contingut. En canvi, "du -sh xyz" mostra la mida que ocupa en el sistema operatiu, en conclusió, el espai ocupat.

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

GParted és una eina que ens permet redimensionar, crear i esborrar particions, entre altres funcions. Compta amb una GUI què permet a l'usuari una interacció per part de l'usuari més fluïda i còmoda.

<img width="777" height="536" alt="image" src="https://github.com/user-attachments/assets/bd058958-2c3c-4afe-a892-6f3b2c0c442b" />


#### Comandes

Amb fdisk podem crear una partició (o varies) si un disc no està particionat. Premem "n" per fer-ne una nova partició i premem enter (es sel·leccionen les opcions per defecte). Quan haguem arribat a l'apartat on ens pregunta la mida de la partició dividim el nombre màxim entre 2 per fer-ne 2 de la mateixa mida. 

<img width="777" height="525" alt="image" src="https://github.com/user-attachments/assets/6bd7602e-e7bc-413b-ae23-c88d8ad15ffb" />

<img width="556" height="484" alt="image" src="https://github.com/user-attachments/assets/7041e457-8aba-4fb9-9780-40ca49e84e36" />

<img width="814" height="354" alt="image" src="https://github.com/user-attachments/assets/8816df23-79df-472e-abf1-4df235fd0336" />

Amb la "w" sortim i guardem.

Creem la partició ext4 amb "mkfs ext4 -b 2048 /dev/sdb1".

<img width="696" height="213" alt="image" src="https://github.com/user-attachments/assets/9a64650c-42fd-4266-af53-c9b858281074" />

I la partició ntfs amb "mkfs ntfs /dev/sdb2/".

<img width="535" height="38" alt="image" src="https://github.com/user-attachments/assets/50fff4e3-cd28-4cc9-a2d2-e26526e1b307" />

Comprovem la mida de block de la partició ext4.

<img width="636" height="91" alt="image" src="https://github.com/user-attachments/assets/d370799c-3b20-46b4-b18f-39b22aafe486" />

Comprovem les particions al GParted.

<img width="756" height="253" alt="image" src="https://github.com/user-attachments/assets/3d494eed-d1e3-4b6d-91e1-2da16707783b" />




<img width="671" height="168" alt="image" src="https://github.com/user-attachments/assets/a4f3d598-7b86-499f-aeb0-ea484dffcdbd" />

<img width="557" height="110" alt="image" src="https://github.com/user-attachments/assets/d3555320-f7d9-4ddf-b181-cbaeabd1ddce" />

<img width="438" height="86" alt="image" src="https://github.com/user-attachments/assets/7941c80b-148b-4b79-8b66-455e89750975" />


## GESTIÓ DE PROCESSOS
## GESTIÓ D'USUARIS, GRUPS I PERMISOS
## CÒPIES DE SEGURETAT I AUTOMATIZACIÓ DE TASQUES
## QUOTES D'USUARI


