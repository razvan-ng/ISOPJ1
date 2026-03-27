---
layout: default
title: "SPRINT 4: CONFIGURACIÓ DEL PROGRAMARI DE BASE I SISTEMES D'EMMAGATZEMATGE EN UBUNTU"
---

## RAID

RAID (*Redundant Array of Independent Disks*) és una tècnica per agrupar diversos discos en una sola unitat lògica.  
S’utilitza per millorar la **redundància**, la **disponibilitat** i, segons el nivell, també el **rendiment**.

### Tipus de RAID

**RAID 0**  
Fa *striping*: reparteix les dades entre diversos discos.  
Millora el rendiment, però **no té redundància**.

**RAID 1**  
Fa *mirroring*: copia les mateixes dades en dos discos.  
Ofereix **alta seguretat**, però redueix la capacitat útil al 50%.

**RAID 5**  
Fa *striping* amb **paritat distribuïda**.  
Necessita mínim 3 discos i permet fallar **1 disc** sense perdre dades.

**RAID 6**  
Similar al RAID 5, però amb doble paritat.  
Necessita mínim 4 discos i permet fallar **2 discos**.

**RAID 10**  
Combina **RAID 1 + RAID 0**.  
Ofereix **bon rendiment i redundància**, però necessita mínim 4 discos.

### Resum tècnic

Els RAID s’utilitzen per augmentar la tolerància a fallades.  
No tots els nivells donen seguretat: **RAID 0 no protegeix dades**, mentre que **RAID 1, 5, 6 i 10 sí**.

## 1. Configuració RAID 

<img width="698" height="312" alt="image" src="https://github.com/user-attachments/assets/fd1c163c-6b1e-4c7b-8a63-6ec55f26a578" />

Instal·lem el paquet mdadm al client.

<img width="698" height="312" alt="image" src="https://github.com/user-attachments/assets/482bff94-f3ea-45af-be4d-ac188349cafd" />

Amb fdisk -l identifiquem els discos que tenim a la màquina.

<img width="658" height="531" alt="image" src="https://github.com/user-attachments/assets/6fdbb887-71f8-4ae7-a742-205d9a4d6897" />

Creem una partició en ambdós discos que ocupin tot el disc.

<img width="658" height="531" alt="image" src="https://github.com/user-attachments/assets/c3c14579-5676-40ba-b2ca-62317bd71081" />

Comprovem amb fdisk -l les particions creades.

<img width="658" height="507" alt="image" src="https://github.com/user-attachments/assets/abbc0ae6-1134-40b8-8ccf-6509c343315d" />

Creem una carpeta on farem les diferentes proves.

<img width="485" height="156" alt="image" src="https://github.com/user-attachments/assets/3158c1b3-0ecc-409d-8302-b49b0ea4ba56" />

Amb mdadm creem el RAID amb els dos discos.

<img width="660" height="285" alt="image" src="https://github.com/user-attachments/assets/9c7528ee-6e10-4078-8603-fbc8fc39d58d" />

Donem format al RAID.

<img width="660" height="285" alt="image" src="https://github.com/user-attachments/assets/14ea016c-c00e-4fe3-977a-5b2e5370bd10" />

Amb detail, podem consultar la informació referent al RAID.

<img width="607" height="506" alt="image" src="https://github.com/user-attachments/assets/de2e5151-3823-4d74-87f9-64c7171c49a1" />

Hem d'enviar a mdadm.conf la informació del array i els dispositius que conformen el RAID.

<img width="591" height="85" alt="image" src="https://github.com/user-attachments/assets/62d4890a-a5c2-4ea4-8239-47f542d129a9" />
<img width="591" height="85" alt="image" src="https://github.com/user-attachments/assets/d08b31b9-216f-4fe7-abb2-ca483a90d16c" />

Al fitxer fstab configurem que cada cop que iniciem l'ordinador es faci el muntatge automaticament. En cas que no s’inicii el sistema podriem probar en actualitzar initramfs: update-initramfs -u -k all i reiniciem l’ordinador.

<img width="591" height="224" alt="image" src="https://github.com/user-attachments/assets/9a0eb45c-7d26-4c94-b575-752a76980f71" />
<img width="1047" height="277" alt="image" src="https://github.com/user-attachments/assets/e37b28c2-d6a6-41fe-8c1b-bac60895cfb9" />

Creem un arxiu de prova.

<img width="536" height="95" alt="image" src="https://github.com/user-attachments/assets/24743e9b-ecfb-4ca3-a224-9af15af347fa" />

Amb el programa que hem instal·lat per fer els RAIDs podem configurar un disc com defectuós per fer la prova.

<img width="622" height="67" alt="image" src="https://github.com/user-attachments/assets/989fb465-b99e-4afd-9145-e0d287b996cb" />

Amb detail podem veure com apareix un disc en estat defectuós.

<img width="618" height="380" alt="image" src="https://github.com/user-attachments/assets/9e98a9bb-bdca-46c1-a4a5-de94150a3a95" />

Però veurem que encara podem continuar accedint a la informació.

<img width="508" height="132" alt="image" src="https://github.com/user-attachments/assets/ef4f18f0-6b43-4698-9e9a-d955c723c9db" />

També el podem traure i veurem que tenim només 1 dispositiu actiu. 

<img width="729" height="526" alt="image" src="https://github.com/user-attachments/assets/d088a317-831b-4805-847e-901ff80ee3bb" />

Però tot i això podem accedir al fitxer.

<img width="386" height="70" alt="image" src="https://github.com/user-attachments/assets/f6389e5a-dc37-4d92-a9f3-07190565e733" />

Tornem a afegir el disc al RAID.

<img width="641" height="44" alt="image" src="https://github.com/user-attachments/assets/68fc16b1-99cb-42a6-a5af-1d0c94a0c866" />

I mentre s'estigui activant veurem com el segon disc (que és el que hem tret) es sincronitza.

<img width="708" height="80" alt="image" src="https://github.com/user-attachments/assets/8339b161-1e21-454a-b3e1-6491427535a7" />

I després d'un moment veurem que s'ha sincronitzat correctament.

<img width="708" height="80" alt="image" src="https://github.com/user-attachments/assets/612d6008-db7e-4da4-b1ae-ea9bf3db657d" />

Per començar a desmontar el RAID treiem l'automuntatge del fstab.

<img width="708" height="269" alt="image" src="https://github.com/user-attachments/assets/ec364134-707f-4b30-a2bd-1116a10953cb" />

Després desmuntem la unitat de la sessió actual.

<img width="708" height="60" alt="image" src="https://github.com/user-attachments/assets/614e3275-0d12-4f7e-b8d5-325c1ae2c58a" />

Aturem el RAID al mdadm.

<img width="708" height="60" alt="image" src="https://github.com/user-attachments/assets/7e334991-8b24-4019-abd1-1cfb5c93ad91" />

I esborrem la carpeta d'on s'ubicava el disc muntat.

<img width="575" height="55" alt="image" src="https://github.com/user-attachments/assets/676b4787-ae6a-45a8-a3b0-174c1a75a8d1" />

Comprovem que el raid s'ha borrat.

<img width="673" height="95" alt="image" src="https://github.com/user-attachments/assets/8eb5db48-25de-4255-9ec5-9a03cbcee350" />

Esborrem el contingut de mdadm.conf.

<img width="673" height="95" alt="image" src="https://github.com/user-attachments/assets/6388086b-a0ce-48ae-ab6c-b3e39c9bebde" />

Reiniciem la màquina.

<img width="472" height="446" alt="image" src="https://github.com/user-attachments/assets/a2f47382-3cdb-46ad-a957-d048a0ab91e3" />

I per últim veiem que no tenim cap RAID disponible.

<img width="646" height="114" alt="image" src="https://github.com/user-attachments/assets/944df78f-5301-4565-b289-7a20a57c1545" />


