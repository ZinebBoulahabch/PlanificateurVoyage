# Cahier des Charges - DevNetwork

## 1. Contexte et Définition du Projet
DevNetwork est une plateforme web moderne destinée aux développeurs pour partager leurs projets, collaborer, évaluer le travail des autres et rechercher des profils de développeurs. La plateforme vise à créer un écosystème dynamique où les développeurs peuvent se connecter, partager leurs réalisations et développer leur réseau professionnel.

### Problématique :
- Manque de visibilité pour les projets personnels des développeurs
- Difficulté à trouver des collaborateurs ou des mentors
- Absence d'un système unifié pour évaluer et commenter le travail des autres développeurs

### Contraintes Techniques :
- Framework : Django 5.0.7
- Base de données : PostgreSQL
- API : Django REST Framework 3.15.2
- Authentification : Django REST Framework SimpleJWT 5.3.1
- Stockage : AWS S3 (boto3, s3transfer)
- Gestion des fichiers statiques : Whitenoise 6.7.0

## 2. Objectifs
- Créer une plateforme centralisée pour les développeurs
- Faciliter la recherche de profils et projets
- Implémenter un système d'évaluation et de feedback
- Développer un système de messagerie interne
- Atteindre une base d'utilisateurs active de 70% dans les 6 premiers mois

## 3. Périmètre

### Cible :
- Développeurs web et logiciels
- Débutants et professionnels expérimentés
- Étudiants en développement

### Plateforme :
- Application web responsive
- Interface utilisateur moderne et intuitive
- API RESTful pour les futures extensions

### Fonctionnalités Principales :
- Système d'authentification sécurisé
- Gestion des profils développeurs
- Partage et gestion de projets
- Système de recherche avancée
- Système de notation et commentaires
- Messagerie interne
- Gestion des médias (images, fichiers)

### Exclusions :
- Application mobile native
- Système de paiement
- Fonctionnalités de streaming en direct

## 4. Parties Prenantes
- Développeurs (utilisateurs finaux)
- Équipe de développement
- Administrateurs système
- Modérateurs de contenu
- Investisseurs potentiels

## 5. Description des Besoins

### 5.1. Besoins Fonctionnels

| Fonctionnalité | Description | Contraintes | Priorité |
|----------------|-------------|-------------|-----------|
| Authentification | Inscription et connexion sécurisées | JWT, validation email | Haute |
| Profils | Gestion des profils développeurs | Photos, compétences, projets | Haute |
| Projets | Partage et gestion de projets | Limite de stockage, formats supportés | Haute |
| Recherche | Recherche de profils et projets | Full-text search PostgreSQL | Haute |
| Messagerie | Communication entre utilisateurs | Messages privés, notifications | Moyenne |
| Évaluation | Système de notation et commentaires | 5 étoiles, modération | Moyenne |

### 5.2. Besoins Non Fonctionnels

| Objectif | Description | Contraintes | Priorité |
|----------|-------------|-------------|-----------|
| Performance | Temps de réponse | < 2 secondes | Haute |
| Sécurité | Protection des données | JWT, HTTPS | Haute |
| Scalabilité | Support utilisateurs | 10,000+ simultanés | Haute |
| Disponibilité | Uptime | 99.9% | Haute |
| Compatibilité | Navigateurs | Modernes (Chrome, Firefox, Safari) | Haute |

## 6. Installation et Déploiement

### Prérequis :
- Python 3.8+
- PostgreSQL
- AWS Account (pour S3)
- Git

### Installation :
1. Cloner le repository :
```bash
git clone https://github.com/Emmetthazel/DevNetwork.git
```

2. Créer et activer l'environnement virtuel :
```bash
pip install virtualenv
virtualenv envname
envname\scripts\activate
```

3. Installer les dépendances :
```bash
cd devNetwork
pip install -r requirements.txt
```

4. Configurer les variables d'environnement :
- SECRET_KEY
- DATABASE_URL
- AWS_ACCESS_KEY_ID
- AWS_SECRET_ACCESS_KEY
- AWS_STORAGE_BUCKET_NAME

5. Lancer le serveur de développement :
```bash
python manage.py runserver
```

## 7. Sécurité et Maintenance
- Mises à jour régulières des dépendances
- Sauvegardes quotidiennes de la base de données
- Monitoring des performances
- Gestion des logs
- Plan de reprise d'activité

## 8. Évolutions Futures
- Intégration de fonctionnalités de collaboration en temps réel
- Système de recommandation de projets
- API publique pour les intégrations tierces
- Système de badges et récompenses
- Fonctionnalités de mentorat
