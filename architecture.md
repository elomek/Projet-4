graph TD
    User[Utilisateur (Frontend: HTML, Bootstrap, AJAX)] -->|Envoie des données| API[Django API (Django REST Framework)]
    API -->|Répond en JSON| Frontend
    User -->|S'authentifie avec| JWT[Authentification JWT]
    API -->|Valide l'authentification avec JWT| JWT
    API -->|Stocke dans la base de données| DB[Base de données PostgreSQL]
    API -->|Envoie des tâches d'analyse| Celery[Gestion des tâches Celery]
    Celery -->|Gère l'analyse des sentiments| NLPModel[Modèle d'analyse de sentiment]
    NLPModel -->|Envoie les résultats à| API
    API -->|Renvoie les résultats au frontend| Frontend
    Frontend -->|Affiche les résultats de l'analyse| User

