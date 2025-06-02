Description
Ce projet JARVIS est une API Django sécurisée qui permet la gestion de documents avec un système d'authentification basé sur des tokens JWT (JSON Web Tokens). Les utilisateurs doivent être authentifiés pour accéder aux endpoints et ne peuvent accéder qu'aux documents qu'ils possèdent.

+Fonctionnalités principales
-Authentification sécurisée via JWT (login, rafraîchissement de token)

-Permissions strictes pour l'accès aux documents (seul le propriétaire peut consulter un document)

-Endpoints RESTful pour gérer les documents

+Cloner le dépôt
git clone https://github.com/gargour/JARVIS.git
cd JARVIS

+Installer les dépendances  
pip install -r requirements.txt

python manage.py migrate
python manage.py makemigrations
+Authentification
Obtenir un token JWT (login) 
POST /api/token/
Content-Type: application/json

{
    "username": "votre_nom_utilisateur",
    "password": "votre_mot_de_passe"
}

Rafraîchir un token JWT :
POST /api/token/refresh/
Content-Type: application/json

{
    "refresh": "votre_token_de_refresh"
}
+Structure du projet
JARVIS/ : dossier principal de l’application Django

JARVIS/models.py : définition du modèle Document avec un champ owner (utilisateur propriétaire)

JARVIS/views.py : vue API sécurisée DocumentDetailView contrôlant les permissions d’accès

JARVIS/urls.py : routes incluant endpoints JWT et API

# Ce projet est encore en développement. Bonne utilisation !
