# **Conception architecturale d'une application de gestion de taches**

## **1. Introduction**

Il s'agit ici, de concevoir l'architecture d'une application de gestion de taches avec une interface simple, intuitive et lisible, créer les diagrammes d'architecture, définir la structure des dossiers et fichiers, rédiger le document de conception afin de permettre à un utilisateur d'organiser et de suivre ses activités quotidiennes.

## **2. Objectifs**

Les principaux objectifs du projet sont:

- Appliquer les principes d'architecture full stack
- Mise en place d'une architecture 3 tiers
- Définir une API REST
- Séparer clairement les différentes responsabilités
- Produire une documentation de conception détaillée
- Définir les flux de données et responsabilités 

## **3. Besoins Fonctionnels**

l'application doit permettre à l'utilisateur de:

- Créer une nouvelle tache
- Renseigner un titre
- Ajouter une description
- Définir une priorité
- Enregistrer automatiquement la date de création
- Modifier le titre d'une tache
- Modifier la description d'une tache
- Changer la priorité d'une tache
- Mettre à jour son statut (terminé / non terminé)

Afin de bien structurer les données, le serveur devra permettre de:

- Afficher la liste compléte des taches
- Avoir une vue globale sur les détails d'une tache
- Consulter les taches selon leur statut
- Supprimer une tache existante
- Confirmer l'action avant suppression

## **4. Besoins Non-Fonctionnels**

l'application devra garantir:

- Protection contre les injections SQL
- Validation des données 
- Protection des informations sensibles
- Traitement automatique des requetes 
- Assurer l'intégrité des données
- Gestion fluide des données
- Temps de chargement de page et réponse rapide
- Bonne structuration et compréhension 
- Bonne organisation
- Clarté et simplicité

## **5. Contraintes Techniques**

- Avoir une architecture 3 tiers
- Respecter un modèle client/serveur
- Avoir une communication sécurisée
- Etre accessible sur un navigateur web 
- Etre accessible sur différent système d'exploitation
- Avoir une structure de projet organisée
- Faire une séparation claire entre frontend et backend
- Avoir un diagramme d'architecture

## **6. Architecture du système**

les couches de notre architecture seont les suivantes:

- Frontend: pour l'interface utilisateur
- Backend: pour l'API REST
- Base de données: pour le stockage des informatio    ns

Voici un schéma logique démonstratif:

Utilisateur 
    |
    v
Front-end (React)
    |API REST
    v
Back-end (Node)
    |
    v
Base de données (MySQL / PostgreSQL)


### **6.1 Choix des technologies**

les technologies proposées sont les suivantes:

| Couche | Technologie |
|--------|-------------|
| Frontend | React.js |
| Backend | Node.js |
| Base de données | MySQL / PostgreSQL |
| Communication | API REST |
| Versionning | Git |

### **6.2 Responsabilités de chaque composants**

*Pour le Frontend*
- Affichage et rendu de l'interface utilisateur
- Gestion des interactions utilisateur (clics, saisies, navigation)
- Validation côté client (première ligne de défense)
- Gestion de l'état local de l'application
- Communication avec le back-end via des requêtes HTTP
- Optimisation des performances côté client

*Pour le Backend*
- Traitement de la logique métier complexe
- Authentification et autorisation des utilisateurs
- Validation rigoureuse des données (sécurité)
- Gestion des sessions et des tokens
- Communication avec la base de données
- Exposition d'APIs pour le front-end
- Gestion des erreurs et logging

*Pour la base de données*
- Stockage permanent des données
- Gestion des transactions (ACID)
- Maintien de l'intégrité référentielle
- Optimisation des requêtes et indexation
- Gestion de la concurrence d'accès
- Sauvegarde et récupération des données

## **7. Modélisation des données**

**Table: tasks**

| Champ | Type | Description |
|-------|------|-------------|
| id | INT | Identifiant unique |
| title | VARCHAR | Titre de la tache |
| description | TEXT | Description |
| priority | ENUM | Priorité |
| status | BOOLEAN | État de la tache |
| created_ad | DATE | Date de création |

## **8. Endpoints de l'API**

les Endpoints principaux avec implémentation du CRUD sont les suivants:

| CRUD | Méthode | URL | Action |
|------|---------|-----|--------|
| Create | POST | /tasks | Créer une tache |
| Read | GET | /tasks | Récupérer/ lire les taches |
| Update | PUT | /tasks/:id | Modifier une tache |
|Delete | DELETE | /tasks/:id | Supprimer une tache |

## **9. Flux des données**

L’utilisateur interagit avec l’interface
               |
               v  
Le front-end envoie une requête HTTP
               |
               v 
L’API traite la requête
               |
               v  
Les données sont enregistrées ou récupérées
               |
               v  
Une réponse JSON est retournée
               |
               v  
L’interface est mise à jour  

## **10. Structure du projet**

'''
├── LICENSE
├── README.md
├── taskflow
│   ├── backend
│   │   ├── config
│   │   ├── controllers
│   │   ├── models
│   │   └── routes
│   └── frontend
│       └── src
│           ├── components
│           ├── pages
│           └── services
'''

**Explication**

- frontend/ : contient l’interface utilisateur développée avec React.

- components/ : regroupe les composants réutilisables.

- services/ : contient la gestion des appels API.

- pages/ : structure les différentes vues de l’application.

- backend/ : contient la logique serveur.

- controllers/ : gèrent le traitement des requêtes.

- models/ : représentent la structure des données.

- routes/ : définissent les endpoints REST.

- config/ : contient la configuration de la base de données.

## **11. Conclusion**

Ce projet permet de conception architecturale permet de mettre en avant les bases d'un projet full stack.