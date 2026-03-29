# TP 15 — Conteneurisation avec Docker

## 📚 Cours
Développement JakartaEE : Spring 

---

## Contexte
Dans les environnements modernes, les applications sont déployées dans des conteneurs isolés pour garantir la portabilité. Ce TP vise à transformer une application Spring Boot en **Image Docker**, à l'exécuter, puis à orchestrer son fonctionnement avec une base de données **MySQL** via **Docker Compose**.

L'objectif est de passer d'un déploiement local manuel à une infrastructure conteneurisée reproductible sur n'importe quel serveur.

---

## Objectifs
*   **Dockerfile** : Construire une image personnalisée pour une application Spring Boot.
*   **Docker CLI** : Maîtriser les commandes de gestion des images et des conteneurs.
*   **Docker Compose** : Orchestrer multi-services (App + Base de données).
*   **Persistance** : Utiliser les volumes Docker pour conserver les données MySQL.
*   **Cloud** : Publier l'image sur Docker Hub.

---

## Technologies utilisées
- **Spring Boot 3.x** / Java 17
- **Docker & Docker Desktop**
- **Docker Compose**
- **MySQL 8.0**
- **Maven**
- **Docker Hub**

---

## Structure du Projet

<img width="1792" height="902" alt="image" src="https://github.com/user-attachments/assets/de7749e4-291c-48c8-8551-4a19448ee800" />

##  Construction et exécution de l’image Docker
1. Compiler et exécuter le projet localement pour s’assurer que tout fonctionne
- ###  mvn clean package
![WhatsApp Image 2026-03-29 at 15 05 41](https://github.com/user-attachments/assets/3ee6b25f-8806-4d4b-8be8-5ee5ccb29463)

![WhatsApp Image 2026-03-29 at 15 06 08](https://github.com/user-attachments/assets/2990e0ed-3c26-4e49-8c95-0e99a54a324f)

![WhatsApp Image 2026-03-29 at 15 06 33](https://github.com/user-attachments/assets/ee8587f2-3e0d-474f-96b3-be829483089c)

![WhatsApp Image 2026-03-29 at 15 06 54](https://github.com/user-attachments/assets/e3cc4736-cdb8-4380-ba8d-64141267769c)

- ### java -jar target/springdocker-0.0.1-SNAPSHOT.jar
  
![WhatsApp Image 2026-03-29 at 16 02 04](https://github.com/user-attachments/assets/64291954-20a7-4a8d-a7eb-85be81ebf16d)

![WhatsApp Image 2026-03-29 at 16 02 28](https://github.com/user-attachments/assets/46a71c6d-562e-4e05-8659-3ae8ed47c197)

2. Construction de l’image :

![WhatsApp Image 2026-03-29 at 16 09 11](https://github.com/user-attachments/assets/bd22867f-8b8e-4819-8d34-a4612054ce06)

3. Vérification de l’image :

![WhatsApp Image 2026-03-29 at 16 10 52](https://github.com/user-attachments/assets/07e2c3ba-e5cc-49d7-a1e4-6996bd78acad)

4. Exécution du conteneur :

![WhatsApp Image 2026-03-29 at 16 32 11](https://github.com/user-attachments/assets/678ededa-0cc3-48f5-89f1-4f6bd8afc5c4)

5. Vérifier les logs :

![WhatsApp Image 2026-03-29 at 16 38 41](https://github.com/user-attachments/assets/c09f1c7e-25f8-4d7c-85b5-6a2dff829da5)

6. Arrêter et supprimer le conteneur :

![WhatsApp Image 2026-03-29 at 16 43 29](https://github.com/user-attachments/assets/fa34e3c1-7bfc-4cf4-8b46-a472ff095618)

## Exécution avec Docker Compose 

1. Démarrer les conteneurs :

![WhatsApp Image 2026-03-29 at 16 54 30](https://github.com/user-attachments/assets/d8b8f00c-333e-473f-987e-0ea1dcd5dbac)

2. Vérifier les services actifs :

![WhatsApp Image 2026-03-29 at 16 56 33](https://github.com/user-attachments/assets/129c982e-2b6d-4e04-9258-d3f5da4cb5eb)

3. Afficher les logs :

![WhatsApp Image 2026-03-29 at 16 57 59](https://github.com/user-attachments/assets/91ab386d-c4e3-4bdf-bb86-17f4dd891053)

4. Arrêter l’environnement :

![WhatsApp Image 2026-03-29 at 16 59 06](https://github.com/user-attachments/assets/e68fce1d-304d-4589-9e41-6a6ada2a39e3)

## Vérifications :

- #### Validation de la persistance des données et accès au CLI MySQL via Docker Desktop.

![WhatsApp Image 2026-03-29 at 17 30 32](https://github.com/user-attachments/assets/0cdf8fb0-1e37-410b-bbac-35bde0fe9a96)

![WhatsApp Image 2026-03-29 at 17 44 35](https://github.com/user-attachments/assets/d64035fa-a7b1-4161-a3a7-fbd97be58bba)

![WhatsApp Image 2026-03-29 at 18 43 20](https://github.com/user-attachments/assets/4dc1c622-d804-4871-bbad-76a028b89618)

## Extensions :

1. Ajouter phpMyAdmin dans docker-compose.yml pour gérer visuellement la base.

![WhatsApp Image 2026-03-29 at 17 55 06](https://github.com/user-attachments/assets/311242e9-aa2b-4ee5-aec3-2748a6ecea46)

#### Cela te permettra de voir tes tables sans passer par le terminal noir de Docker Desktop.

![WhatsApp Image 2026-03-29 at 17 57 49](https://github.com/user-attachments/assets/656e1128-3bac-47ae-911c-bbec9559c456)

2. Créer une image personnalisée et la publier sur Docker Hub :

- ### Connexion au compte Docker Hub dans le  terminal :

![WhatsApp Image 2026-03-29 at 18 13 01](https://github.com/user-attachments/assets/2e926d08-9f64-4d0e-8626-79a835f46962)


![WhatsApp Image 2026-03-29 at 18 28 54](https://github.com/user-attachments/assets/5aebfa98-a8d2-4b03-8a31-9681424bf1fe)


## Conclusion
Ce TP m'a permis de comprendre le cycle de vie d'une application conteneurisée. Grâce à Docker, l'adage "ça marche sur ma machine" disparait au profit
d'une infrastructure code (Dockerfile et docker-compose.yml) garantissant un déploiement identique en développement et en production.
