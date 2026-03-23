---
layout: default
title: "SPRINT 5: MONITORATGE, AUDITORIES I PROGRAMES SERVIDOR/CLIENT"
---

# 1. SERVIDOR D'ACTUALITZACIONS
## Exercici 1 ##

### Servidor ###

<img width="480" height="270" alt="image" src="https://github.com/user-attachments/assets/6807218d-a9c3-40ff-8d09-576be4877fc1" />
<img width="595" height="284" alt="image" src="https://github.com/user-attachments/assets/2837a708-36a6-41f9-9578-4b6508aecefe" />

Instal·lem els paquets necesaris per fer aquesta tasca; apache2 i apt-mirror.

<img width="777" height="473" alt="image" src="https://github.com/user-attachments/assets/b060a581-0501-4b0a-9503-8ecd7570239e" />

Un cop instal·lem el apt-mirror, haurem d'entrar al fitxer de configuració ubicat a /etc/apt/mirror.list. Allí podrem afegir els repositoris que volem compartir amb altres clients. 

<img width="777" height="351" alt="image" src="https://github.com/user-attachments/assets/74ba5038-496c-4935-9777-64607996abac" />

Comentem la resta de repositoris i deixem el de google el qual conté només un paquet per agilitzar la prova.

<img width="777" height="351" alt="image" src="https://github.com/user-attachments/assets/5110b57b-baf8-4398-af14-43dd56982e8d" />

Amb la comanda apt-mirror descarreguem localment el contingut del paquet del repositori.

<img width="997" height="79" alt="image" src="https://github.com/user-attachments/assets/20aa04b7-4173-45e7-a2e8-9b3f2b465f28" />

Creem un softlink del repositori al apache.

<img width="890" height="67" alt="image" src="https://github.com/user-attachments/assets/741947c8-7dfe-4692-b9df-83e43c24315b" />

Comprovem que s'hagi creat correctament.

### Client ###

<img width="807" height="72" alt="image" src="https://github.com/user-attachments/assets/0fb385a9-8f4d-44c2-a46b-eae3fdfebfb7" />

Al Ubuntu 24 la ubicació del fitxer de repositoris ha canviat, però encara podem afegir-ne a /etc/apt/sources.list.

<img width="956" height="114" alt="image" src="https://github.com/user-attachments/assets/0ee130b3-86b5-4d54-ac3a-3e687a44303c" />

Afegim la signatura del repositori per indicar que el repositori es de confiança.

<img width="956" height="360" alt="image" src="https://github.com/user-attachments/assets/23775d0c-a3c6-495d-9b77-868fe074a72f" />

Amb un apt update podem veure que ha consultat el server.

<img width="956" height="360" alt="image" src="https://github.com/user-attachments/assets/d292487c-db0a-4e3a-b4a1-01a824072c2f" />

Provem d'instal·lar chrome i podem veure que ho està descarregant del servidor.

<img width="956" height="360" alt="image" src="https://github.com/user-attachments/assets/6dec0810-26a6-4cd2-bbc0-4e832419799e" />

Comprovem al nostre calaix d'aplicacions que chrome està disponible.

## Exercici 2 ##

## Servidor ##

<img width="913" height="321" alt="image" src="https://github.com/user-attachments/assets/dbcd95dc-d60a-4bae-9c59-dbe7b6f07762" />

Dins de sources.list afegim el PPA de xtradeb, una suite de diferentes aplicacions).

<img width="842" height="439" alt="image" src="https://github.com/user-attachments/assets/ecf60550-79a3-49a0-ab35-3177c37ee9fb" />

Amb la comanda apt-mirror descarreguem el contingut del repositori a la màquina.

<img width="858" height="77" alt="image" src="https://github.com/user-attachments/assets/4591a1f2-394e-4762-891d-152dc5ea303d" />

Creem un softlink del repositori descarregat localment a apache per poder-hi accedir des de fora.

## Client ##

<img width="962" height="77" alt="image" src="https://github.com/user-attachments/assets/26cdc339-52b7-4ba3-8a45-5ed2a2bcd409" />

Modifiquem el fitxer sources.list i afegim l'enllaç del repositori ppa apuntant al servidor.

<img width="810" height="124" alt="image" src="https://github.com/user-attachments/assets/70b80897-f5f3-4fcb-8c14-1356f61b29f7" />

Afegim la signatura del PPA al repositori. 

<img width="810" height="255" alt="image" src="https://github.com/user-attachments/assets/9e42f32b-e844-4c94-aeb7-2f6e380f42dc" />

En el moment en que fem un update veurem que la màquina està consultant al server.

<img width="1098" height="258" alt="image" src="https://github.com/user-attachments/assets/28d5b344-a12d-420f-ac57-61cd674f7a14" />

Intentem instal·lar chromium ungoogled ja que és un dels programes que tenim al repositori.

<img width="992" height="721" alt="image" src="https://github.com/user-attachments/assets/25bd0292-25d8-4a65-9871-e295009dc1d3" />

Un cop finalitzada l'instal·lació veurem que ja podrem accedir-hi.

