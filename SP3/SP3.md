/>---
layout: default
title: "SPRINT 3: ADMINISTRACIÓ DE DOMINIS I SEGURETAT"
---

# Part 1: Configuració del Servidor LDAP

## 1.1. Configuració Prèvia del Sistema
Abans d'instal·lar el servei, s'ha configurat la xarxa i el nom de la màquina per assegurar la connectivitat.

**Configuració IP del server, host i hostname:**

<img width="578" height="447" alt="image" src="https://github.com/user-attachments/assets/0cd6e071-fee8-4143-91d0-c928364520fb" />
<img width="810" height="101" alt="image" src="https://github.com/user-attachments/assets/d8764a25-b930-4104-92cf-2bbf4d86f1d7" />

Configurem una IP fixa mitjançant la GUI. Després podem comprovar si s'han aplicat els canvis.

<img width="766" height="85" alt="image" src="https://github.com/user-attachments/assets/4e3c7c5b-3c9a-40ab-8c85-e153776fa5a6" />

Configurem el hostname (el nom de la màquina) a un nom identificador.

<img width="727" height="184" alt="image" src="https://github.com/user-attachments/assets/7af30710-a663-44c3-88f8-7496479766bb" />

A /etc/hosts ja començem a definir el nostre domini "gina.cat".

# Part 2: Instal·lació d'LDAP

## 2.1. Instal·lació

<img width="690" height="384" alt="image" src="https://github.com/user-attachments/assets/08a5fcfb-f588-4aa6-a262-68832ad270f6" />

S'han instal·lat els paquets slapd i ldap-utils. Durant la instal·lació s'ha definit el domini base.

## 2.2. Comprovació

<img width="432" height="273" alt="image" src="https://github.com/user-attachments/assets/806bacd2-75c6-4df2-9744-003e4e970326" />

Amb slapcat comprovem la configuració actual.

# Part 3: Estructura del Directori (OUs)

## 3.1 Estructura lògica
Descarreguem els arxius .ldif per establir l'estructura.

<img width="587" height="179" alt="image" src="https://github.com/user-attachments/assets/f533f6aa-d46f-47bf-b9be-c328bfc96dd6" />

Descomprimim el .zip

# Part 4: Configuració de sldap.

## 4.1 Instal·lació

<img width="587" height="179" alt="image" src="https://github.com/user-attachments/assets/17c2095c-7e51-4cd6-a845-50368c2d860f" />

<img width="824" height="192" alt="image" src="https://github.com/user-attachments/assets/337dc575-3bf3-453f-8708-4b67452a0ea5" />

<img width="723" height="192" alt="image" src="https://github.com/user-attachments/assets/34acf50d-9552-4d91-93a2-d0780418af97" />

<img width="686" height="192" alt="image" src="https://github.com/user-attachments/assets/b9a20a38-7a88-4ec0-af6d-b53f61062f40" />

<img width="723" height="192" alt="image" src="https://github.com/user-attachments/assets/e1bdc469-e3bd-4827-8814-fc9a2bb67d4a" />

<img width="723" height="192" alt="image" src="https://github.com/user-attachments/assets/a0fbbe60-53f5-4ffe-8bca-7b8cebacf84f" />

Un cop hem executat el .ldif podem configurar sldap amb dpkg --reconfigure. Configurem segons les nostres necesitats.

## 4.2 Comprovació

<img width="437" height="259" alt="image" src="https://github.com/user-attachments/assets/99056a18-999a-465e-baf4-f2653d1f8033" />

Comprovem configuracions amb slapcat.

# Part 5: Dominis i UOs

## 5.1 Instal·lació fitxers de configuració

<img width="801" height="211" alt="image" src="https://github.com/user-attachments/assets/bb96b115-0b24-447d-b417-01f9f14ef03f" />

Afegim els fitxers de configuració .ldif descomprimits del .zip.

## 5.2 Estructura dels fitxers. UOs, Grups i Usuaris.

<img width="383" height="114" alt="image" src="https://github.com/user-attachments/assets/76b2bc3f-25d4-486e-b96f-0a77aadd63c6" />

Unitat organitzativa USERS.

<img width="383" height="138" alt="image" src="https://github.com/user-attachments/assets/90a35245-f39c-4c42-940f-2f7445dc5c64" />

Grups.

<img width="383" height="344" alt="image" src="https://github.com/user-attachments/assets/e34fa70f-6989-47d6-849b-eb6a6f331604" />

Usuaris.

## 5.3 Comprovació amb slapcat

<img width="801" height="800" alt="image" src="https://github.com/user-attachments/assets/c617bcea-19e0-44f8-9b84-2517433ab157" />


# Part 6: Configuració al entorn client

## 6.1 Instal·lació

<img width="641" height="188" alt="image" src="https://github.com/user-attachments/assets/988256b5-80e7-4fa4-95b9-719169f213e1" />

Instal·lem els paquets clients del ldap.

## 6.2 Configuració

Configurem els paquets descarregats segons les necessitats del usuari.

<img width="979" height="259" alt="image" src="https://github.com/user-attachments/assets/d9c592c7-d832-4cbf-ad2d-2ed33f41a081" />

<img width="979" height="259" alt="image" src="https://github.com/user-attachments/assets/6032311f-6458-4ce2-bba3-f38aff897929" />

<img width="979" height="259" alt="image" src="https://github.com/user-attachments/assets/4386d064-a82c-4835-81fc-bf78196f2cb0" />

<img width="979" height="259" alt="image" src="https://github.com/user-attachments/assets/c58cdb24-7394-4e7d-9aac-22f96de352dc" />

<img width="979" height="259" alt="image" src="https://github.com/user-attachments/assets/acaafbca-29ff-4862-8b69-1a2a49b60efc" />

<img width="979" height="259" alt="image" src="https://github.com/user-attachments/assets/b6eb9616-6cba-4348-8f6b-edbbc70998d3" />

<img width="979" height="259" alt="image" src="https://github.com/user-attachments/assets/d8d36aaf-d513-4a17-bd24-3f408580436f" />

S'hauria de configurar un usuari sense privilegis, però per aquesta pràctica ho farem amb admin.

## 6.3 Reconfiguració

<img width="890" height="188" alt="image" src="https://github.com/user-attachments/assets/6228ed08-4f62-455e-aae5-9c851ad1673d" />

En cas de trobar-nos amb algún error podem reconfigurar amb dpkg --reconfigure ldap-auth-config

## 6.4 Modificació del fitxer nsswitch

<img width="890" height="405" alt="image" src="https://github.com/user-attachments/assets/d1698fbf-5933-4b85-861d-52c0c1fcf058" />

Afegim ldap compat per què primer vagi a comprovar al ldap per fer l’autenticació.

## 6.5 Modificació del fitxer pam.d/common-session

<img width="890" height="459" alt="image" src="https://github.com/user-attachments/assets/a524b5f1-b00d-493e-abfc-ec9ffd028286" />

Afegim l'última linea al fitxer.

<img width="890" height="459" alt="image" src="https://github.com/user-attachments/assets/83bdeb22-59bb-4fdf-b568-77bd0bd1c6c3" />

Borrem "authtok" en aquest apartat on aparegui.

## 6.6 Modificació fitxer 50-ubuntu.conf

<img width="759" height="106" alt="image" src="https://github.com/user-attachments/assets/6835e1d8-02e4-42fd-972b-bb07843cf7aa" />

Per iniciar sessió gràficament hem d'afegir el greeter. Però per comandes ja podriem fer-ho sense afegir això.

## 6.7 Prova d'inici de sesssió.

<img width="474" height="82" alt="image" src="https://github.com/user-attachments/assets/10b28b36-2135-4ace-88d5-cdfcb4671088" />

Intentem iniciar sessió per terminal

<img width="474" height="231" alt="image" src="https://github.com/user-attachments/assets/77991fcf-1aee-4c1b-b01d-4febe26cb658" />

<img width="474" height="231" alt="image" src="https://github.com/user-attachments/assets/d617d0a2-406b-42e0-8dae-878af2bff54a" />

Iniciem gràficament.

# Part 7: Instal·lació de Apache Directory Studio

## 7.1 Instal·lació, configuració i creació d'usuari en ADS.

<img width="630" height="78" alt="image" src="https://github.com/user-attachments/assets/2ea2e84e-5dce-49e2-854b-ef97cf42f258" />

Instal·lem JAVA. Després comprovem que s'ha instal·lat correctament amb java -version.

<img width="761" height="210" alt="image" src="https://github.com/user-attachments/assets/d9104878-b9da-46d2-85f2-34980bb9da7a" />

Descarreguem el paquet tar.gz de la pàgina oficial. El descomprimim.

<img width="872" height="116" alt="image" src="https://github.com/user-attachments/assets/0ca25964-0601-4840-b988-17ca2d95619c" />

Copiem el descomprimit a la ruta /opt.

<img width="924" height="35" alt="image" src="https://github.com/user-attachments/assets/d34998fd-2da1-46b2-8243-7a8fdaf6aa09" />

Donem permissos 

<img width="934" height="54" alt="image" src="https://github.com/user-attachments/assets/9b84af3e-25d6-4b87-ac3e-43478af8ac02" />

<img width="906" height="381" alt="image" src="https://github.com/user-attachments/assets/b4c6e328-2b7d-406f-b8d5-81f408d25b72" />

Comprovem la ubicació de Java, descomentem aquestes dues linies de l'arxiu ini i editem segons la ubicació. Ens hem de fixar en la versió de java que tenim instal·lada.

<img width="700" height="36" alt="image" src="https://github.com/user-attachments/assets/0542f903-9b2a-407f-be77-2d7aad7bcc6a" />

Anem a la carpeta /usr/share/applications i creem un archiu apachedirectorystudio.desktop per tenir un accés directe a la interficie gràfica.

<img width="727" height="39" alt="image" src="https://github.com/user-attachments/assets/b82d5b98-fd9c-48e6-9f16-848241fbd489" />

Otorguem permissos d'escriptura al arxiu i el editem.

<img width="906" height="186" alt="image" src="https://github.com/user-attachments/assets/9e7dd839-1b89-4dea-bccc-2d4e5f2fc4df" />

Afegim la informació de la aplicació. Desem i surtim.

<img width="383" height="39" alt="image" src="https://github.com/user-attachments/assets/126a62b2-4d9d-416b-9cd8-8e585699ebce" />

Executem aquesta comanda per tornar al mode desktop o premem Ctrl + Alt + F1.

<img width="1098" height="573" alt="image" src="https://github.com/user-attachments/assets/4a8cc620-1fcb-4fb4-aa7c-8e296e5241ed" />

<img width="964" height="753" alt="image" src="https://github.com/user-attachments/assets/0b885232-b8dd-4b75-883a-9fbbb999166b" />

Anem al calaix d'aplicacions i trobarem la drecera. Iniciem el programa

<img width="495" height="367" alt="image" src="https://github.com/user-attachments/assets/b02844b1-8df8-47fb-a490-be64c6ef9ad0" />

Anem al desplegable de LDAP i creem una nova connexió.

<img width="587" height="275" alt="image" src="https://github.com/user-attachments/assets/50bd734c-18b7-41ba-b23d-218b7664482a" />

Afegim la IP del server i un nom distintiu.

<img width="468" height="62" alt="image" src="https://github.com/user-attachments/assets/4091e406-a5dd-46a9-bd3f-5a8936d1b0e1" />

Busquem l'usuari administrador del domini.

<img width="597" height="175" alt="image" src="https://github.com/user-attachments/assets/c50642da-c59d-4189-952b-67379e30b0d2" />

<img width="651" height="218" alt="image" src="https://github.com/user-attachments/assets/f47a20fe-1fa3-41fa-97fb-563e5502cd6f" />

Afegim l'usuari amb el domini i comprovem la autenticació.

<img width="913" height="506" alt="image" src="https://github.com/user-attachments/assets/76818219-7cc4-40bb-8c73-4351bf3968f2" />

Un cop establerta la connexió veurem el panell del nostre servidor LDAP.

<img width="715" height="285" alt="image" src="https://github.com/user-attachments/assets/f2e7a953-2e12-4a0a-889b-eb5c9a5a94a1" />

Per crear una UO fem click esquerre sobre dc=gina dc=cat i creem una nova entrada.

<img width="608" height="202" alt="image" src="https://github.com/user-attachments/assets/1ff06e62-05d5-4bc4-843b-9fc3ee386fcf" />

La creem de zero.

<img width="606" height="377" alt="image" src="https://github.com/user-attachments/assets/929cf302-cf23-42b0-b1b1-b89071ce47ce" />

Busquem "organizationalUnit" i l'afegim.

<img width="605" height="250" alt="image" src="https://github.com/user-attachments/assets/a4a958c5-b39b-40aa-9230-5fc94a81af9c" />

En el desplegable busquem "ou" i creem la unitat "classe".

<img width="220" height="176" alt="image" src="https://github.com/user-attachments/assets/aaed4777-2b74-45ce-8cc9-2383ded64cab" />

Ara ja ens apareixerà la unitat organitzativa.

<img width="800" height="194" alt="image" src="https://github.com/user-attachments/assets/eda56bbd-a28c-473c-9a5c-3a30a159af15" />

Per crear un usuari dins de la UO seguim els mateixos passos però des de la nova UO.

<img width="604" height="181" alt="image" src="https://github.com/user-attachments/assets/33867a1f-d1b2-4fc5-b364-03ee4b79551e" />

Sel·lecionem el tipus inetOrgPerson.

<img width="611" height="216" alt="image" src="https://github.com/user-attachments/assets/a6ca2309-4552-4f0e-945e-f2f25d7610b4" />

A RDN sel·lecionem "UID" i creem el nom d'usuari.

<img width="508" height="403" alt="image" src="https://github.com/user-attachments/assets/2dd77004-4cc6-4150-949e-3e61f779b7c7" />

Un cop configurem els paràmetres del usuari podem configurar una contrasenya. Fem click esquerrre i fem "New Attribute".

<img width="533" height="272" alt="image" src="https://github.com/user-attachments/assets/cd6fb81f-10c6-4954-b86e-09cc64fd67ef" />

Busquem "userPassword" i fem click sobre Next.

<img width="760" height="458" alt="image" src="https://github.com/user-attachments/assets/8dfcfcc1-6949-4e15-94b7-eeed1d7fdf33" />

Configurem la contrasenya, i per més seguretat, sel·lecionem el mètode de hash a CRYPT-SHA-512 per no guardar el text en pla.

<img width="602" height="373" alt="image" src="https://github.com/user-attachments/assets/575cb101-d6cd-4acb-b46d-a9ea81c635ab" />

Ara ja tenim l'usuari configurat. Ja podem acabar.

<img width="675" height="343" alt="image" src="https://github.com/user-attachments/assets/885c5ea2-a011-46bc-ade2-31817cb68bfc" />

Podem comprovar que ja apareix l'usuari.

## 7.2 Comprovació en entorn client.

<img width="433" height="169" alt="image" src="https://github.com/user-attachments/assets/901613d0-6d17-4b82-8bd1-00f36f11e1ec" />

<img width="378" height="525" alt="image" src="https://github.com/user-attachments/assets/7c7bc1dd-454f-4ce4-b1a9-7c4795b5ea87" />

Fem click sobre "Not listed?" i escrivim l'usuari que hem creat.
