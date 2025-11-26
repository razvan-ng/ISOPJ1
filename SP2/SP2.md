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

Montarem una partició en el nostre sistema operatiu cada vegada que arranquessim l'equip.

<img width="671" height="168" alt="image" src="https://github.com/user-attachments/assets/a4f3d598-7b86-499f-aeb0-ea484dffcdbd" />

<img width="557" height="110" alt="image" src="https://github.com/user-attachments/assets/d3555320-f7d9-4ddf-b181-cbaeabd1ddce" />

<img width="438" height="86" alt="image" src="https://github.com/user-attachments/assets/7941c80b-148b-4b79-8b66-455e89750975" />

<img width="667" height="262" alt="image" src="https://github.com/user-attachments/assets/35386ce3-4b82-41f1-85f7-0c266ab40294" />

Comprovem que les configuracions s'han aplicat correctament.

<img width="522" height="185" alt="image" src="https://github.com/user-attachments/assets/598afae0-ae9d-4807-9e1e-c45a39311121" />

## GESTIÓ DE PROCESSOS


## GESTIÓ D'USUARIS, GRUPS I PERMISOS

### Fitxers implicats

És important gestionar els usuaris d'un sistema de manera correcta per establir permissos i restriccions de forma acertada.

A Ubuntu tenim una alternativa amb GUI per fer aquesta tasca de forma més bàsica (gnome-system-tools).

<img width="1004" height="664" alt="image" src="https://github.com/user-attachments/assets/1d10253b-58d2-46d4-8dac-9b29f51d6c53" />

Els fitxers implicats en la gestió d'usuaris són 3; passwd, group i shadow.

Podem accedir a cadascún amb nano, encara que no els haurem de modiifcar mai amb aquesta eina.

sudo nano /etc/passwd

<img width="706" height="740" alt="image" src="https://github.com/user-attachments/assets/6e4f8a4c-6905-4642-9bc2-e03de690e752" />

Aquest fitxer conté tots els usuaris del sistema. Defineix l’usuari razvan (UID i GID 1000), amb directori /home/razvan i shell /bin/bash. La contrasenya està amagada a /etc/shadow (el camp “x”).

sudo nano /etc/group

Conté tots els grups del sistema. Cada vegada que es crea un usuari, és crea un grup automàticament. Per exemple, podem comprovar qui es l'administrador del sistema (adm).

<img width="706" height="740" alt="image" src="https://github.com/user-attachments/assets/a5b16367-462e-4342-a20d-1d20b59cf1d6" />

sudo nano /etc/shadow

Trobem per a cada usuari, el password (encriptat) que té. Al final de la línia trobem la caducitat de la contrasenya (és a dir, podem establir quan s'ha de canviar), saber fa quan no es canvïa i si s'ha de canviar, etc.

<img width="706" height="740" alt="image" src="https://github.com/user-attachments/assets/2e7a450a-ef39-41ab-9584-82fff22754cf" />

sudo nano /etc/gshadow

Passwords de grup. Hi ha una diferència respecte al group ja que veiem tots els usuaris que formen un grup, sent l'únic lloc on veurem qui es l'administrador d'un grup concret. Només es pot posar un administrador.

<img width="706" height="740" alt="image" src="https://github.com/user-attachments/assets/72795737-c7dc-4dd3-bef9-b04a73917b19" />

### Comandes bàsiques

adduser xyz, on xyz és el nom d'usuari que tindrà el compte que volem crear.

<img width="562" height="349" alt="image" src="https://github.com/user-attachments/assets/c34d1f22-f191-4226-84e1-733aefae1939" />

Aquest usuari no tindrà carpeta home fins que no iniciï sessió. Si ho fa llavors es crearan automàticament.

<img width="637" height="447" alt="image" src="https://github.com/user-attachments/assets/b71f2e41-95ef-4f70-9adc-4f7466b3f915" />

Amb useradd xyz, on xyz és el nom d'usuari que tindrà el compte que volem crear, crearem un usuari amb menys privilegis.

<img width="496" height="113" alt="image" src="https://github.com/user-attachments/assets/2aa7dad7-e2cc-41de-8dd5-a36c0392d47e" />

Degut a això la terminal que tindrà l'usuari serà sh. Podem canviar-ho al bash (tot i que l'usuari funcionaria sense fer això).

<img width="599" height="61" alt="image" src="https://github.com/user-attachments/assets/d729e8c1-e2a4-4c0a-beef-1ec8b012dcad" />

Creem la carpeta home del usuari (useradd no crea la carpeta).

<img width="640" height="135" alt="image" src="https://github.com/user-attachments/assets/f97dd16d-9a7b-4c3b-bb99-533cc286fd42" />

Haurem d'assignar la propietat de la carpeta a l'usuari creat.

<img width="656" height="147" alt="image" src="https://github.com/user-attachments/assets/646688d8-2d45-4f69-bfc5-68b5fea605cd" />

Afegim usuaris al grup users. Els borrem. Afegim usuaris al grup sudo.

<img width="893" height="753" alt="image" src="https://github.com/user-attachments/assets/82d5ee29-a7c2-4260-941e-b6950d47041a" />

Podem borrar usuaris sense borrar la seva carpeta home amb deluser xyz, on xyz és el nom d'usuari a borrar.

<img width="457" height="98" alt="image" src="https://github.com/user-attachments/assets/09d95bc5-b5d0-4c07-be30-ebfd9bb49791" />

Per borrar usuaris borrant la seva carpeta home ho farem amb userdel -r xyz, on xyz és el nom d'usuari a borrar.

<img width="611" height="74" alt="image" src="https://github.com/user-attachments/assets/f66ab04f-bed5-4132-9836-3abe94c1d96b" />

Per bloquejar usuaris ho farem amb usermod -L xyz, on xyz és el nom d'usuari a bloquejar.

<img width="901" height="114" alt="image" src="https://github.com/user-attachments/assets/92233318-a8d5-4743-ad2e-9c820b20ff09" />

Per desbloquejar-ho ho fem amb usermod -U xyz.

<img width="479" height="41" alt="image" src="https://github.com/user-attachments/assets/425b756b-21c6-4969-ab67-11c90bebff94" />

Per canviar el nom a un grup ho fem amb groupmod -n (nom_nou) (nom_vell). Eliminem el grup amb groupdel xyz.

<img width="509" height="184" alt="image" src="https://github.com/user-attachments/assets/9d37a023-cba6-4470-85a6-53f9c3065ef3" />

Per afegir usuaris a un grup ho podem fer de tres maneres diferents.

Amb adduser (nom_usuari) (nom_grup)

<img width="496" height="107" alt="image" src="https://github.com/user-attachments/assets/90043f8d-31ae-4d20-91e0-8cea7790352a" />

Amb gpasswd -a (nom_usuari) (nom_grup)

<img width="505" height="41" alt="image" src="https://github.com/user-attachments/assets/696b3703-fc87-44f0-b9fa-e2a9d7be6829" />

Amb usermod -a -G (nom_grup) (nom_usuari)

<img width="520" height="19" alt="image" src="https://github.com/user-attachments/assets/c35d53c8-3d2e-416a-9b5a-83f648c43cf1" />

Comprovem que els usuaris s'hagin afegit correctament.

<img width="532" height="56" alt="image" src="https://github.com/user-attachments/assets/46f8f1e2-8824-42ff-b425-29cfa6360eb3" />

Per denominar administrador a un usuari ho fem mitjançant gpasswd -A (usuari) (grup)

<img width="554" height="181" alt="image" src="https://github.com/user-attachments/assets/ee5784cd-5f6b-498b-a81c-2d9ae7ccd203" />

Un cop fet això no podrem eliminar l'admin del grup. Per això haurem d'eliminar el grup.

<img width="592" height="65" alt="image" src="https://github.com/user-attachments/assets/40111a63-bebb-4062-8485-4eecee6bf78e" />

Havent eliminat el grup els usuaris continuaran existint.

<img width="594" height="81" alt="image" src="https://github.com/user-attachments/assets/b3c7da46-440a-49c7-a31c-d5966ee2b25f" />

Comprovem els grups i els usuaris.

<img width="582" height="161" alt="image" src="https://github.com/user-attachments/assets/5ac3f933-2ac9-4c55-b244-ee876d0fe0f4" />


### Personalització comandes adduser i useradd

Creem 4 usuaris aleatoris. Comprovem que s’hagin creat.

<img width="602" height="110" alt="image" src="https://github.com/user-attachments/assets/a58ab7d9-c6b2-42cd-845f-126d32395bc1" />

Creem el grup. Com ens hem equivocat de nom el canviem.

<img width="602" height="97" alt="image" src="https://github.com/user-attachments/assets/0bebd895-11d5-4f99-b993-590773e39d3a" />

Afegim els usuaris als grups de les diferents maneres que hem vist. Comprovem que s’hagin afegit. Despres els tornem a eliminar.

<img width="633" height="165" alt="image" src="https://github.com/user-attachments/assets/8671f247-8983-4fa2-b63d-f311a71754ee" />
<img width="633" height="165" alt="image" src="https://github.com/user-attachments/assets/282f3c65-804b-45fc-800f-6686d526ece9" />

Amb usermod -g (nom_grup) (nom_usuari) modifiquem el grup principal de l’usuari. Un usuari només té un grup principal, però pot formar part de molts de grups.

<img width="633" height="165" alt="image" src="https://github.com/user-attachments/assets/f2e530c5-da8f-464f-9558-9576f6c3cbf6" />

Si intentem esborrar un grup principal d’un usuari no el podrem esborrar.

<img width="633" height="70" alt="image" src="https://github.com/user-attachments/assets/9f5679bf-d3be-4591-8a64-05eef02b0d0f" />

**On intervenen el les comandes d'usuaris?**

_A adduser;_

/etc/skel
/etc/adduser.conf
/etc/login.defs

_A useradd;_

/etc/login.defs
/etc/default/useradd

A /etc/skel/ tot el que posem en aquest directori es copiarà a la carpeta home del usuari creat amb adduser.

<img width="540" height="373" alt="image" src="https://github.com/user-attachments/assets/e993c7a1-78e7-42eb-bb16-e34fc9a6094b" />

Podem establir (a /etc/adduser.conf) que, per cada usuari creat, la seva home no estigui a /home sinó que estigui a /var (per exemple).

<img width="647" height="246" alt="image" src="https://github.com/user-attachments/assets/e31c607f-0850-4d5f-b211-52849b0cf659" />

Podem canviar (a /etc/adduser.conf) també el ID del grups i el dels usuaris nous que es crearan.

<img width="692" height="173" alt="image" src="https://github.com/user-attachments/assets/a226ef70-4796-49fa-b76f-c8e4f333d4c9" />

A /etc/login.defs podem, per exemple, configurar la caducitat de les contrasenyes.

<img width="730" height="189" alt="image" src="https://github.com/user-attachments/assets/80dc55d6-2d6b-40b4-b45f-de318ae225d1" />

Comprovem que els canvis que hem fen s'han aplicat correctament. Provem a crear un uusari nou amb adduser.

Carpeta home a /var.

<img width="730" height="189" alt="image" src="https://github.com/user-attachments/assets/ddaadc22-9fc1-4135-848b-bf1d025b1730" />

User i grup ID.

<img width="731" height="65" alt="image" src="https://github.com/user-attachments/assets/4404afef-c542-4779-bd0a-4cb916fc91b6" />

Caducitat de contrasenya.

<img width="731" height="65" alt="image" src="https://github.com/user-attachments/assets/88cacc15-d04b-4aee-bbc2-98ac18a443b1" />

Comprovem que s'han creat els arxius que hem configurat a /etc/skel a la carpeta home del usuari.

<img width="731" height="189" alt="image" src="https://github.com/user-attachments/assets/cffe4f12-c05f-44bd-b8c5-f90cbf3e8a79" />

A /etc/default/useradd canviem el terminal de SH a BASH.

<img width="731" height="189" alt="image" src="https://github.com/user-attachments/assets/022df3ae-8758-4b9e-a0ea-acde66e7379e" />

Comprovem que s'hagi canviat el terminal.

<img width="731" height="189" alt="image" src="https://github.com/user-attachments/assets/58d94830-a08d-4903-94e1-03890475ecf9" />

Configurem l'ubicació predeterminada del terminal quan l'usuari inicie sessió a /etc/skel/.profile

<img width="731" height="527" alt="image" src="https://github.com/user-attachments/assets/6737b6a0-89f7-4aae-bba0-89c7dae2d8e4" />

A /etc/skel/.bashrc podem configurar un aliar per executar una comanda només amb un shortcut.

<img width="732" height="228" alt="image" src="https://github.com/user-attachments/assets/4713a8cf-eb5e-4fcc-bbc3-9c1019186802" />

A /etc/skel/.bash_logout podem configurar que, cada vegada que l'usuari faci logout s'elimini (per exemple) la carpeta d'imatges.

<img width="732" height="228" alt="image" src="https://github.com/user-attachments/assets/a0ece6eb-854b-4df5-b928-f40409a198a6" />

### Configurem els arxius .bashrc, .bash_logout i .profiles

Colorejem el prompt a .bashrc.

<img width="688" height="118" alt="image" src="https://github.com/user-attachments/assets/bcf79dde-e408-4a71-a19c-5d894077a1bf" />

Afegim un missatge de comiat i neteja del terminal.

<img width="688" height="118" alt="image" src="https://github.com/user-attachments/assets/d7113fe6-ee5e-4256-acc2-9b726ac5f431" />

Afegim variables d'entorn i PATH millorat.

<img width="688" height="118" alt="image" src="https://github.com/user-attachments/assets/673b522b-5e39-4fff-993b-2d768546ae88" />

Apliquem els canvis.

<img width="688" height="118" alt="image" src="https://github.com/user-attachments/assets/d2619f80-0ff0-4511-a76d-476c8460977d" />


### Gestió de permissos

#### Permissos UOG

Creem una carpeta i un arxiu de prova. Després, donem propietat a l'usuari nick de tots els arxius i subcarpetes que hi ha dins de la carpeta prova.

<img width="536" height="387" alt="image" src="https://github.com/user-attachments/assets/8ff62e27-80be-4829-8a40-cb2007aa5f77" />

Donem tots els permisos al propietari, lectura i execució al grup, i cap accés a la resta d'usuaris amb chmod 750.

<img width="514" height="277" alt="image" src="https://github.com/user-attachments/assets/f003e62c-c73b-4a2c-925f-c473d3aead39" />

Assignem l'usuari i el grup nick a la carpeta palomes i a tot el seu contingut. Després canviem el grup propietari de la carpeta palomes i de tot el seu contingut al grup paloma.

<img width="517" height="59" alt="image" src="https://github.com/user-attachments/assets/a9fab930-6d5f-47c1-a5b3-5ed714faa39a" />

Afegim i després es retirem el permís de lectura per a la resta d'usuaris (altres) sobre la carpeta palomes. Comprovem els canvis aplicats.

<img width="514" height="277" alt="image" src="https://github.com/user-attachments/assets/4f99f629-e5e7-438e-945e-dfced3717b53" />

Verifiquem que l'usuari nick pot crear fitxers al directori, mentre que comprovem que l'usuari cire té denegats els permisos per escriure o esborrar res.

<img width="577" height="432" alt="image" src="https://github.com/user-attachments/assets/d5baa227-033b-4ac8-9562-7d29f0357820" />

Verifiquem que l'usuari ferran no té permís per entrar al directori palomes ni per llistar-ne el contingut.

<img width="610" height="208" alt="image" src="https://github.com/user-attachments/assets/eef74c31-9cf4-42fb-8402-422cd6d8e85c" />

Afegim els usuaris ferran i deivy al grup paloma i atorguem permís d'escriptura al grup sobre la carpeta palomes.

<img width="493" height="239" alt="image" src="https://github.com/user-attachments/assets/a13219fd-a302-4bb9-8858-d267f99e3668" />

Verifiquem que l'usuari deivy pot crear fitxers al directori, però comprovem que l'usuari ferran no té permís per esborrar l'arxiu que ha creat el seu company.

<img width="579" height="338" alt="image" src="https://github.com/user-attachments/assets/98184961-f3b3-43c2-b091-be771efcb74b" />

Llistem els detalls dels permisos i propietaris dels fitxers, i comprovem que l'intent d'esborrar l'arxiu ddd falla perquè aquest no existeix.

<img width="500" height="271" alt="image" src="https://github.com/user-attachments/assets/aa8d566e-6c94-4896-8cc9-b2e05f08e226" />

Assignem el permís especial "Sticky Bit" i accés total per al grup a la carpeta palomes, verificant que ara apareix una "T" al final de la línia de permisos.

<img width="586" height="471" alt="image" src="https://github.com/user-attachments/assets/3bed13c0-4fbb-447b-8773-ad49bc907810" />

#### Permissos ACL

Creem una carpeta compartida amb accés total (777) i generem un arxiu al seu interior amb permisos restringits (640) perquè la resta d'usuaris no hi puguin accedir.

<img width="548" height="183" alt="image" src="https://github.com/user-attachments/assets/9c61bbfa-81b0-457f-95a0-01282bca0aa4" />

Donem permisos concrets a l'usuari roig perquè pugui llegir i escriure al fitxer proves2.

<img width="662" height="27" alt="image" src="https://github.com/user-attachments/assets/43d7b3a4-0efc-4904-ad50-21989288805c" />

Comprovem amb getfacl que l'excepció s'ha aplicat correctament, veient que l'usuari roig té permisos específics de lectura i escriptura sobre el fitxer.

<img width="490" height="258" alt="image" src="https://github.com/user-attachments/assets/878bddd7-078b-4f57-91c4-4a9c1223a821" />

Comprovem que l'usuari blau no pot accedir al fitxer proves2, rebent un missatge d'error de "Permission denied" en intentar obrir-lo.

<img width="739" height="478" alt="image" src="https://github.com/user-attachments/assets/08857596-1ef6-430d-a5fc-0b755ac7bc75" />

Verifiquem que l'usuari roig pot accedir i editar l'arxiu proves2 sense cap problema, confirmant que els permisos especials (ACL) funcionen correctament.

<img width="739" height="478" alt="image" src="https://github.com/user-attachments/assets/5a432b18-8e15-4e89-aea0-e5daf9e781e8" />

Eliminem tots els permisos especials (ACL) de l'arxiu proves2 per deixar-lo net i tornar al seu estat original.

<img width="504" height="185" alt="image" src="https://github.com/user-attachments/assets/1a0a9217-1d9a-474a-bc28-e4f869574f9a" />

Retirem tots els permisos a l'usuari roig sobre la carpeta compartida mitjançant setfacl, impedint-li qualsevol mena d'accés.

<img width="569" height="54" alt="image" src="https://github.com/user-attachments/assets/6b865ba1-b437-4ba7-b93d-5194e6aa28d4" />

Comprovem que l'usuari roig no pot accedir al directori compartida i rep un missatge de permís denegat en intentar entrar-hi.

<img width="388" height="54" alt="image" src="https://github.com/user-attachments/assets/d2602e87-b0cf-43de-915d-ab8854b7bc7c" />

#### Configuració de màscara


## CÒPIES DE SEGURETAT I AUTOMATIZACIÓ DE TASQUES


## QUOTES D'USUARI


