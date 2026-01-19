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

