# Projet-cours-G1

# Projet 1 : Cours

## mois
- id
- nom_mois

## module
- id
- nom_module
- description
- id_mois [FK]

## chapitre
- id
- titre_chapitre
- id_module [FK]

## cours
- id
- titre_cours
- contenu
- id_chapitre [FK]

## user
- id
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
- id
- nom
- prenom
- email
