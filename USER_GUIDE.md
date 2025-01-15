# Installation du paquet `dialog` sous Ubuntu et Debian obligatoire 

Le paquet **`dialog`** est un utilitaire permettant de créer des interfaces utilisateur simples en mode texte dans un terminal. Il est souvent utilisé dans les scripts Bash pour des menus interactifs.

## Étapes d'installation

### 1. Mettre à jour la liste des paquets
Avant d'installer un paquet, il est recommandé de mettre à jour la liste des paquets pour s'assurer d'avoir les versions les plus récentes :

sudo apt update
### 2. Installer le paquet dialog
Utilisez la commande suivante pour installer dialog :
sudo apt install dialog

### 3. Vérifier l'installation
Une fois l'installation terminée, vérifiez que le paquet est correctement installé en affichant sa version :
dialog --version
Tester dialog
Voici un petit exemple de script pour vérifier que dialog fonctionne correctement :
#!/bin/bash
dialog --msgbox "Bienvenue dans Dialog ! Installation réussie." 10 30
Enregistrez ce script dans un fichier (par exemple test_dialog.sh), rendez-le exécutable et lancez-le :
chmod +x test_dialog.sh
./test_dialog.sh
Une boîte de dialogue devrait s’afficher dans le terminal avec le message "Bienvenue dans Dialog ! Installation réussie."

# Mise en place du code Bash

## 1.Menu principal interractif 

| ![Image 1](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/Menu_principal.png) | ![Image 2](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/1_Menu_principal_interractif.PNG) |
|-------------------------|------------------------|

## 2.Sous Menu : action sur les utilisateurs 

| ![Image 3](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/Actions_utilisateurs.png) | ![Image 4](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/2_Menu_actions_sur_les_utilisateurs.PNG) |
|-------------------------|------------------------|

## 3.Sous Menu : action sur les ordinateurs 

| ![Image 5](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/Actions_ordinateurs.png) | ![Image 6](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/3_Menu_actions_sur_les_ordinateurs.PNG) |
|-------------------------|------------------------|

## 4.Sous Menu : recherche d'informations 

| ![Image 7](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/Recherches_Infos.png) | ![Image 8](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/4_Menu_recherche_informations.PNG) |
|-------------------------|------------------------|

## 5.Fonction : Création d'utilisateurs

| ![Image 9](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/Cr%C3%A9ation_Utilisateur.png) | ![Image 10](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/5_Fonction_creation_utilisateur.PNG) |
|-------------------------|------------------------|

## 6.Fonction : Suppression d'utilisateurs

| ![Image 11](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/Cr%C3%A9ation_Utilisateur.png) | ![Image 12](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/6_Fonction_suppression_utilisateur.PNG) |
|-------------------------|------------------------|

## 7.Fonction : Arrêt d'un ordinateur

|![Image 13](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/7_Fonction_arreter_ordinateur.PNG)

## 8.Fonction : Redémarrage d'un ordinateur

|![Image 14](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/8_Fonction_redemarrer_ordinateur.PNG)

## 9.Fonction : Dernière connexion d'un utilisateur

|![Image 15](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/9_Fonction_derniere_connexion_utilisateur.PNG)

## 10.Fonction : Dernière version de l'OS d'un ordinateur

|![Image 15](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/10_Fonction_derniere_version_os_ordinateur.PNG)

## 11.Fonction : Affichage des logs

| ![Image 15](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/Affichage_Logs.png) | ![Image 16](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/Bash/11_Fonction_afficher_derniers_logs.PNG) |
|-------------------------|------------------------|


# Mise en place du code Powershell

## 1. Presentation de la connexion SSH

| ![Image 21](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/powershell/1.Connexion_SSH.png?raw=true) | ![Image 22](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/powershell/SSH.PNG?raw=true) |
|-------------------------|----------------|

## 2. Menu principal interractif 

| ![Image 17](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/powershell/2.Menu_principal.png?raw=true) | ![Image 18](https://github.com/user-attachments/assets/b660c539-a32e-419c-a57f-78783f986ccd) |
|-------------------------|----------------|

## 3. Sous Menu : actions sur les utilisateurs

| ![Image 19](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/powershell/3.Actions_Utilisateurs.png?raw=true) | ![Image 20](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/powershell/G%C3%A9rer%20utilisateurs.PNG?raw=true) |
|-------------------------|----------------|

## 4. Sous Menu : actions sur les ordinateurs 

| ![Image 23](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/powershell/4.Actions_Ordinateurs.png?raw=true) | ![Image 24](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/powershell/G%C3%A9rer%20ordinateur.PNG?raw=true) |
|-------------------------|----------------|

## 5. Sous Menu : action sur les logiciels

| ![Image 25](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/powershell/5.Actions_Logiciels.png?raw=true) | ![Image 26](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/powershell/G%C3%A9rer%20logiciel.PNG?raw=true) |
|-------------------------|----------------|

## 6. Sous Menu : actions d'audit

| ![Image 27](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/powershell/6.Actions_Audit.png?raw=true) | ![Image 28](https://github.com/WildCodeSchool/TSSR-2411-P2-G4/blob/main/screenshots/USER_GUIDE/powershell/Option%20d'audit.PNG?raw=true) |
|-------------------------|----------------|

