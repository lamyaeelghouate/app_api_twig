# API Symfony avec Authentification JWT

## Description

Ce projet implémente une API RESTful à l'aide de Symfony. L'API permet de gérer des entités via des opérations CRUD (Créer, Lire, Mettre à jour, Supprimer) et est sécurisée avec une authentification JWT.

## Objectifs

1. Concevoir une API RESTful avec Symfony.
2. Gérer les données via des opérations CRUD (produits, user).
3. Sécuriser l'API avec un mécanisme d'authentification basé sur JWT (JSON Web Tokens).
4. Utiliser Git pour versionner le code.
5. Tester et documenter les endpoints de l'API avec Postman.

## Prérequis

Avant de commencer, assurez-vous que vous avez les éléments suivants :

- **PHP** installé (version 8.0 ou supérieure).
- **Composer** installé.
- **Symfony CLI** installé (facultatif mais recommandé).
- **Base de données** configurée (MySQL ou PostgreSQL).
- **Postman** installé pour tester l'API.

## Installation

### 1. Cloner le projet

Clonez ce projet dans votre répertoire local à l'aide de Git :

```bash
git clone https://github.com/lamyaeelghouate/app_api_twig
cd projet

## Utilisation de l'API

L'API permet d'effectuer diverses opérations sur les ressources, telles que les produits ou autres entités définies dans votre projet. Les opérations sont sécurisées par JWT, sauf celles qui ne nécessitent pas d'authentification, comme l'authentification des utilisateurs.

### Endpoints disponibles

#### 1. **GET /api/products**
- **Description** : Récupère la liste de tous les produits.
- **Réponse** : Liste de produits avec leurs informations.
- **Exemple de réponse** :
```json
[
    {
        "id": 1,
        "name": "Produit 1",
        "price": 2999
    },
    {
        "id": 2,
        "name": "Produit 2",
        "price": 4999
    }
]

## Authentification JWT
L'API utilise JWT pour sécuriser l'accès à certains endpoints, comme la création, la mise à jour et la suppression des produits. Pour obtenir un token JWT, vous devez vous authentifier via l'endpoint /api/login_check.

### 1. POST /api/login_check
Description : Authentifie un utilisateur et génère un token JWT.
Requête :
json
Copy code
{
    "username": "test@test.com",
    "password": "password"
}
## Réponse :
json
Copy code
{
    "token": "votre_token_jwt"
}
Utilisez ce token dans l'en-tête Authorization: Bearer {votre_token_jwt} pour interagir avec les endpoints sécurisés.


## Tester avec Postman

Collection Postman
Authentification : Utilisez l'endpoint /api/login pour obtenir un token JWT.
CRUD des produits : Utilisez les autres endpoints (GET, POST, PUT, DELETE) pour tester les opérations CRUD.
Exemple de test dans Postman
Authentification :

Méthode : POST
URL : http://localhost:8000/api/login_check
Body :
json
Copy code
{
    "username": "utilisateur",
    "password": "motdepasse"
}
Création de produit :

### Méthode : POST
URL : http://localhost:8000/api/products
Headers :
json
Copy code
{
  "Authorization": "Bearer votre_token_jwt"
}
Body :
json
Copy code
{
    "name": "Produit Exemple",
    "price": 2999
}



