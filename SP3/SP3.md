---
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

<img width="361" height="244" alt="image" src="https://github.com/user-attachments/assets/27c7b251-2c51-43a9-9e54-5c1612c89338" />

Fem click sobre "Not listed?", escrivim l'usuari i la contrasenya que hem creat.

<img width="312" height="55" alt="image" src="https://github.com/user-attachments/assets/1adaffae-7bf7-43cc-a85f-080a9f48f965" />

Anem al terminal i executem whoami per veure l'usuari actual.

# Part 8: Activitat.

## - Fes un dpkg-reconfigure slapd al servidor per tal de deixar la base de dades buida i només amb el domini i l’usuari admin creat. Comprova-ho amb un slapcat. ##

<img width="819" height="270" alt="image" src="https://github.com/user-attachments/assets/a07698d9-2479-42f0-8edf-cb36a9cc3f8e" />

Diem que no volem ometre la configuració del server OpenLDAP.

<img width="1263" height="270" alt="image" src="https://github.com/user-attachments/assets/8522b160-ed0e-40f8-b2db-144998ef36c9" />

Configurem el domini gina.cat.

<img width="1263" height="270" alt="image" src="https://github.com/user-attachments/assets/23f3e540-54d9-4fba-8acc-1eb1e4d9fa28" />

El nom de la organització.

<img width="1263" height="270" alt="image" src="https://github.com/user-attachments/assets/1afefd52-70f8-4efb-b6a8-2755d3a15fff" />

Contrasenya d'admin,

<img width="1263" height="270" alt="image" src="https://github.com/user-attachments/assets/e1394f62-7330-48d9-8938-01a423d90c97" />

Li diem que volem que la base de dades s'elimini,

<img width="1263" height="270" alt="image" src="https://github.com/user-attachments/assets/48d08e34-0305-40c3-a26e-c8499742ac5a" />

Movem els fitxers de la base de dades anterior per no causar discrepàncies amb la BD nova.

<img width="757" height="137" alt="image" src="https://github.com/user-attachments/assets/7132f6dd-57b0-4985-a1f1-721f73e0a294" />

Esperem que acabi.

<img width="442" height="232" alt="image" src="https://github.com/user-attachments/assets/24685bbf-6162-4d17-aff2-f21c56beb03b" />

Ja no tenim cap usuari o grups dels que teniem abans creats. 

## -  Descarrega l'arxiu dades_pt10.ldif del moodle i amb la comanda ldapadd carrega els usuaris, grups i uos (Compte que el domini és vesper.cat, hauràs de modificar-lo pel teu). ##

<img width="832" height="753" alt="image" src="https://github.com/user-attachments/assets/e81d91fe-43a3-482d-bffd-e5822d104ab3" />

El domini del meu server és gina.cat, per tant, he de canviar vesper a dc=vesper per dc=gina.

<img width="862" height="280" alt="image" src="https://github.com/user-attachments/assets/788d67fd-fc19-4661-85e7-28e64b8a3ea8" />

Un cop hem guardat d'arxiu executem ldapadd -x -D "cn=admin,dc=gina,dc=cat" -W -f dades_V2.ldif per executar l'arxiu.

## - Fes un altre slapcat per tal de comprovar que les dades s'han carregat correctament. ## 

<img width="767" height="807" alt="image" src="https://github.com/user-attachments/assets/18c8af42-9c31-4850-925c-9b9480687053" />

## 1. Crea un nou usuari directament al domini. ##

<img width="749" height="256" alt="image" src="https://github.com/user-attachments/assets/80919e6e-d187-45c2-8f17-0d730ddd211a" />

Creem un arxiu ldif i definim els paràmetres per a l'usuari joan.

<img width="729" height="84" alt="image" src="https://github.com/user-attachments/assets/311c8268-87fd-4690-b683-80d67731ff78" />

Apliquem l'arxiu que acabem de crear.

<img width="729" height="104" alt="image" src="https://github.com/user-attachments/assets/3773bd93-53e7-4e99-8fc1-df2fb04d769c" />

Comprovem amb slapcat. Podem veure que ja tenim l'usuari joan i la seva carpeta home.

## 2. Crea una nova uo anomenada nòmines. ##

<img width="729" height="104" alt="image" src="https://github.com/user-attachments/assets/3a9034e5-6c08-4e28-9244-5322ed5aac90" />

Creem l'arxiu uo_nomines.ldif amb els paràmetres de la nova UO.

<img width="729" height="104" alt="image" src="https://github.com/user-attachments/assets/a512e05f-0cbb-41d6-bfa8-d455c95ad812" />

Apliquem l'arxiu amb ldapadd.

## 3. Mou l’usuari que has creat dintre de la uo nòmines. ##

<img width="1287" height="80" alt="image" src="https://github.com/user-attachments/assets/8823de63-493f-431e-80ed-04f8aed289e8" />

Amb la comanda ldapmodrdn movem l'usuari joan dins de nòmines. L'últim argument "cn=joan" indica que mantenim el mateix nom relatiu.

<img width="411" height="353" alt="image" src="https://github.com/user-attachments/assets/34b0adc0-dc08-403c-af62-1748ca74c2dd" />

Comprovem amb slapcat.

## 4. Quants grups hi ha al domini gina.cat? ##

<img width="912" height="376" alt="image" src="https://github.com/user-attachments/assets/97cae3d8-654b-4863-a618-bd88d8aea3b0" />

Segons la comanda ldapsearch tenim 2; informatica i administracio.

## 5. Afegeix l’usuari que has creat dintre d’un dels grups del domini. ##

<img width="850" height="116" alt="image" src="https://github.com/user-attachments/assets/bf698a0e-613b-4d7c-b08a-08209d99306a" />

Creem un arxiu indicant que volem modificar el grup de l'usuari joan i l'afegim al grup d'informàtica.

<img width="985" height="90" alt="image" src="https://github.com/user-attachments/assets/e4473348-0f61-439c-8cac-97aa6d45276c" />

L'executem.

## 6. D’un sol cop: Afegeix un nou atribut opcional a l’usuari sergi, modifica el cognom de l’usuari sergi al valor Pallarés. ##

<img width="744" height="139" alt="image" src="https://github.com/user-attachments/assets/163224e9-cc40-4870-8c7e-52e716b49a25" />

Hem d'afegir un atribut opcional (per exemple description) i canviar el cognom (sn) a "Pallarés". Creem l'arxiu ldif.

<img width="962" height="107" alt="image" src="https://github.com/user-attachments/assets/976ae48b-0028-490a-be01-c30075c2fbda" />

L'apliquem.

## 7. Quants usuaris hi ha dintre de la uo rrhh? Quins són? ##

<img width="1020" height="476" alt="image" src="https://github.com/user-attachments/assets/f61276b7-8399-4f8d-9a71-b8987564bcec" />

Amb la comanda ldapsearch li diem que ens mostri tots els usuaris (cn) a la uo rrhh. Tenim 3; xavier, enric i sergi.

## 8. Esborra el gidNumber del grup informàtica. ##

<img width="770" height="81" alt="image" src="https://github.com/user-attachments/assets/e1b24617-649b-4374-9bc0-0404987a670d" />

Creem aquest arxiu ldif indicant que volem esborrar el gidNumber del grup informatica.

<img width="770" height="117" alt="image" src="https://github.com/user-attachments/assets/4304bc98-f3ae-4331-8099-eeefed0114c9" />

No ens haurà funcionat perquè l'objectClass posixGroup obliga a tenir un gidNumber.

## 9. Quantes uos hi ha al domini gina.cat? ##

<img width="973" height="406" alt="image" src="https://github.com/user-attachments/assets/b36f577c-3115-4f59-aa02-e80697e825a0" />

Amb la comanda ldapsearch i indicant-li objectClass=organizationalUnit veurem totes les UOs de gina.cat. Tenim 3; rrhh, departaments i nomines.

## 10. Modifica el cn de Xavier per Francesc Xavier. ##

<img width="1262" height="114" alt="image" src="https://github.com/user-attachments/assets/3214bdac-8aed-40d2-86d5-07b1a49b1e47" />

Això és un canvi de RDN (Relative Distinguished Name). Amb ldapmodrdn ho podrem fer. Un cop executada la comanda, comprovem amb slapcat.

## 11. Esborra la uo nòmines. ##

LDAP no permet esborrar una UO si no està buida. Primer hem d'esborrar (o moure) l'usuari joan que hi ha dins.

<img width="1212" height="39" alt="image" src="https://github.com/user-attachments/assets/910ccf27-6133-4ec5-9b79-80475313f0fa" />

Esborrem l'usuari joan.

<img width="610" height="40" alt="image" src="https://github.com/user-attachments/assets/f39afd51-468c-4b46-a547-f7fe122d8167" />

Comprovem que s'ha esborrat correctament. Com que no ens ha retornat cap informació, ja s'ha esborrat.

<img width="1011" height="76" alt="image" src="https://github.com/user-attachments/assets/206a9402-a3eb-4183-8c67-d31a1b31511a" />

Esborrem la uo nòmines i comprovem que efectivament, s'ha esborrat.

## 12. Mostra els usuaris que tinguin com a grup principal el grup administració. ##

<img width="1070" height="516" alt="image" src="https://github.com/user-attachments/assets/d1a7f231-7daa-4e24-b241-4ba6b362b484" />

El grup Administració té el GID 1002. Cerquem usuaris amb aquest gidNumber. L'usuari que busquem és sergi.

## 13. Quin usuari té el uidNumber 1003? ##

<img width="845" height="246" alt="image" src="https://github.com/user-attachments/assets/3f620532-b381-4be2-849d-f09828fb9442" />

Cap usuari. Al fitxer original els UIDs salten del 1002 (Enric) al 1004 (Sergi).

## 14. Mostra quins són els usuaris on el seu cognom comenci per R i el seu uidNumber sigui més gran que 1003. ##

<img width="931" height="255" alt="image" src="https://github.com/user-attachments/assets/f5145a68-ea75-4faa-bf2a-0e42cd48226f" />

El filtre per "més gran que" (>) no és estàndard en filtres simples, es fa servir "més gran o igual" (>=). Si no haguéssim fet el pas 6 sortiria en Sergi (sn=Reus, uid=1004). En aquest cas no surt res.

## 15. Mostra quins usuaris formen part del grup informàtica o aquells usuaris que tinguis de cognom Pallarés. ##

<img width="1019" height="560" alt="image" src="https://github.com/user-attachments/assets/5e96b40d-f329-4f3b-bdca-ebb1046bb79f" />

El grup informàtica té GID 1001. Filtre: (GID=1001) OR (sn=Pallarés).
Els usuaris buscats són: Francesc Xavier GID 1001, Enric GID 1001 i Sergi GID 1002 (amb cognom Pallarés).

# Part 9: Configuració de SAMBA.

## 9.1 Què és un servidor Samba?

Un **servidor Samba** és un servei que permet **compartir recursos dins d’una xarxa**, especialment:

- **Fitxers**
- **Carpetes**
- **Impressores**

L’objectiu és que diferents ordinadors de la mateixa xarxa puguin accedir a aquests recursos com si fossin comparticions de xarxa normals (per exemple, una carpeta comuna).

### Diferència entre Samba i NFS

La diferència principal és **com es controla l’accés**:

#### Samba
- L’autenticació es fa per **usuaris**.
- Es pot fer amb:
  - **usuaris locals** (usuari/contrasenya al servidor)
  - o amb un sistema centralitzat com **LDAP** (gestió d’usuaris a la xarxa)

#### NFS
- L’accés es controla principalment per **IP** (o rang d’IPs).
- És a dir, depèn més de **des d’on et connectes** que no pas de **quin usuari ets**.

### Compatibilitat

Un punt clau és que **Samba és compatible amb Windows i Linux**:

- A **Windows** es veu com una carpeta compartida típica.
- A **Linux** també es pot muntar i utilitzar sense problemes.

## 9.2 Autenticació a través d'LDAP.

## 9.3 Creació del server SAMBA. Configuració d'usuaris dins del server.

<img width="654" height="191" alt="image" src="https://github.com/user-attachments/assets/dcbfdc40-5547-45bb-b491-bb20778c9c00" />

Instal·lem el paquet samba amb _sudo apt install samba_.

<img width="453" height="214" alt="image" src="https://github.com/user-attachments/assets/85132575-cc9d-4730-bda9-a35d8cab8109" />

Creem la carpeta proves i donem permis 777. Creem un arxiu hola i comprovem els permissos read write.

<img width="424" height="63" alt="image" src="https://github.com/user-attachments/assets/23057037-0a99-4ec6-8e0b-cb5575f5142e" />

Creem els usuaris blau, roig i groc. Els configurem de forma que no puguin accedir amb una sessió i només funcionin per a samba.

<img width="305" height="70" alt="image" src="https://github.com/user-attachments/assets/05ccc08c-c231-4e29-95f2-263721c6dda6" />

Creem el grup color

<img width="329" height="155" alt="image" src="https://github.com/user-attachments/assets/a3e27242-b413-4e80-bec0-5b483204b7a1" />

Afegim els usuaris al grup que hem creat abans.

<img width="746" height="297" alt="image" src="https://github.com/user-attachments/assets/a649fd4a-d554-44aa-9738-7ac5172c5eb7" />

Comprovem que s'han creat els usuaris i estan dins del grup color.

<img width="321" height="206" alt="image" src="https://github.com/user-attachments/assets/31320d11-0cf4-47f3-9664-383532500d55" />

Configurem contrasenyes per als usuaris samba.

<img width="211" height="161" alt="image" src="https://github.com/user-attachments/assets/122cded4-d35c-4043-85ef-5082c35a83f2" />

A l'arxiu smb.conf (/etc/samba/smb.conf) configurem el recurs compartit. Aqui podem tots els recursos compartits. Afegim la configuració al final del arxiu.

<img width="390" height="32" alt="image" src="https://github.com/user-attachments/assets/bc8fd5b6-4352-4860-8571-8e35832321fa" />

Sempre que modifiquem l'arxiu hem de reiniciar el servei.

## 8.4 Accés al servidor samba des de l'entorn client.

<img width="674" height="166" alt="image" src="https://github.com/user-attachments/assets/eeddf414-2886-4405-99ae-838e950cbb96" />

Instal·lem el paquet smbclient amb sudo apt install smbclient.




