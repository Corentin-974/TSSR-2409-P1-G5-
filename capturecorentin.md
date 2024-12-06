
# Etapes d'installation et Configuration de Windows Server 2022

## Configuration VM (VirtualBox)

- Sur votre VM, cliquer sur Nouvelle;
- Nommer la machine SRVWIN01;
  
![Capture d'écran 2024-12-05 115712](https://github.com/user-attachments/assets/a0801cfb-d1f1-4e95-acaa-b2296685a710)


- Ajouter l'ISO Windows server 2022 téléchargeé préalablement sur internet pour l'ajouter par la suite dans la partie "ISO Image";


![Capture d'écran 2024-12-05 115904](https://github.com/user-attachments/assets/37564f55-50ac-4086-87c6-a819f23364df)


- Aller dans l'onglet "Hardware";
- Ajouter au minimun 2 à 4 Go de RAM et 2 CPU;


![Capture d'écran 2024-12-05 110516](https://github.com/user-attachments/assets/5f27bf23-eac3-4beb-a44b-735a90fbb138)

- Aller dans l'onglet "Hard Disk";
- Choisir l'espace de stockage que l'on souhaite attribuer à la machine (conseillé : 40 Go);

![Capture d'écran 2024-12-05 120009](https://github.com/user-attachments/assets/c0a46ca6-b531-4626-a4a1-47e1c3997fd4)

- Démarrer le Windows Server 2022;

![Capture d'écran 2024-12-05 110700](https://github.com/user-attachments/assets/c9fb5a00-d0ee-4700-b295-2d8b70cc10b6)

- Au début de l'installation, vous pouvez choisir la langue que vous souhaitez pour l'installation;
-  Choisir "French" pour le "Time and currency format";
-  Choisir "French" pour avoir le configuration du clavier en Français;
  
![Capture d'écran 2024-12-05 110739](https://github.com/user-attachments/assets/116bb49b-ae52-4c91-aad6-34b5601c7317)

- Pour le système d'exploitation à installer, il est conseillé de sélectionner la version Standard avec Expérience utilisateur (*Standard Evaluation (Desktop Experience)*) car nous avons besoin d'une interface graphique et nous ne sommes pas sur un projet de Datacenter;
- Cliquer sur "Next";
- Cocher pour accepter les termes du contrat de license puis cliquer sur "Next";

![Capture d'écran 2024-12-05 110815](https://github.com/user-attachments/assets/84eebfb5-f85e-4191-9b2f-fb7d3afcee37)

- Choisir l'installation "Custom";
- Garder la configuration par défaut;
- Cliquer sur "Next";

![Capture d'écran 2024-12-05 110921](https://github.com/user-attachments/assets/cf714a24-14b0-4fb3-8871-523e7b443f6b)

- Laisser le système s'installer;
- Une fois le système installé, il est demandé de choisir un nom d'utilisateur qui sera "Administrateur" et un mot de passe qui sera "Azerty01";

![Capture d'écran 2024-12-05 110946](https://github.com/user-attachments/assets/c46debe3-df3d-4c05-836e-9236214f1bb6)

- Cliquer sur "Yes" pour confirmer la découverte de la machine par d'autres machines du réseau;

![Capture d'écran 2024-12-05 111017](https://github.com/user-attachments/assets/1b382da2-2af2-43c4-be89-676a7c972c6f)

- Rentrer votre mot de passe et accéder à votre session;
- Aller dans le "Gestionnaire de Service" s'il ne s'ouvre pas automatiquement;

![Capture d'écran 2024-12-05 111248](https://github.com/user-attachments/assets/b8bc37d7-8888-4659-8324-09a5df4f9627)

- Aller dans "Serveur local";
- Cliquer sur l'adresse Ethernet;
- Clique droit sur "Ethernet" et "Propriétés";

![Capture d'écran 2024-12-05 112754](https://github.com/user-attachments/assets/04169614-59a1-4390-aa9e-169d43859826)

- Un onglet "Gestion de réseau" apparaît;
- Cliquer sur "Protocole Internet version 4" puis sur "Prorpiétés";
- Aller dans "Configuration alternative" puis rentrer l'adresse IP et le masque de sous-réseau (255.255.255.0);
- Appuyer sur "Ok" pour valider les changements;

![Capture d'écran 2024-12-05 112852](https://github.com/user-attachments/assets/b23c1145-bacc-4ddf-8d97-a390a7e83565)

- Dans le gestionnaire de réseau puis serveur local, cliquer sur Pare-feu Microsoft Defender;
- Cliquer sur désactiver pour "réseau avec domaine", "Réseau privé", "Réseau public" puis retourner dans le gestionnaire de serveur;
  
![Capture d'écran 2024-12-05 113014](https://github.com/user-attachments/assets/f69e6686-6cf7-4068-a791-8c5313c268cb)

- Pour pouvoir partager nos documents, il est important d'installer le "NFS";
- Pour cela, aller dans "Gérer" puis "Ajouter des rôles et des fonctionnalités";
- Dans "Installation type", sélectionner "Installation basée surun rôle ou une fonctionnalité" puis cliquer sur "Suivant";
- Vérifier si le serveur cible est correct puis cliquer sur "Suivant";
  
![Capture d'écran 2024-12-05 113504](https://github.com/user-attachments/assets/d652bb3f-87f7-44e3-9721-4ef656dc0576)

- Dans "Rôles de serveurs", développer "Services de fichiers et de stockage" puis "Services de fichiers et iSCSI";
- Selectionner "Serveur pour NFS" puis "Suivant";

![Capture d'écran 2024-12-05 113613](https://github.com/user-attachments/assets/9c22ea78-704b-4f46-a83f-df3473420941)

- Cliquer sur "Ajouter des fonctionnalités" puis "Suivant";
- Dans "Fonctionnalités" cliquer sur "Suivant";
- Cliquer sur "Installer" sur l'onglet de confirmation pour débuter l'installation;
- Cliquer sur "Fermer" une fois l'installation terminé;

![Capture d'écran 2024-12-05 114259](https://github.com/user-attachments/assets/1727abe1-8635-44f7-8a93-7fa0dc4b1277)

- Une fois ces étapes faites, aller dans le dossier KeePass créé préalablement et qui contient la BDD (voir le USER_GUIDE.md pour créer une nouvelle base de donnée);
- Une fois sur le dossier, clique droit sur le dossier puis "Propriété", puis "Partagé",
- Noter le chemin du réseau qui sera utilisé par la suite pour le client;
- Cliquer sur "Paratgé"; 

![Capture d'écran 2024-12-05 113139](https://github.com/user-attachments/assets/b56c523e-13b7-4119-92fc-3145da72b33e)

- Sur "Tout le monde", donner les droits d'écritue et de lecture seulement;
- Votre dossier est maintenant mis en réseau et est visible par les clients;
![Capture d'écran 2024-12-05 113247](https://github.com/user-attachments/assets/d8302be2-01df-4143-a141-1384523f23d0)

Nous allons maintenant expliquer l'installation et la configuration de KeePass.

