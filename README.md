# Projet-cours-G1

# Projet 1 : Cours

## Les tables

## mois
- id [PK]
- nom_mois

## module
- id [PK]
- nom_module
- description
- id_mois [FK]

## chapitre
- id [PK]
- titre_chapitre
- id_module [FK]

## cours
- id [PK]
- titre_cours
- contenu
- id_chapitre [FK]

## user
- id [PK]
- username
- nom
- prenom
- email
- password

## progression
- id_module
- id_user


## admin
- id [PK]
- nom
- prenom
- email
- password
- id_module [FK]

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
