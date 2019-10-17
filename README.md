# Projet-cours-G1

# Projet 1 : Cours

## Les tables

### mois
- id [PK]
- nom_mois

### module
- id [PK]
- nom_module
- description
- id_mois [FK]

### chapitre
- id [PK]
- titre_chapitre
- id_module [FK]

### cours
- id [PK]
- titre_cours
- contenu
- id_chapitre [FK]

### user
- id [PK]
- username
- nom
- prenom
- email
- password

### progression
- id_module
- id_user

### admin
- id [PK]
- nom
- prenom
- email
- password
- id_module [FK]

Legende: PK = PRIMARY KEY, FK = FOREIGN KEY

## le code sql

### mois

CREATE TABLE mois (
id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
nom_ois VARCHAR(50) NOT NULL,);

### module
CREATE TABLE module (
id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
description TEXT NOT NULL,
nom_module VARCHAR(50) NOT NULL,
id_mois INT NOT NULL FOREIGN KEY);

### chapitre
CREATE TABLE chapitre (
id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
titre_chapitre VARCHAR(50) NOT NULL,
id_module INT NOT NULL FOREIGN KEY);

### cours
CREATE TABLE cours (
id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
titre_cours VARCHAR(50) NOT NULL,
id_chapitre INT NOT NULL FOREIGN KEY);

### media
CREATE TABLE media (
id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
video BLOB NOT NULL,
id_cours INT NOT NULL FOREIGN KEY);

### user
CREATE TABLE user (
id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
nom VARCHAR(50) NOT NULL,
prenom VARCHAR(50) NOT NULL,
email VARCHAR(50) NOT NULL,
password VARCHAR(50) NOT NULL);

### progression
CREATE TABLE progression (
id_user INT NOT NULL,
id_module INT NOT NULL);

### admin

CREATE TABLE admin (
id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
nom VARCHAR(50) NOT NULL,
prenom VARCHAR(50) NOT NULL,
email VARCHAR(50) NOT NULL,
password VARCHAR(50) NOT NULL,
id_module INT NOT NULL FOREIGN KEY);

# Projet 2 : plateforme zalando
## les tables

### genre
- id_genre
- nom_genre

### genre-categorie
- id_genre
- id_categorie

### categorie
- id_categorie
- nom_categorie
- id_type [FK]

### sous-categorie
- id_sous_categorie
- nom_sous_categorie

### type
- id_type
- nom_type

### categorie-sous_categorie
- id_categorie
- id_sous_categorie

### article
- id_article
- prix_article
- photo_article
- nom_article
- couleur_article
- id_taille [FK]

### taille
- id_taille
- nom_taille

### user
- id_user
- nom_user
- prenom_user
- date_naissance_user
- email_user
- password_user
- sexe_user

### preferences
- id_preference
- id_article [FK]
- id_user [FK]

### commande
- id_commande
- id_article [FK]
- id_user [FK]

### media
- id_media
- photo
- id_article


## le code SQL

### genre
CREATE TABLE genre(
id_genre INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
nom_genre VARCHAR(50) NOT NULL,);

### genre
CREATE TABLE genre(
id_genre INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
nom_genre VARCHAR(50) NOT NULL);

### genre-categorie
CREATE TABLE genre-categorie(
id_genre INT NOT NULL,
id_categorie INT NOT NULL);

### categorie
CREATE TABLE categorie(
id_categorie INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
nom_categorie VARCHAR(50) NOT NULL,
id_type INT NOT NULL FOREIGN KEY);

### sous_categorie
CREATE TABLE sous-categorie(
id_sous_categorie INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
nom_sous_categorie VARCHAR(50) NOT NULL);

CREATE TABLE categorie(
id_categorie INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
nom_categorie VARCHAR(50) NOT NULL,
id_type INT NOT NULL FOREIGN KEY);

### type
CREATE TABLE type(
id_type INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
nom_type VARCHAR(50) NOT NULL);

### categorie-sous_categorie
CREATE TABLE categorie-sous_categorie(
id_genre INT NOT NULL,
id_sous_categorie INT NOT NULL);

### taille
CREATE TABLE taille(
id_taille INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
nom_taille VARCHAR(50) NOT NULL);

### preference
CREATE TABLE preference(
id_preference INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
id_article UNT NOT NULL FOREIGN KEY,
id_user INT NOT NULL FOREIGN KEY);

### commande
CREATE TABLE commande(
id_commande INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
id_article INT NOT NULL FOREIGN KEY,
id_user INT NOT NULL FOREIGN KEY);

### article
CREATE TABLE article(
id_article INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
nom_article VARCHAR(50) NOT NULL),
couleur_article VARCHAR(50) NOT NULL),
prix_article INT NOT NULL);

### media
CREATE TABLE media(
id_media INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
photo BLOB NOT NULL,
id_article INT NOT NULL FOREIGN KEY);
