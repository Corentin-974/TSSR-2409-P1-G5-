# Projet 1 : Gestion Base de données chiffrée et sécurisée avec KeePass

## Objectif principal
Création d’une base de données sécurisée et chiffrée, hébergée sur un serveur Windows Server 2022, et accessible à partir de plusieurs clients via le logiciel **KeePass**.

### Détails techniques
- **Base de données** : Chiffrée avec KeePass.
- **Sécurisation** : Protection par clé maître (mot de passe, fichier clé ou combinaison des deux).
- **Serveur** : Hébergement sur **Windows Server 2022** avec accès via un partage réseau ou un service cloud privé (WebDAV, SMB, etc.).
- **Clients** : Compatible avec tous les systèmes d’exploitation (Windows, macOS, Linux, Android, iOS).

## Objectif secondaire
Assurer que le deuxième client utilise un **système d’exploitation différent** du premier (exemple : un client sous Windows et un autre sous Linux ou macOS).

## Schéma d’utilisation
1. **Client 1** : Poste sous Windows accédant à la base via KeePass.
2. **Client 2** : Poste sous Linux ou macOS accédant via KeePassXC ou autre solution compatible.

## Sécurisation et gestion des accès
- Utilisation de **protocoles sécurisés** (SMB sécurisé ou HTTPS).
- Configuration des **droits d’accès** sur le serveur pour restreindre les connexions aux utilisateurs autorisés.

## Avantages
- **Sécurité** : Chiffrement fort avec KeePass.
- **Flexibilité** : Compatibilité multi-OS.
- **Centralisation** : Stockage des données sur un serveur sécurisé.

# Contexte et introduction

Dans le cadre d’un projet visant à renforcer la sécurité des données sensibles au sein d’une infrastructure informatique, l’objectif est de mettre en place une solution de gestion des mots de passe centralisée et sécurisée. Pour répondre à cette exigence, le logiciel **KeePass** sera utilisé pour créer une base de données chiffrée, hébergée sur un serveur sécurisé.

Le choix de **Windows Server 2022** comme serveur garantit une infrastructure robuste et fiable, tandis que la compatibilité avec divers systèmes d’exploitation (Windows, macOS, Linux, etc.) permet une utilisation flexible et adaptée aux besoins des utilisateurs. Ce projet vise donc à assurer la sécurité des données tout en offrant un accès contrôlé et multi-plateforme à la base de mots de passe.

Le projet comprend également un objectif secondaire consistant à valider la **compatibilité** entre différents systèmes d’exploitation utilisés par les clients.

# Rôles des membres

## Sprint 1
- **Scrum Master** : Corentin
- **Product Owner** : Karim
- **Développeur** : Benjamin

## Sprint 2
- **Product Owner** : Corentin
- **Scrum Master** : Benjamin
- **Développeur** : Karim

# Choix techniques

Pour ce projet, nous utiliserons Windows server version 2022 comme serveur. Pour le côté client, il a été décidé d'utiliser Ubuntu pour le Client 1 car simple à utliser et Windows 10/11 pour le client 2 qui est facilement trouvable sur internet et instalable.

# Difficultés rencontrés 


**Configurer les adresses IP** : trouver la bonne configuration de l'adresse IP du serveur et du client avec le bon masque de sous réseau,    

**Ping du client au serveur** : réussir à ping le serveur à partir du client et donc avoir accès aux documents partagés du serveur,

**Partager correctement la BDD** : rendre visible le dossier de la BDD sur le réseau partagé + configurer correctement les propriétés de partage du dossier pour que les clients aint les droits d'exécution, d'écriture et de lecture,

**Monter la BDD sur le client** : trouver la bonne ligne de commande pour récupérer et monter le dossier partagé sur le poste client,   

**Rentrer le nom d'utilisateur et le mot de passe automatiquement** : Après avoir enregistré ses informations de connexion dans KeePass pour un site web, on souhaite remplir automatiquement le nom d'utilisateur et le mot de passe lors de l'accès à la page de connexion du site.

# Les solutions

**Configurer les adresses IP** : après avoir saisi l’adresse IP attribuée au projet, il faut sélectionner le masque de sous-réseau 255.255.255.0 pour permettre la communication entre le serveur et le client. Ensuite, pour accéder à Internet avec cette IP, il est nécessaire de renseigner la passerelle et les serveurs DNS (comme 8.8.8.8 et 1.1.1.1) qui facilitent l’accès à des services en ligne,

**Ping du client au serveur** : pour que le client puisse pinger le serveur, il est nécessaire de vérifier que les paramètres réseau des machines virtuelles (VM) du client et du serveur sont configurés en mode accès par pont. Ce mode permet à chaque VM de se connecter directement au réseau local de l’hôte, comme si elles étaient des appareils physiques sur le même réseau. Cela leur attribue une adresse IP sur le même réseau que l’hôte, facilitant ainsi la communication entre elles,

**Partager correctement la BDD** : 

**Monter la BDD sur le client** :  

**Rentrer le nom d'utilisateur et le mot de passe automatiquement** : 

# Améliorations possibles







Autres gestionnaires de mots de passe :

**1. KeeWeb**

Type : Open-source.

Plateformes : Windows, macOS, Linux, Web.

Caractéristiques :
- Compatible avec les fichiers KeePass.
- Fonctionne en mode hors ligne et peut être auto-hébergé.
- Interface web et applications de bureau.

**2. Bitwarden** (auto-hébergé ou cloud)
   
Type : Open-source avec options gratuites et payantes.

Plateformes : Windows, macOS, Linux, Android, iOS, Web.

Caractéristiques :
- Chiffrement de bout en bout.
- Peut être auto-hébergé.
- Intégrations avec navigateurs.
  
