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

Distingim entre un servei, que és el programa que s'executa en segon pla (conegut com a dimoni), i el procés, que correspon a l'execució activa de les tasques d'aquest programa al sistema.

Utilitzem la comanda pstree per visualitzar l'estructura de processos en forma d'arbre jeràrquic; afegim l'opció -p per veure els identificadors (PID) de cada tasca i especifiquem l'usuari per filtrar i veure només la seva activitat.

<img width="866" height="670" alt="image" src="https://github.com/user-attachments/assets/7916a622-9a7c-41c4-8fd3-8d2f80e9fd4d" />

Tenim un altre procés de terminal obert en el usuari razvan i amb pstree el podem veure.

<img width="866" height="670" alt="image" src="https://github.com/user-attachments/assets/4c2cb0a2-8ed3-42a5-af1a-249a336fce0a" />

D'altra banda, podem aplicar la comanda grep per filtrar l'arbre de processos i focalitzar-nos únicament en aquells que contenen la paraula "terminal". Això ens permet identificar ràpidament el gnome-terminal i els seus processos fills.

<img width="866" height="670" alt="image" src="https://github.com/user-attachments/assets/e9262040-e75c-4ca5-a14d-3a65b0b78750" />

El pstree mostra la jerarquia visual; el ps aux detalla informació tècnica com el PID i la memòria.

<img width="866" height="670" alt="image" src="https://github.com/user-attachments/assets/8a63ca3f-a2be-469a-96a1-782a6c97521a" />

Podem filtrar els processos amb | grep (nom), per exemple, ps aus | grep terminal

<img width="810" height="135" alt="image" src="https://github.com/user-attachments/assets/75940523-9f1e-44b4-8092-9ce992089bf1" />

Amb grep filtrem la sortida per mostrar només els processos propietat d'un usuari específic, com "razvan".

<img width="877" height="266" alt="image" src="https://github.com/user-attachments/assets/8b1ceacb-f3ff-412e-b04b-8bc9e53a62f5" />

Top monitoritza el rendiment en temps real, classificant els processos segons l'ús intensiu de CPU i memòria.

<img width="926" height="670" alt="image" src="https://github.com/user-attachments/assets/92253881-eaae-4ff1-a877-4a94d9376334" />

Htop és una alternativa visual i interactiva que facilita cercar (F3) i matar (F9) processos còmodament.

<img width="926" height="670" alt="image" src="https://github.com/user-attachments/assets/f903e15e-9bb8-497e-b1ee-457f4b6af2cb" />

Per buscar un procés, premem F4 i busquem el procés que volem.

<img width="1186" height="629" alt="image" src="https://github.com/user-attachments/assets/3584db2b-db93-4696-bf41-ccbf0607a989" />

Un cop l'hem trobat premem enter. Un cop sel·leccionat premem F9 i enter per matar-lo.

<img width="1186" height="629" alt="image" src="https://github.com/user-attachments/assets/a094a6b9-2eb1-43c0-80fe-b50a44b1ba69" />

També tenim l’alternativa gràfica BTOP. (Igual que HTOP).

<img width="1166" height="670" alt="image" src="https://github.com/user-attachments/assets/86cd95aa-794c-419a-9fcb-9ba2e8a865e8" />

Ctrl + Z atura temporalment l'execució del procés actiu, enviant-lo al segon pla en estat suspès (Stopped). Per comprovar els estats dels processos ho comprovem amb jobs.

<img width="419" height="197" alt="image" src="https://github.com/user-attachments/assets/bab964f4-87a0-4c2c-9378-ab53fc580c4a" />

Per tornar a portar-lo a primer pla executem fg (num_jobs).

<img width="247" height="82" alt="image" src="https://github.com/user-attachments/assets/b3799dfb-85d3-4529-a81c-96bed513044f" />

Ctrl + C envia el senyal SIGINT per interrompre l'execució; jobs verifica si queden tasques actives en segon pla.

<img width="342" height="51" alt="image" src="https://github.com/user-attachments/assets/540350d2-f64c-4240-af6d-f8ac2ae92b07" />

Afegint & enviem el procés al segon pla, recuperant el terminal immediatament i obtenint el seu PID.

<img width="343" height="66" alt="image" src="https://github.com/user-attachments/assets/13bac614-2c71-4424-a622-a1d66eef274d" />

Per donar més prioritat (temporalment i per un procés que s’està executant) (nomes usuari root) fem: renice -n -19 -p [PID]

-19 és màxima prioritat

Amb nice podem establir prioritat a un procés

nice -n -19 [proces]

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

Verifiquem el valor de la màscara (umask) i observem com canvia automàticament quan passem de l'usuari estàndard a l'administrador (root), fent-se més restrictiva.

<img width="480" height="270" alt="image" src="https://github.com/user-attachments/assets/6fb58dd0-524b-4701-84fa-561129411b69" />

Editem el fitxer de configuració /etc/login.defs per establir una màscara (umask) definitiva que s'aplicarà automàticament a tots els usuaris, tant als actuals com als que crearem en el futur.

<img width="480" height="270" alt="image" src="https://github.com/user-attachments/assets/9eb48cdd-f37e-4afe-a3a1-1b41e828da12" />

Editem el fitxer de configuració personal .profile per establir una màscara (umask) que s'aplicarà exclusivament a aquest usuari cada cop que iniciï sessió, sense afectar la resta del sistema.

<img width="480" height="270" alt="image" src="https://github.com/user-attachments/assets/9a782f45-e8be-4b23-a9a3-e0a7393f316d" />

Modifiquem temporalment la màscara (umask) per agilitzar la feina, aconseguint que els nous fitxers i carpetes es creïn directament com a privats sense haver de canviar els permisos manualment després.

<img width="480" height="270" alt="image" src="https://github.com/user-attachments/assets/0f53f45a-615b-4c6f-b442-34acd100ae4f" />

Modifiquem la línia corresponent al fitxer de configuració global login.defs i guardem els canvis per establir la màscara definitiva per a tots els usuaris del sistema.

<img width="480" height="270" alt="image" src="https://github.com/user-attachments/assets/ccc07b6a-27cd-44c3-bb38-e8d8986a01df" />


## CÒPIES DE SEGURETAT I AUTOMATIZACIÓ DE TASQUES

### 1. Teoria de còpies de seguretat. ###

#### 1.1. Què és una còpia de seguerat? ####

Una còpia de seguretat és el **procés sistemàtic de replicació d'actius de dades**(fitxers, bases de dades, sistemes operatius) amb l'objectiu de garantir la integritat i la disponibilitat de la informació. La seva funció principal és permetre la restauració del sistema a un punt anterior en el temps (rollback) després d'un esdeveniment de pèrdua de dades (error humà, corrupció de software, fallada de hardware o ciberatac com el ransomware).

#### 1.2. Tipus de còpies de seguretat. ####

| Tipus | Funcionament | Temps d'Execució (Backup) | Ús d'Emmagatzematge | Velocitat de Restauració (RTO) | Cadena de Recuperació |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Completa**<br>*(Full)* | Copia **totes** les dades seleccionades, hagin canviat o no. | **Lenta**<br>Processa el major volum de dades. | **Alt**<br>Requereix molta capacitat. | **Molt Ràpida**<br>No depèn d'altres fitxers. | 1. Restaurar l'última Còpia Completa. |
| **Incremental** | Copia només les dades modificades des de l'**últim backup de qualsevol tipus**. | **Molt Ràpida**<br>Processa el mínim volum necessari. | **Molt Baix**<br>Màxima eficiència d'espai. | **Lenta**<br>Requereix processar múltiples fitxers. | 1. Última Completa.<br>2. Totes les Incrementals seqüencials fins al punt desitjat. |
| **Diferencial** | Copia les dades modificades des de l'**últim backup COMPLET**. És acumulativa. | **Moderada**<br>Més lenta que la incremental a mesura que passa el temps. | **Moderat**<br>Major que la incremental (redundància de canvis). | **Ràpida**<br>Més senzilla que la incremental. | 1. Última Completa.<br>2. Només l'última Diferencial. |

### 2. Comandes per backup. ###

#### 2.1. CP (Copy) ####

És la comanda estàndard de sistemes UNIX/Linux per a la replicació d'arxius i directoris a nivell de sistema de fitxers. Es considera una **còpia no intel·ligent** perquè, per defecte, **llegeix l'origen i reescriu completament el destí sense analitzar si les dades ja existeixen o si han estat modificades.** La seva operativitat es limita generalment a l'àmbit local (o unitats muntades) i resulta ineficient per a polítiques de backup recurrents, ja que no optimitza l'ample de banda ni els temps d'E/S (Entrada/Sortida), consumint recursos innecessaris en tornar a copiar dades idèntiques.

#### 2.2. rSync (Remote Sync) ####
És una eina avançada de sincronització de fitxers dissenyada per treballar de manera eficient tant en entorns **locals com remots** (generalment via SSH). La seva característica principal és la **intel·ligència en la transferència**: utilitza un algoritme de "delta encoding" que compara els fitxers d'origen i destí per identificar blocs de dades modificats. Això **permet transmetre únicament les diferències (i no el fitxer sencer)**, reduint dràsticament el consum d'ample de banda i el temps d'execució, convertint-la en l'estàndard de facto per a còpies de seguretat incrementals i miralls (mirroring) de servidors.


#### 2.3. DD (Data Duplicator) ####
Més que una eina de còpia de fitxers, és una utilitat de **clonació a baix nivell** que opera directament sobre els blocs del dispositiu, ignorant l'estructura del sistema de fitxers. **Realitza una còpia exacta bit a bit** (raw copy) des d'un dispositiu d'entrada a un de sortida. Això significa que **clona absolutament tot: la taula de particions, el sector d'arrencada (MBR/GPT), les dades i fins i tot l'espai buit o esborrat.** És l'eina utilitzada per crear imatges forenses, còpies de seguretat completes del sistema operatiu o clonar discos durs sencers, garantint una rèplica idèntica a l'original

### 3. Posada en pràctica de les comandes de backup. ###

En la màquina virtual creem dues unitats d'1GB cadascuna.

<img width="735" height="482" alt="image" src="https://github.com/user-attachments/assets/b51ff3a5-89ec-4ace-8754-a71d1831e87e" />

Els donem format ext4 als dos i li fem només una partició a cada disc.

<img width="735" height="482" alt="image" src="https://github.com/user-attachments/assets/62007772-9585-4351-94af-e3f4e21482e6" />

Creem una carpeta que copiarem. Montem la unitat sdb1 en una carpeta *copies* a */var*.

<img width="735" height="295" alt="image" src="https://github.com/user-attachments/assets/8f866957-a3a2-49e8-867d-b50367082d29" />


#### 3.1. CP ####

Realitzem una còpia recursiva de les dades i verifiquem que, encara que esborrem la carpeta original després de crear un fitxer de prova, la còpia de seguretat es manté intacta i independent al nou directori.

<img width="735" height="295" alt="image" src="https://github.com/user-attachments/assets/0b9f1651-c6a5-4580-8352-19f724d70f14" />

#### 3.2. rSync ####

Utilitzem cp per fer còpies directes de fitxers, mentre que fem servir rsync per sincronitzar carpetes de manera intel·ligent, actualitzant només les dades que han canviat.

<img width="641" height="399" alt="image" src="https://github.com/user-attachments/assets/fe1bbc63-56ee-48d9-9cf9-b0f02138abe7" />

#### 3.3. DD ####

Es clona la partició sdb1 a sdc1 mitjançant dd i es verifica la integritat de la còpia amb md5sum.

<img width="732" height="483" alt="image" src="https://github.com/user-attachments/assets/b29ec318-8009-4b81-834a-6f8c9de39fa0" />


### 4. Posada en pràctica de programes de backup. ###

#### 4.1. Déjà Dup ####

#### 4.2. Duplicity ####

### 5. Teoria d'automatització de scrips, cron i anacron. ###


##### 5.1. Cron: #####

- Funciona com un rellotge de precisió. Pots programar tasques al minut exacte (ex: "Dimarts a les 14:05").

- Punt feble: Si a les 14:05 l'ordinador està apagat, el Cron no se n'assabenta. Quan encenguis l'ordinador a les 15:00, la tasca no s'executarà fins al dimarts següent.

- Ús: Servidors que estan encesos 24/7 o tasques que han de passar sí o sí a una hora (com enviar un informe al final de la jornada).

##### 5.2. Anacron: #####

- No entén de minuts o hores exactes, sinó de freqüència (1 dia, 7 dies, 1 mes).

- Punt fort (Persistència): Guarda un fitxer amb la data de l'última execució. Si tens programada una tasca "diària" i tens l'ordinador apagat 3 dies, tan bon punt l'encenguis, l'Anacron veurà que la data ha caducat i executarà la tasca pendent immediatament.

- Ús: Manteniment del sistema (rotació de logs, actualització de bases de dades locate) en ordinadors personals o portàtils que s'apaguen cada nit.

### 6. Posada en pràctica d'automatització.

#### 6.1. Cron ####

Documents importants: /etc/crontab

Aquest fitxer gestiona les tasques programades de tot el sistema. A diferència dels cron personals, aquí cal especificar l'usuari (ex: root) que executarà la comanda.

<img width="732" height="483" alt="image" src="https://github.com/user-attachments/assets/0f481bfc-3a8d-43d9-994e-319e50d9cb75" />

Amb crontab -u [usuari] -e editem la taula de programació personal d'un usuari concret. A diferència de /etc/crontab, aquí no cal especificar l'usuari a cada línia perquè ja estem dins el seu fitxer.

<img width="732" height="483" alt="image" src="https://github.com/user-attachments/assets/57b5dd14-afc1-42ff-86f7-ea7e4b8d783a" />

<img width="732" height="483" alt="image" src="https://github.com/user-attachments/assets/b75a8678-812c-440b-932f-279abb8276fe" />

Amb crontab -e -u [usuari] podem programar scripts que s'executaran automàticament

<img width="732" height="165" alt="image" src="https://github.com/user-attachments/assets/6e1c9217-fc43-44fa-a277-66d9d4efcb3e" />

Diferents direcoris de manteniment amb tasques automatizades a executar.

#### 6.2. Anacron ####

<img width="732" height="482" alt="image" src="https://github.com/user-attachments/assets/2d0b89b8-0c50-4888-9603-05c0b14a5e27" />

Aquest fitxer controla la periodicitat de les tasques de manteniment. A diferència del cron normal, aquí no hi ha hores exactes, sinó que es defineix una freqüència en dies (1, 7, monthly) i un retard en minuts (5, 10, 15) perquè l'ordinador no es col·lapsi executant-ho tot just arrencar.

S'utilitza la comanda run-parts per executar, d'un sol cop, tots els scripts que hi hagi dins els directoris de manteniment (/etc/cron.daily, /etc/cron.weekly, etc.).

#### 6.3. Creació d'scripts ####

<img width="972" height="482" alt="image" src="https://github.com/user-attachments/assets/d1efd35c-4079-4af0-a824-c88d44e7a143" />

Aquest script de Bash ens permet automatitzar la creació de còpies de seguretat. Ens facilita empaquetar tot el contingut de la carpeta Documents en un arxiu únic a l'escriptori. A més, ens assegura mantenir un històric ordenat, ja que afegeix automàticament la data i l'hora actuals al nom del fitxer.

<img width="650" height="486" alt="image" src="https://github.com/user-attachments/assets/0a024f07-692d-4cb7-8689-be4ef314f952" />

Amb la comanda chmod +x, assignem permisos d'execució al nostre script copies.sh.  Finalment, verifiquem l'estat amb ls -l, confirmant que ara disposa dels permisos necessaris-

<img width="671" height="114" alt="image" src="https://github.com/user-attachments/assets/68f08bf6-ea74-4986-aafc-b5c15bc226de" />

Dins el directori Documents, generem fitxers de mostra. Creem dos arxius buits (PT1.Varas i PT2.Varas) per simular contingut.

<img width="711" height="480" alt="image" src="https://github.com/user-attachments/assets/93754185-18cb-4bcd-82c5-d9bda06aa941" />

Modifiquem l'arxiu /etc/crontab per programar la tasca automàtica. Afegim una línia que ens permet executar l'script el dia 9 de cada mes a les 13:35. Definim l'usuari root i la ruta de l'arxiu per assegurar que el sistema trobi i llanci la còpia de seguretat puntualment.

<img width="713" height="585" alt="image" src="https://github.com/user-attachments/assets/e68fd08d-bb8a-46ba-8ba4-82bec144fde8" />

Passats uns minuts, obrim l'arxiu resultant per assegurar-nos que s'ha completat correctament. 

<img width="771" height="218" alt="image" src="https://github.com/user-attachments/assets/0673947f-beca-4062-9a58-a9e73245dd39" />

Finalment, copiem l'script dins de /etc/cron.daily, això ens garanteix que la còpia es farà un cop al dia, recuperant l'execució encara que l'ordinador estigués apagat en el moment previst.

<img width="749" height="302" alt="image" src="https://github.com/user-attachments/assets/05ed0fe2-0769-4aad-bc57-4449bb2a0c73" />

Editem el fitxer /etc/anacrontab per controlar quan s'executen les tasques pendents. A la primera línia (1 1 cron.daily), configurem que l'script s'executi una vegada al dia (1) amb un retard d'un minut (1) després de l'inici del sistema.

<img width="749" height="302" alt="image" src="https://github.com/user-attachments/assets/c6c304df-03c0-44d0-8460-0cd73d760c5d" />

Consultant el fitxer /var/spool/anacron/cron.daily, verifiquem la marca de temps de l'última execució (20251209). Aquest registre permet a Anacron saber que la tasca diària ja s'ha completat i no cal tornar-la a executar.

## QUOTES D'USUARI/DE DISC

### Definició

Una quota d'usuario (o de disc) és un mecanisme d'administració de sistemes que serveix per limitar l'espai d'emmagatgematge o el nombre d'arxius que un usuari (o grup) pot utilitzar en un sistema de fitxers. En entorns compartits amb diversos usuaris aquesta eina és fonamental per evitar que un sol usuari ompli tot el disc dur i bloquegi el sistema per a la resta.

En les quotes d'usuari tenim diferents conceptes clau que hem de saber abans de configurar res; _Soft Limit_, _Hard Limit_ i _Grace Period_. 

#### Soft Limit ####

És un limit d'avís. L'usuari pot superar-lo momentàniament però no per sempre. Aquest rebrà advertències que s'està quedant sense espai. Per exemple; si a Movistar tinc contractats 70GB d'internet de dades mòbils, al consumir 65GB m'enviaran un SMS indicant-me que estic a punt de gastar-me la totalitat del meu tràfic disponible d'internet. 

#### Hard Limit ####

És el límit absolut. L'usuari ha arribat al màxim permès i el sistema bloqueja l'escriptura immediatament si s'intenta superar. No ens permetrà guardar ni un byte més. En la posada a pràctica més abaix ho comprovarem. Seguint l'analogia del _Soft Limit_, ara ja ens hem gastat els 70GB i Movistar ens ha bloquejat la connexió a Internet.

#### Grace Period ####

O període de gràcia en català, és el temps que el sistema dona a l'usuari que ha superat el _Soft Limit_ perquè esborri arxius i torni a estar per sota d'aquest límit. Si passa el temps i no ho ha arreglat, el _Soft Limit_ es converteix en un Hard Limit.

### Posada en pràctica

<img width="737" height="485" alt="image" src="https://github.com/user-attachments/assets/8b16318c-8ac5-49b7-a8b8-7fc83e85c9d8" />

Comprovem els discs que tenim a la nostra VM. Escollim el /dev/sdc1 ja que no l'hem fet servir en la pràctica anterior.

<img width="737" height="485" alt="image" src="https://github.com/user-attachments/assets/6d67895e-7d4d-4ef7-861c-a8e32d467fbd" />

Donem format al disc per fer-lo servir nou.

<img width="737" height="485" alt="image" src="https://github.com/user-attachments/assets/3c41deac-a33a-4b74-9a2c-c66187397776" />

Instal·lem el paquet què ens ajudarà en la nostra feina amb apt install quota.

<img width="737" height="485" alt="image" src="https://github.com/user-attachments/assets/2b785a77-dddb-4e0b-818f-72eaf7ad8ed9" />

<img width="737" height="485" alt="image" src="https://github.com/user-attachments/assets/ee1871e3-ff81-4627-988f-8cece80e74d2" />

Un cop formatat, montem el disc a l'ubicació /mnt/dades_usuaris. Haurem de crear la carpeta dades_usuaris abans de fer el muntatge. Ens hem d'assegurar que configurem correctament els paràmetres ja que sinó ens saltarà el mode d'emergència i no podrem arrancar el SO.

<img width="737" height="485" alt="image" src="https://github.com/user-attachments/assets/72d71b1b-0bfc-4cd0-aa23-fd991e9b54ee" />
<img width="737" height="485" alt="image" src="https://github.com/user-attachments/assets/182eb799-9502-46a2-8c84-f7666abfa07e" />

Podem comprovar que el disc s'ha montat correctament. Amb el ls, si veiem l'arxiu _lost+found_ significa que està montat. D'altra banda podem comprovar els muntatges dels sistema i comprovar que veiem el nostre disc.

<img width="737" height="485" alt="image" src="https://github.com/user-attachments/assets/4c424d1f-506f-4453-9001-e45a980d14ff" />

Les quotes d'usuari han vingut activades per defecte, però en el cas que no fos així les haurem d'activar amb la comanda quotaon. En la imatge les he desactivat i tornat a activar per veure com es faria.

<img width="737" height="485" alt="image" src="https://github.com/user-attachments/assets/bc313680-175d-48d6-8c2b-609a6415b56b" />

Amb les comandes de la imatge podem comprovar la quota de disc de cada usuari. Amb quota -u [usuari] podem verificar la quota a un usuari especific i amb repquota [particio] podem veure tots els usuaris i la seva quota respectivament.

<img width="728" height="490" alt="image" src="https://github.com/user-attachments/assets/f7bb5350-7c3c-4937-a358-0dd626557aba" />

Amb edquota -u usuari podem configurar els límits. Podem configurar els tres conceptes mencionats a la definició; _Soft Limit_, _Hard Limit_ i _Grace Period_. 

<img width="728" height="490" alt="image" src="https://github.com/user-attachments/assets/4efd98bd-9c90-4fb3-8a66-43433a2f79eb" />

Com l'usuari ha sobrepassat el _Hard Limit_, el quota no l'ha deixat escriure més. L'arxiu s'ha tallat fins la quantitat d'espai que li quedava.

<img width="728" height="490" alt="image" src="https://github.com/user-attachments/assets/f5026346-0aa0-47db-b907-90216405640c" />

Si desactivem el quota podem comprovar que ara l'usuari ja pot fer servir l'espai que vulgui en el disc dur.

<img width="728" height="490" alt="image" src="https://github.com/user-attachments/assets/b9f6622a-9878-4835-a7b1-534f31175845" />

D'altra banda, amb edquota -t podem establir una configuració de quota per a tots els usuaris.

<img width="728" height="490" alt="image" src="https://github.com/user-attachments/assets/24a665ce-5e5f-4197-9ffb-a2233ba62c96" />

Configurem la quota a 15 i després comprovem que els canvis s'han aplicat correctament.


