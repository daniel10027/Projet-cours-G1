# Projet-cours-G1

# Projet 1 : Cours

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


# remarques

## admin
- id [PK]
- nom
- prenom
- email
