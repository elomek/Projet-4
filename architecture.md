# Architecture du Projet

Ce diagramme représente l'architecture du projet utilisant Django REST Framework, PostgreSQL, Celery, Redis, JWT, AJAX, Bootstrap et HTML.

```mermaid
graph TD
    User --> API
    API --> DB
    API --> Celery
    Celery --> Redis
    Celery --> NLPModel
    NLPModel --> DB
    API --> User
    User --> JWT

