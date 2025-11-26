# GraphQL

Un microservice GraphQL Spring Boot pour la gestion de comptes bancaires (Comptes) avec support de différents types de comptes.

## Vidéo

<!-- Ajoutez votre vidéo ici -->

---

## Description

Cette application fournit une API GraphQL pour la gestion de comptes bancaires. Elle supporte :
- Création et consultation de comptes
- Deux types de comptes : COURANT et EPARGNE
- Statistiques de soldes (total, nombre, moyenne)

## Structure du Projet

```
GraphQL/
├── src/
│   ├── main/
│   │   ├── java/ma/projet/graph/
│   │   │   ├── controllers/
│   │   │   │   └── CompteControllerGraphQL.java    # Résolveurs GraphQL
│   │   │   ├── entities/
│   │   │   │   ├── Compte.java                     # Entité Compte
│   │   │   │   └── TypeCompte.java                 # Énumération type de compte
│   │   │   ├── repositories/
│   │   │   │   └── CompteRepository.java           # Couche d'accès aux données
│   │   │   ├── exeption/
│   │   │   │   └── GraphQLExceptionHandler.java    # Gestion des erreurs
│   │   │   └── GraphApplication.java               # Application principale
│   │   └── resources/
│   │       ├── graphql/
│   │       │   └── schema.graphqls                 # Schéma GraphQL
│   │       └── application.properties
│   └── test/
└── pom.xml
```

## Démarrage

Lancer l'application :
```bash
mvn spring-boot:run
```

Point d'accès GraphQL : `http://localhost:8080/graphql`

## Opérations GraphQL

**Requêtes :**
- `allComptes` - Obtenir tous les comptes
- `compteById(id: ID)` - Obtenir un compte par ID
- `totalSolde` - Obtenir les statistiques de soldes (nombre, somme, moyenne)

**Mutations :**
- `saveCompte(compte: CompteRequest)` - Créer un nouveau compte
