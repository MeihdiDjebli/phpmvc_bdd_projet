# BIAG

La Bibliothèque Internationale de l'Abbé Grégoire (BIAG) possède le catalogue de livre le plus important au monde.

5 catégories de livres sont gérées par la BIAG :

1. Actualité
2. Jeunesse
3. Sciences
4. Esotérisme
5. Arts

La BIAG est un bâtiment de 5 étages. Il existe 1 étage par catégorie de livre. Les livres d'une catégorie sont rangés par ordre alphabétique du nom de l'auteur.
Chaque livre possède :

* un identifiant unique appelé International Standard Book Number (ISBN),
* un titre,
* une catégorie,
* une langue,
* un résumé,
* un éditeur,
* un ou plusieurs auteurs
* éventuellement des mots clés associés.

Les adhérents à la BIAG sont des universitaires ou non-universitaires. Pour être adhérent, il faut indiquer son nom, prénom, date de naissance et adresse email.

Un universitaire peut emprunter autant d'ouvrages qu'il le souhaite alors qu'un non-universitaire peut seulement emprunter 3 ouvrages à la fois.
Chaque emprunt est limité dans le temps : de 1 à 90 jours.
Les adhérents ont une date de début et de fin de validité en dehors de laquelle ils ne sont plus considérés comme adhérent et donc ne peuvent plus emprunter.

La BIAG souhaite un outil de gestion du catalogue de livres et des emprunts. L'équipe est constituée d'une conservatrice et de 10 bibliothécaires.

# Installation des sources et lancement des conteneurs

1. Téléchargez ou clonez ce dépôt sur votre machine ;
2. Depuis une console de commande, dans le dossier contenant les sources, exécutez la commande `docker-compose up -d` ;
3. 1 conteneur Apache + PHP est accessible depuis http://localhost, 1 conteneur MySQL est créé et visualisable avec l'outil PHPMyAdmin depuis http://localhost:8080 ;

Pour vous connecter à PHPMyAdmin vous aurez besoin de :

- Serveur : db
- Utilisateur : root
- Mot de passe : root

Les sources PHP/HTML/CSS/Javascript doivent impérativement être insérées dans le dossier /src.

# BDD

A remplir

# PHP MVC

## Fonctionnalités

L'outil doit permettre :

ATTENTION chaque fonctionnalité doit respecter les règles énoncées ci-dessus.
Le projet est noté 30 / 20. Tous les points ne sont donc pas forcément à réaliser mais plus vous effectuerez de fonctionnalités et plus vous augmenterez vos chances d'obtenir la note maximale (20).

- La création / modification / suppression d'un ouvrage par un utilisateur 5
- La création / modification / suppression d'un adhérent par un utilisateur 5
- La création / modification / suppression d'un utilisateur (simple utilisateur ou conservateur) par un conservateur 3
- L'authentification des utilisateurs 2
- La recherche d'un ouvrage par titre (tout ou partie), auteur ou catégorie 5
- L'emprunt d'un ouvrage par un adhérent ; 5
- Le retour d'un ouvrage par un adhérent en indiquant s'il y a eu dépassement ; 2
- La recherche des adhérents ayant dépassé la date limite de retour de leur emprunt ; 3

L'utilisation du patron MVC est conseillé.
Le langage PHP 8.1 est à utiliser pour le traitement des requêtes et la liaison avec un système de gestion de base de données relationnelles (SGBDR).

Le HTML et le CSS sont à utiliser pour les interfaces.

Le Javascript peut être utilisé si cela permet une plus-value en terme d'expérience utilisateur.

## Modalités de dépôt

Le dépôt de votre projet au format archive (.zip, .rar, ...) se fera sur l'espace Moodle PHP MVC. L'archive doit contenir :

- Toutes les sources dans un dossier /src ;
- Le fichier ./docker-compose.yaml ;
- Le fichier /database/init.sql contenant un export brut de votre base de données (création de la structure + insertion des données minimales).
La commande `docker-compose exec db sh -c 'exec mysqldump --all-databases -uroot -p"$MYSQL_ROOT_PASSWORD"' > database/init.sql` 
effectue un export brut (ATTENTION vous devez exécuter cette commande depuis le dossier contenant le fichier docker-compose.yml)