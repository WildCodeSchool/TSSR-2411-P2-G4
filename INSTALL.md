
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




-----

# Installation et Configuration d'un Client Ubuntu 22.04/24.04 LTS

## Prérequis
- Image ISO d'Ubuntu 22.04/24.04 LTS (téléchargeable sur [Ubuntu Downloads](https://ubuntu.com/download/desktop)).
- Une clé USB bootable créée avec un outil comme **Rufus** (Windows) ou **Etcher** (Linux/macOS).

---

## Étape 1 : Installation d'Ubuntu
1. **Démarrage sur la clé USB** :
   - Configure le BIOS/UEFI pour démarrer sur la clé USB.
   - Sélectionne **Installer Ubuntu** dans le menu.

2. **Processus d'installation** :
   - **Langue** : Choisis la langue souhaitée.
   - **Disposition du clavier** : Sélectionne le clavier approprié.
   - **Mises à jour et logiciels** :
     - Coche **Installation normale**.
     - Coche **Télécharger les mises à jour pendant l'installation**.
     - Décoche **Installer des logiciels tiers...** (si non nécessaire).
   - **Type d'installation** :
     - Choisis **Effacer le disque et installer Ubuntu** pour une installation propre.

3. **Configuration utilisateur** :
   - **Nom de l'ordinateur** : `CLILIN01`.
   - **Compte utilisateur** :
     - Nom d'utilisateur : `wilder`.
     - Mot de passe : `Azerty1*`.

4. **Installation** :
   - Lance l'installation.
   - Redémarre la machine à la fin du processus et retire la clé USB.

---

## Étape 2 : Configuration réseau avec une IP fixe
1. **Accès à la console** :
   - Connecte-toi avec l'utilisateur `wilder`.
   - Ouvre un terminal avec `Ctrl+Alt+T`.

2. **Modifier la configuration réseau** :
   - Édite le fichier de configuration réseau avec :
     ```bash
     sudo nano /etc/netplan/01-netcfg.yaml
     ```

   - Ajoute la configuration suivante (remplace `<nom_interface>` par le nom de ton interface réseau) :
     ```yaml
     network:
       version: 2
       renderer: networkd
       ethernets:
         <nom_interface>:
           dhcp4: false
           addresses:
             - 172.16.10.30/24
           gateway4: 172.16.10.1
           nameservers:
             addresses:
               - 8.8.8.8
               - 8.8.4.4
     ```

3. **Appliquer la configuration** :
   ```bash
   sudo netplan apply
Vérifier la connectivité réseau :
bash
Copier le code
ip a
ping -c 4 8.8.8.8
Étape 3 : Ajouter l'utilisateur "wilder" au groupe sudo
Par défaut, l'utilisateur créé a les droits sudo. Si ce n'est pas le cas :

Ajoute wilder au groupe sudo :
bash
Copier le code
sudo usermod -aG sudo wilder
Vérifie les groupes de l'utilisateur :

bash
Copier le code
groups wilder
Étape 4 : Mise à jour du système
Mets à jour les dépôts et le système :

bash
Copier le code
sudo apt update && sudo apt upgrade -y
Installe des utilitaires nécessaires :

bash
Copier le code
sudo apt install net-tools vim curl -y
Ton client Ubuntu CLILIN01 est maintenant installé et configuré avec :

Nom de l'ordinateur : CLILIN01
Utilisateur : wilder
Mot de passe : Azerty1*
IP fixe : 172.16.10.30/24
