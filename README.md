# Gestion de Base de Données Cassandra avec Spring Boot

## Aperçu
Ce dépôt GitHub renferme les ressources nécessaires pour la manipulation pratique d'une base de données Cassandra à l'aide de Spring Boot. L'objectif principal est d'illustrer l'intégration harmonieuse entre une application Spring Boot et Cassandra, une base de données NoSQL, à travers la gestion d'une table de produits dans un keystore.

### Technologies Utilisées

* Spring Boot
* Cassandra
* Spring Data Cassandra
* Swagger UI

## Fonctionnalités Principales

Cette application Spring Boot offre les fonctionnalités suivantes :

- **Ajout de Produits** : Permet l'ajout d'un nouveau produit dans la base de données.
- **Consultation de Produits** : Récupération des détails d'un produit par son identifiant UUID.
- **Mise à Jour de Produits** : Permet de mettre à jour les informations d'un produit existant.
- **Suppression de Produits** : Permet de supprimer un produit de la base de données.
- **Recherche de Produits** : Permet de rechercher des produits en fonction d'un mot-clé dans leur nom.

## Utilisation

- **Démarrage de Cassandra avec Docker :** Veuillez vous assurer que Docker est installé et opérationnel.
- **Accès à l'API via Swagger UI :** Après le démarrage de l'application, accédez à Swagger UI pour interagir avec l'API :

```bash
http://localhost:8080/swagger-ui.html
```

## Architecture du Projet

- **Entité Produit**: Modèle de données pour les produits.
- **ProductRepository**: Interface pour les opérations CRUD sur Cassandra.
- **ProductServices**: Couche de service fournissant des méthodes pour la gestion des produits.
- **ProductRestAPI**: Contrôleur REST pour interagir avec l'application via HTTP.

## Configuration Technique

### Utilisation de Cassandra dans Docker
```yaml
version: '3'
services:
  cassandra:
    image: cassandra:latest
    container_name: cassandra
    environment:
      - CASSANDRA_DC=dc1
      - CASSANDRA_ENDPOINT_SNITCH=GossipingPropertyFileSnitch
    ports:
      - '9042:9042'
```

## Dépendances Maven

Incluez les dépendances suivantes dans votre fichier `pom.xml` pour bénéficier des fonctionnalités de Spring Boot, Cassandra et Swagger UI:

```xml
<!-- Swagger UI pour la Documentation API -->
<dependency>
    <groupId>org.springdoc</groupId>
    <artifactId>springdoc-openapi-starter-webmvc-ui</artifactId>
    <version>2.1.0</version>
</dependency>

<!-- Prise en charge des Données Cassandra et Web -->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-cassandra</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>

<!-- Intégration Docker Compose -->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-docker-compose</artifactId>
    <scope>runtime</scope>
    <optional>true</optional>
</dependency>
```
# Par : Nouhayla MOUAKKAL | II-BDCC2 
## TP6 - Module : Big Data : Architectures de stockages