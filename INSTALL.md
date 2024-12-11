![Description de l'image](https://raw.githubusercontent.com/WildCodeSchool/TSSR-2411-P2-G4/refs/heads/main/screenshots/cc3e918a-2c3e-4b68-a7a9-55fbde4e6220.webp)


# Installation d'un Client Windows 10 - CLIWIN01

## 1. Installation de Windows 10

- **Préparation de la machine** : Téléchargez l'image ISO de Windows 10 depuis le site officiel de Microsoft.
- **Création d'un support d'installation** : Utilisez l'outil de création de média pour créer une clé USB bootable.
- **Démarrage de l'installation** : Insérez la clé USB dans la machine cible et redémarrez. Assurez-vous que la machine boote depuis la clé USB dans le BIOS/UEFI.
- **Choix de la langue et des paramètres** : Sélectionnez la langue, la région et la disposition du clavier.
- **Installation** : Suivez les instructions à l'écran pour installer Windows 10. Une fois l'installation terminée, le système redémarre et la configuration initiale se termine.

## 2. Configuration du Nom de la Machine (CLIWIN01)

- **Accès aux paramètres système** : Allez dans **Paramètres** > **Système** > **Informations système**.
- **Modification du nom de l'ordinateur** :
  - Cliquez sur **Renommer ce PC**.
  - Entrez le nouveau nom "CLIWIN01" et redémarrez la machine.

## 3. Création du Compte Utilisateur 'wilder'

- **Accès aux paramètres des comptes utilisateurs** : Allez dans **Paramètres** > **Comptes** > **Famille et autres utilisateurs**.
- **Ajout d'un utilisateur** :
  - Cliquez sur **Ajouter un autre utilisateur sur ce PC**.
  - Entrez le nom d'utilisateur "wilder" et le mot de passe "Azerty1*".
  - Sélectionnez **Administrateur** pour ajouter l'utilisateur au groupe des administrateurs locaux.
- **Valider la création du compte**.

## 4. Configuration de l'Adresse IP Fixe (172.16.10.20/24)

- **Accès aux paramètres réseau** : Allez dans **Paramètres** > **Réseau et Internet** > **Ethernet** ou **Wi-Fi** (selon le type de connexion).
- **Modifier les paramètres de l'adaptateur** : Cliquez sur **Modifier les options de l'adaptateur**.
- **Configuration de l'adresse IP** :
  - Faites un clic droit sur la connexion active (Ethernet ou Wi-Fi) et choisissez **Propriétés**.
  - Sélectionnez **Protocole Internet Version 4 (TCP/IPv4)** et cliquez sur **Propriétés**.
  - Cochez **Utiliser l'adresse IP suivante** et entrez l'adresse IP suivante :
    - **Adresse IP** : `172.16.10.20`
    - **Masque de sous-réseau** : `255.255.255.0`
    - **Passerelle par défaut** : `172.16.10.1` (si nécessaire, selon votre réseau).
- **Valider et fermer les paramètres**.

## 5. Vérification de la Configuration

- **Vérification du nom de la machine** : Ouvrez une fenêtre **Invite de commandes** et tapez la commande `hostname` pour vérifier que le nom de l'ordinateur est bien "CLIWIN01".
- **Vérification du compte utilisateur** : Tapez `net user wilder` pour vérifier que le compte "wilder" existe et qu'il est membre du groupe des administrateurs locaux.
- **Vérification de l'adresse IP** : Tapez `ipconfig` dans l'Invite de commandes pour vérifier que l'adresse IP est bien définie sur `172.16.10.20`.


# Installation et Configuration d'Ubuntu 22.04/24.04 LTS

## 1. Installation d'Ubuntu 22.04/24.04 LTS

### 1.1 Préparation de la machine
- **Télécharger l'ISO d'Ubuntu** : Téléchargez l'image ISO d'Ubuntu 22.04 ou 24.04 LTS depuis le site officiel d'Ubuntu.
- **Créer un support d'installation** : Utilisez un outil comme Rufus ou balenaEtcher pour créer une clé USB bootable à partir de l'image ISO.

### 1.2 Démarrer l'installation
- Insérez la clé USB dans la machine cible et redémarrez-la. Assurez-vous que le BIOS/UEFI est configuré pour booter à partir de la clé USB.
- Sélectionnez **Install Ubuntu** pour commencer l'installation.

### 1.3 Configuration initiale
- **Langue et clavier** : Sélectionnez votre langue préférée et la disposition du clavier.
- **Connexion à Internet** : Vous pouvez choisir de vous connecter à un réseau Wi-Fi ou de configurer une connexion Ethernet (si nécessaire).
- **Type d'installation** : Choisissez Installation normale ou Installation minimale, selon vos préférences.
- **Partitionnement** : Laissez Ubuntu partitionner automatiquement votre disque ou configurez-le manuellement selon vos besoins.

### 1.4 Finalisation de l'installation
- **Nom de l'ordinateur et identifiants utilisateur** : Lors de la configuration de l'utilisateur, entrez le nom de la machine comme `CLILIN01` et créez un utilisateur avec le nom `wilder` et le mot de passe `Azerty1*`.
- **Configuration réseau** : Vous pouvez ignorer cette étape si vous souhaitez configurer l'adresse IP plus tard dans les paramètres système.

### 1.5 Redémarrage
Une fois l'installation terminée, redémarrez la machine et retirez la clé USB pour démarrer Ubuntu à partir du disque dur.

## 2. Configuration du Nom de la Machine (CLILIN01)
- **Accéder aux paramètres système** : Allez dans **Paramètres > Détails > À propos**.
- **Modifier le nom de la machine** : Cliquez sur **Nom de l'ordinateur** et entrez `CLILIN01`. Un redémarrage peut être nécessaire pour appliquer le changement.

## 3. Création du Compte Utilisateur 'wilder' dans le groupe sudo

### Création de l'utilisateur
1. Ouvrez un terminal.
2. Tapez la commande suivante pour créer l'utilisateur :
    ```bash
    sudo adduser wilder
    ```
    Entrez le mot de passe `Azerty1*` lorsque cela est demandé.

### Ajout de l'utilisateur au groupe sudo
Après avoir créé l'utilisateur, ajoutez-le au groupe `sudo` pour lui accorder les privilèges administratifs avec la commande suivante :
```bash
sudo usermod -aG sudo wilder

