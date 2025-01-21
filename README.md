
# README - Site E-commerce de Manga

Ce projet est une application web permettant d'acheter des mangas en ligne. L'utilisateur peut parcourir la collection, choisir une quantité et ajouter les articles à son panier. Le site comprend un système d'authentification pour gérer les comptes utilisateurs.

---

## Prérequis 

- **Serveur local** :
  - [WAMP](https://www.wampserver.com/) (Windows)
  - [MAMP](https://www.mamp.info/) (Mac)
  - [XAMPP](https://www.apachefriends.org/) (Windows, Mac, Linux)
- **Base de données MySQL** (inclus dans WAMP/MAMP/XAMPP).
- **Éditeur de code** comme [Visual Studio Code](https://code.visualstudio.com/).

---

## Installation

1. **Récupération du code**:
   - Crée un dossier et clonez le dépôt en utilisant la commande suivante :
   ```git
   git clone https://github.com/Karuran12/Projet-README/tree/main
   ```

2. **Configurer le serveur local**:
   - Démarrez votre serveur WAMP, MAMP ou XAMPP.
   - Placez le dossier cloné dans le répertoire `htdocs` (MAMP) ou `www` (WAMP/XAMPP).

3. **Base de Donnée**:

    - ### **Table**
Voici à quoi doit ressembler la table utilisateur: 
| Champ    | Type          | Description                                |
|----------|---------------|--------------------------------------------|
| id       | INT (PRIMARY) | ID unique de l'utilisateur.               |
| name     | VARCHAR(100)  | Nom de l'utilisateur.                     |
| password | VARCHAR(255)  | Mot de passe haché.                       |
| cree     | TIMESTAMP     | Date et heure de création du compte.      |

Voici à quoi doit ressembler la table livres: 

| Champ       | Type          | Description                                  |
|-------------|---------------|----------------------------------------------|
| id          | INT (PRIMARY) | ID unique du livre.                         |
| photo       | VARCHAR(255)  | Chemin vers l'image de couverture.          |
| titre       | VARCHAR(255)  | Titre du manga.                             |
| auteur      | VARCHAR(255)  | Auteur du manga.                            |
| description | TEXT          | Description détaillée.                      |
| prix        | DECIMAL(10,2) | Prix du manga.                              |
| categorie   | VARCHAR(100)  | Catégorie du manga (Action, Aventure, etc.).|
| stock       | INT           | Quantité disponible en stock. 

Voici à quoi doit ressembler la table panier: 

| Champ       | Type          | Description                                   |
|-------------|---------------|-----------------------------------------------|
| id          | INT (PRIMARY) | ID unique pour chaque entrée.                |
| user_id     | INT           | Référence à l'utilisateur (clé étrangère).   |
| livre_id    | INT           | Référence au manga (clé étrangère).          |
| quantite    | INT           | Quantité de manga dans le panier.            |
| date_ajout  | TIMESTAMP     | Date et heure d'ajout au panier.             |



Voici le [fichier ](./manga.sql) qui contient le code SQL à exécuter sur MySQL. 

4. **Modifaction à effectuer dans le code**:
    - modifier la ligne 5 de [route.php](./controller/route.php) qui ce trouve dans le dossier Controller avec vos information personnelle.

    ```php
    $pdo = new PDO("mysql:host=localhost;port=<votre_port>;dbname=manga", "<votre_nom_utilisateur>", "<votre_mots_de_passe>");
    ```

5. **Lancer le site**:
    - Ouvrez votre navigateur et accédez à http://localhost/<nom_du_dossier>/index.php?page=accueil

5. **Modification et voir**: 
    - Ouvrir le dossier placée dans le répertoire de votre serveur sur votre éditeur de code.

---

## Fonctionnalités 

- **Page d'accueil :** Affiche les mangas avec leurs titres, prix, images, disponibilités et descriptions.
- **Système d'authentification :** Inscription, connexion et déconnexion.
- **Page du Panier :** Ajouter des mangas au panier, visualiser le total.
___


## Comment ça marche ?

1. **Inscription / Connexion :** Créez un compte ou connectez-vous pour commencer.
2. **Page d'accueil :** Explorez notre collection de mangas. Sélectionnez la quantité de vos mangas et envoyez les à la page paniet.
3. **Ajouter au Panier :**  Regardez les mangas selectionner avec la quantité et le prix total. 
___

## Langages utilisés

- PHP
- HTML
- CSS
___

## Collaborateurs

- **Techlead :** [Karuran GAJAROOBAN](https://github.com/Karuran12)
- **Développeur Fullstack :** [Craig Armel YOUAKOUA TCHOUSSOKNOU](https://github.com/craigarmel)

Nous nous engageons à offrir la meilleure expérience d'achat en ligne pour les amateurs de manga. N'hésitez pas à nous contacter pour toute question ou assistance.
