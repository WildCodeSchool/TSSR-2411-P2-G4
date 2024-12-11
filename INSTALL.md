
# Installation d'un Client Windows 10 - CLIWIN01

## 1. Installation de Windows 10

- **Préparation de la machine** : Téléchargez l'image ISO de Windows 10 depuis le site officiel de Microsoft.
- **Création d'un support d'installation** : Utilisez l'outil de création de média pour créer une clé USB bootable.
- **Démarrage de l'installation** : Insérez la clé USB dans la machine cible et redémarrez. Assurez-vous que la machine boote depuis la clé USB dans le BIOS/UEFI.
- **Choix de la langue et des paramètres** : Sélectionnez la langue, la région et la disposition du clavier.
-
-
-   **Installation** : Suivez les instructions à l'écran pour installer Windows 10. Une fois l'installation terminée, le système redémarre et la configuration initiale se termine.

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
