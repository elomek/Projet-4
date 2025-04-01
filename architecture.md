# Architecture du Projet

Ce diagramme représente l'architecture du projet utilisant Django REST Framework, PostgreSQL, Celery, Redis, JWT, AJAX, Bootstrap et HTML.

```mermaid
graph TD;
    User[Utilisateur (Frontend: HTML, Bootstrap, AJAX)] -->|Envoie des requêtes| API[Django API (Django REST Framework)]
    API -->|Traite les requêtes| DB[Base de données PostgreSQL]
    API -->|Envoie des tâches| Celery[File de tâches Celery]
    Celery -->|Gère les tâches| Redis[File d'attente Redis]
    Celery -->|Effectue l'analyse de sentiment| NLPModel[Modèle IA d'Analyse de Sentiment]
    NLPModel -->|Stocke les résultats| DB
    API -->|Renvoie la réponse| User
    User -->|S'authentifie| JWT[Authentification JWT]
