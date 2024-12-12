
# Installation d'un Client Windows 11 - CLIWIN01

## 1. Installation de Windows 11

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



------



# Installation et Configuration d'un Client Ubuntu 22.04/24.04 LTS

## Prérequis
- Image ISO d'Ubuntu 22.04/24.04 LTS (téléchargeable sur [Ubuntu Downloads](https://ubuntu.com/download/desktop)).
- Une clé USB bootable créée avec un outil comme **Rufus** (Windows) ou **Etcher** (Linux/macOS).

--

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

--

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

-----

# Installation et Configuration d'un Serveur Windows Server 2022

## Prérequis
- Image ISO de Windows Server 2022 (téléchargeable sur [Microsoft Evaluation Center](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022)).
- Une clé USB bootable (créée avec un outil comme **Rufus**).

--

## Étape 1 : Préparer l'installation
1. **Créer la clé USB bootable** :
   - Utilise l'outil **Rufus** pour écrire l'image ISO sur une clé USB.
   - Assure-toi que la clé USB est bootable.

2. **Démarrer sur la clé USB** :
   - Accède au BIOS/UEFI de la machine et configure le démarrage sur la clé USB.
   - Dans le menu, sélectionne **Installer Windows Server**.

--

## Étape 2 : Installer Windows Server 2022
1. **Paramètres initiaux** :
   - Choisis la langue, le format de date/heure et la disposition du clavier.
   - Clique sur **Suivant**, puis sur **Installer maintenant**.

2. **Sélectionner l'édition** :
   - Choisis l’édition de Windows Server (exemple : **Standard** ou **Datacenter**).
   - Sélectionne **Server with Desktop Experience** pour installer l’interface graphique.

3. **Accepter le contrat de licence** :
   - Coche la case **J'accepte les termes du contrat de licence**.
   - Clique sur **Suivant**.

4. **Choisir le type d'installation** :
   - Sélectionne **Personnalisée : installer uniquement Windows (avancé)**.

5. **Configurer le disque** :
   - Sélectionne le disque sur lequel installer Windows Server.
   - Formate le disque si nécessaire.
   - Clique sur **Suivant**.

6. **Installation** :
   - L’installation démarre. Attends que le processus se termine et redémarre automatiquement.

--

## Étape 3 : Configuration initiale
1. **Créer le mot de passe Administrateur** :
   - À la fin de l'installation, définis un mot de passe pour le compte `Administrator` :
     - Mot de passe : `Azerty1*`.

2. **Se connecter** :
   - Utilise le compte `Administrator` et le mot de passe défini (`Azerty1*`).

--

## Étape 4 : Configurer une adresse IP fixe
1. **Accéder aux paramètres réseau** :
   - Ouvre le **Gestionnaire de serveur**.
   - Dans **Configuration locale du serveur**, clique sur **Ethernet**.

2. **Configurer une adresse IP fixe** :
   - Clique droit sur l’interface réseau > **Propriétés**.
   - Sélectionne **Protocole Internet Version 4 (TCP/IPv4)** > **Propriétés**.
   - Configure les paramètres suivants :
     - **Adresse IP** : `172.16.10.5`
     - **Masque de sous-réseau** : `255.255.255.0`
     - **Passerelle par défaut** : `172.16.10.1`
     - **Serveur DNS préféré** : `8.8.8.8`
     - **Serveur DNS auxiliaire** : `8.8.4.4`
   - Clique sur **OK** pour appliquer les changements.

3. **Vérifier la configuration réseau** :
   - Ouvre une console **PowerShell** et utilise les commandes suivantes :
     ```powershell
     ipconfig
     Test-Connection 8.8.8.8
     ```

--

## Étape 5 : Renommer le serveur
1. **Changer le nom de l'ordinateur** :
   - Dans le **Gestionnaire de serveur**, clique sur **Nom de l'ordinateur** dans **Configuration locale du serveur**.
   - Clique sur **Modifier**, entre le nom `SRVWIN01` et confirme.
   - Redémarre le serveur pour appliquer le changement.

--

## Étape 6 : Effectuer les mises à jour
1. **Configurer Windows Update** :
   - Accède à **Paramètres** > **Mises à jour et sécurité** > **Windows Update**.
   - Recherche et installe toutes les mises à jour disponibles.

--

## Résumé de la configuration
- **Nom de l'ordinateur** : `SRVWIN01`
- **Utilisateur Administrateur** : `Administrator`
- **Mot de passe** : `Azerty1*`
- **Adresse IP fixe** : `172.16.10.5/24`

-----

# Installation et Configuration d'un Serveur Debian 12

## Prérequis
- Image ISO de Debian 12 (disponible sur le site officiel : [Debian](https://www.debian.org/)).
- Une clé USB bootable (créée avec un outil comme **Rufus**).
- Accès au BIOS/UEFI pour configurer l'ordre de démarrage.

--

## Étape 1 : Préparer le support d’installation
1. **Télécharger l’image ISO** :
   - Télécharge l’image ISO correspondant à Debian 12, version **netinst** ou **DVD**.

2. **Créer une clé USB bootable** :
   - Utilise **Rufus** (Windows) ou la commande `dd` (Linux/MacOS) pour rendre la clé USB bootable avec l’image ISO.

3. **Configurer le démarrage** :
   - Insère la clé USB dans le serveur.
   - Accède au BIOS/UEFI et configure le démarrage sur la clé USB.

--

## Étape 2 : Installation de Debian 12
1. **Démarrer sur le support d'installation** :
   - Sélectionne **Install** ou **Graphical Install** dans le menu de démarrage.

2. **Configurer les paramètres de base** :
   - **Langue** : Choisis la langue souhaitée (ex. Français).
   - **Région** : Sélectionne la région correspondant à ton fuseau horaire.
   - **Disposition clavier** : Sélectionne le type de clavier (ex. Français - AZERTY).

3. **Configurer le réseau** :
   - Lorsque demandé, configure une adresse IP manuellement :
     - **Adresse IP** : `172.16.10.10`
     - **Masque de sous-réseau** : `255.255.255.0`
     - **Passerelle** : `172.16.10.1`
     - **Serveur DNS** : `8.8.8.8`

4. **Configurer le nom de l’hôte** :
   - Nom de la machine : `SRVLX01`

5. **Créer le mot de passe root** :
   - Définit le mot de passe `root` : `Azerty1*`.

6. **Partitionnement des disques** :
   - Choisis **Guided - Use entire disk** (Utilisation guidée du disque entier).
   - Valide le schéma proposé ou personnalise si nécessaire.

7. **Installer les paquets** :
   - Lors du choix des groupes de paquets, sélectionne :
     - **Serveur SSH**
     - **Utilitaires standards du système**

8. **Installation du GRUB** :
   - Installe le chargeur d’amorçage (GRUB) sur le disque principal.

9. **Finalisation** :
   - Une fois l’installation terminée, redémarre le serveur.

--

## Étape 3 : Configurer l’adresse IP fixe
1. **Modifier la configuration réseau** :
   - Ouvre le fichier de configuration Netplan :
     ```bash
     nano /etc/netplan/01-netcfg.yaml
     ```
   - Ajoute ou modifie les paramètres suivants :
     ```yaml
     network:
       version: 2
       ethernets:
         ens33: # Remplace 'ens33' par le nom de ton interface réseau
           dhcp4: no
           addresses:
             - 172.16.10.10/24
           gateway4: 172.16.10.1
           nameservers:
             addresses:
               - 8.8.8.8
               - 8.8.4.4
     ```

2. **Appliquer la configuration** :
   ```bash
   sudo netplan apply
Vérifier la connectivité réseau :
bash
Copier le code
ip a
ping -c 4 8.8.8.8
Étape 4 : Mise à jour et configuration du système
Mettre à jour les dépôts et le système :

bash
Copier le code
apt update && apt upgrade -y
Installer des utilitaires nécessaires :

bash
Copier le code
apt install net-tools vim curl -y
Résumé de la configuration
Nom de l'ordinateur : SRVLX01
Compte root : root
Mot de passe : Azerty1*
Adresse IP fixe : 172.16.10.10/24

