1- Modèle osi

# Modèle Osi
Osi $=$ Open Systems Interconnection
* Couche 1 : **P**hysique (Physical)
* Couche 2 : **L**iaison de données(Data Link)
* Couche 3 : **R**éseau (Network)
* Couche 4 : **T**ransport
* Couche 5 : **S**ession
* Couche 6 : **P**résentation
* Couche 7 : **A**pplication

![288bbb9497391161e69370c90e7fd539.png](../_resources/d1b0a9bddd3b4f6695f145c61f5a7902.png)

**P**our **l**e **r**éseau **t**out **s**e **p**asse **a**utomatiquement

#
## Couche Physique
* la premiére couche du modéle OSI
* Chargée de la transmission effective des signeaux(optique,electrique...)au niveau matériel
* Chargée de la conversion entre bits et signaux électriques ou optiques
* Contient les normes : **RJ45**,**RJ11** ...
## Couche Liaison de données
* Fournit les moyens fonctionnels et procéduraux pour le transfert de données entre des entités d'un réseau.
* Transfére des données entre les noeuds adjacent d'un réseau étandu (WAN).
* transfére des donnée entre ldes noeuds sure le meme segment d'un réseau local (LAN).
* Contient (dans certain cas) les moyens de détection des erreurs qui peuvent survenir au niveau de la couche physique.
* Contient les protocoles: **ARP**,**HDLC**,**MAC**,**ETHERNET**
## Couche Réseau
* s'occupe de toute qui a trait à internet
* Prend en charge la connectivité et le routage (la selection du chemin)
* Contient les protocoles **[ipv4](https://fr.wikipedia.org/wiki/IPv4)** et **ipv6**
## Couche Transport
* gére la communications de bout en bout entre processus
* Contient les protocoles **[TCP](https://fr.wikipedia.org/wiki/Transmission_Control_Protocol)** (transport fiable des données) et **[UDP](https://fr.wikipedia.org/wiki/User_Datagram_Protocol)** (transport non fiable)
* multiplexage et démultiplexage ??

Pour plus d'informations, [cliquez ici](https://www.youtube.com/watch?v=o6xGf7uJ-j4)
## Couche Session

* Prend en charge l'établissement, la gestion et la terminaison de session entre deux hôtes
* Contient le protocole **[SOCKS](https://fr.wikipedia.org/wiki/SOCKS)**

## Couche Présentation
* Responsable du formatage et de la structuration des données pour la couche Aplication par:
	* Compression
	* Conversion de code caractére
	* Chifrfrement et déchiffrement
* Contient les protocoles : **[TLS](https://fr.wikipedia.org/wiki/Transport_Layer_Security)**,**[HTML](https://fr.wikipedia.org/wiki/HyperText_Markup_Language)**,**[XML](https://fr.wikipedia.org/wiki/EXtensible_Markup_Language)**,**[ASCII](https://fr.wikipedia.org/wiki/American_Standard_Code_for_Information_Interchange)**
## Couche Application
* Concernent des applications comme l'email, le navigateur Web, le ftp, etc.
* Contien les protocoles: **[DNS](https://fr.wikipedia.org/wiki/Domain_Name_System)**,**[FTP](https://fr.wikipedia.org/wiki/File_Transfer_Protocol)**,**[HTTPS](https://fr.wikipedia.org/wiki/Hypertext_Transfer_Protocol_Secure)**,**[IMAP](https://fr.wikipedia.org/wiki/Internet_Message_Access_Protocol)**,**[POP](https://fr.wikipedia.org/wiki/Post_Office_Protocol)**,**[SMTP](https://fr.wikipedia.org/wiki/Simple_Mail_Transfer_Protocol)**,**[SSH](https://fr.wikipedia.org/wiki/Secure_Shell)**....