# Hospital Management Application
## Auteurs

- **Nom :** Ayyoub  
- **Prénom :** Ait mansour 
- **Filière :**SDIA
- **TP :** TP1

Ce projet est une application web Java EE basée sur Spring Boot 3.5.0, Spring MVC, Thymeleaf, Spring Data JPA et Spring Security. Elle permet de gérer les patients avec des fonctionnalités comme l'affichage, la pagination, la recherche, la suppression, la validation des formulaires et une sécurité robuste.

## Table des matières
- [Prérequis](#prérequis)
- [Installation](#installation)
- [Fonctionnalités](#fonctionnalités)
- [Structure du projet](#structure-du-projet)
- [Configuration de sécurité](#configuration-de-sécurité)
- [Contributeurs](#contributeurs)

## Prérequis
- Java 17 ou une version supérieure
- Maven 3.6+
- Un IDE (comme IntelliJ IDEA ou Eclipse)
- Une base de données (H2 est inclus pour le développement)


# Fonctionnalités
```
Affichage des patients : Affiche une liste paginée des patients.
Pagination : Permet de naviguer entre les pages de la liste.
Recherche : Recherche des patients par leur nom.
Suppression : Supprime un patient (réservée aux administrateurs).
Ajout/Modification : Fournit un formulaire pour ajouter ou modifier un patient avec validation.
Détails du patient : Affiche les détails d’un patient spécifique.
Sécurité :
Authentification en mémoire avec des utilisateurs prédéfinis.
Rôles : USER et ADMIN.
Protection des accès (par exemple, la suppression est réservée aux admins).
```
# Structure du projet
```
net.ayyoub.hospital/
├── entities/
│   ├── Patient.java         # Entité Patient avec validation
│   └── User.java           # Entité User pour la sécurité
├── repository/
│   ├── PatientRepository.java  # Repository JPA pour Patient
│   └── UserRepository.java    # Repository JPA pour User
├── web/
│   ├── LoginController.java   # Contrôleur pour la page de login
│   └── PatientController.java # Contrôleur pour la gestion des patients
├── HospitalApplication.java   # Classe principale Spring Boot
├── SecurityConfig.java       # Configuration de la sécurité
├── resources/
│   ├── templates/
│   │   ├── error.html        # Page d'erreur
│   │   ├── formPatient.html  # Formulaire pour ajouter/modifier
│   │   ├── login.html        # Page de login
│   │   ├── patientDetails.html # Détails d'un patient
│   │   └── patients.html     # Liste des patients
│   └── application.properties # Configuration de l'application
└── test/                    # Tests (si applicable)
```

# Configuration de sécurité
## Authentification en mémoire
```
Utilisateurs prédéfinis :
    user1 / SDIA (rôle : USER)
    user2 / SDIA (rôle : USER)
    admin / SDIA (rôles : USER, ADMIN)
```
## Endpoints protégés
```
/deletePatient/** et /admin/** : Accessible uniquement aux utilisateurs avec le rôle ADMIN.
/user/** : Accessible uniquement aux utilisateurs avec le rôle USER.
/login, /error, /webjars/**, /css/** : Accessible à tous.
```
