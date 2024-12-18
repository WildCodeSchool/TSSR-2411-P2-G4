# TSSR-2411-P2-G4

![Diagramme d'architecture réseau](https://miro.medium.com/v2/resize:fit:720/format:webp/1*-UvYjyI57PdZ_xC1WwSxAA.png)


# Description du Projet

## Contexte

Le projet consiste à créer un script qui s'exécute sur une machine et effectue des tâches sur des machines distantes, toutes étant sur le même réseau. Ces tâches peuvent être des actions ou des requêtes d'information.

## Objectifs

### Objectif Principal
L'objectif principal consiste à :
- Exécuter un script PowerShell sur un serveur Windows Server 2022, ciblant des ordinateurs Windows.
- Exécuter un script shell bash sur un serveur Debian 12, ciblant des ordinateurs Ubuntu.

### Objectif Secondaire
L'objectif secondaire est optionnel et permet d'améliorer l'évaluation finale :
- Depuis un serveur, cibler une machine cliente avec un système d'exploitation différent.

## Membres du Groupe de Projet et Rôles par Sprint

| Sprint                               | Product Owner (PO) | Scrum Master (SM) | Développeurs               | Objectifs                                                                                                                                     |
|--------------------------------------|--------------------|-------------------|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| Sprint 1  | Adel              | Barbara           | Benjamin, Maxime    | - Analyse des besoins du projet; définition des rôle de chaque membre du groupe; mise en place et interconnectivité réseau des VM. ||-----------------------------------------------------------------------------------------------------------------------------------------------|
| Sprint 2  | Barbara              | Adel           | Benjamin, Maxime    | - Création et mise en application du script Bash pour les VM Serveur Debian 12 et Client Ubuntu 22.04. |


## Environnement

### Clients
1. **Client Windows 10**  
   - **Nom** : CLIWIN01  
   - **Compte utilisateur** : wilder (dans le groupe des admins locaux)  
   - **Mot de passe** : Azerty1*  
   - **Adresse IP fixe** : 172.16.10.20/24

2. **Client Ubuntu 22.04/24.04 LTS**  
   - **Nom** : CLILIN01  
   - **Compte utilisateur** : wilder (dans le groupe sudo)  
   - **Mot de passe** : Azerty1*  
   - **Adresse IP fixe** : 172.16.10.30/24

### Serveurs
1. **Serveur Windows Server 2022**  
   - **Nom** : SRVWIN01  
   - **Compte** : Administrator (dans le groupe des admins locaux)  
   - **Mot de passe** : Azerty1*  
   - **Adresse IP fixe** : 172.16.10.5/24

2. **Serveur Debian 12**  
   - **Nom** : SRVLX01  
   - **Compte** : root  
   - **Mot de passe** : Azerty1*  
   - **Adresse IP fixe** : 172.16.10.10/24

## Détails Techniques

- Le script s'exécute sur un serveur **Windows Server 2022** sous **PowerShell Core 7.4 LTS**.
- Le script peut avoir plusieurs dépendances de fichiers.
- Le script s'exécute également sur un serveur **Debian 12**, utilisant les commandes et instructions shell bash.

## Fonctionnalités

Lors de l'exécution du script, un menu s'affiche, proposant une navigation ergonomique avec des sous-menus :
1. Choisir une **cible**, qui peut être un ordinateur ou un utilisateur.
2. Choisir une/des **action(s)** à effectuer ou une recherche d'information.

### Actions Disponibles

#### Sur les Utilisateurs
- Création de compte
- Suppression de compte
- Autres actions possibles

#### Sur les Ordinateurs Clients
- Arrêt
- Redémarrage
- Autres actions possibles

### Recherche d'Information
On choisit une information ou un lot d'informations :
- **Pour une seule information** : affichage de l'information et enregistrement.
- **Pour plusieurs informations** : enregistrement uniquement.

#### Informations sur les utilisateurs :
- Date de dernière connexion d’un utilisateur  
- Autres informations possibles

#### Informations sur les ordinateurs clients :
- Version de l'OS  
- Autres informations possibles

## Journalisation

La journalisation, également connue sous le nom de logging, consiste à enregistrer de manière systématique les événements significatifs qui se produisent dans un système, une application ou un réseau.  
Les informations enregistrées incluent souvent :
- Les timestamps
- Les actions effectuées
- Les utilisateurs concernés
- Les machines cibles


