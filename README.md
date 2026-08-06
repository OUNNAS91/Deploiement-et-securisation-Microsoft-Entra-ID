# Déploiement et sécurisation d'un environnement Microsoft Entra ID

## Présentation

Ce projet a été réalisé dans le but d'apprendre à déployer, administrer et sécuriser un environnement Microsoft Entra ID (anciennement Azure Active Directory).

L'objectif est de comprendre les principes de la gestion des identités et des accès dans le cloud, tout en appliquant les bonnes pratiques de sécurité utilisées en entreprise.

Ce projet a été réalisé dans un environnement de laboratoire afin de reproduire des tâches couramment effectuées par un administrateur système.

## Objectifs du projet

- Découvrir Microsoft Entra ID
- Créer et administrer des utilisateurs
- Créer et gérer des groupes de sécurité
- Attribuer des rôles administratifs
- Gérer les méthodes d'authentification
- Ajouter une application d'entreprise
- Attribuer des utilisateurs à une application
- Désactiver un compte utilisateur
- Réinitialiser un mot de passe
- Consulter les journaux de connexion
- Consulter les journaux d'audit
- Appliquer les bonnes pratiques de sécurité

## Environnement utilisé

- Microsoft Entra ID (version gratuite)
- Portail Microsoft Azure
- GitHub
- Visual Studio Code
- Navigateur Web (Microsoft Edge)

## Déroulement du projet

### 1. Création du tenant Microsoft Entra ID

La première étape a consisté à créer un tenant Microsoft Entra ID afin de disposer d'un environnement cloud dédié à l'administration des identités.

Cette étape permet de mettre en place un espace d'administration dans lequel seront créés les utilisateurs, les groupes, les rôles et les applications.

### 2. Création des utilisateurs

Plusieurs utilisateurs ont été créés afin de représenter différents collaborateurs de l'entreprise.

Utilisateurs créés :

- Amar OUNNAS
- Marie Dupont
- Henri Durand
- Alexandre Dupont

Chaque utilisateur possède son propre compte Microsoft Entra ID.

### 3. Création des groupes

Deux groupes de sécurité ont été créés afin de faciliter la gestion des autorisations.

Groupes créés :

- IT-Admins
- SOC-Analystes

Les groupes permettent de gérer plus facilement les accès sans attribuer des autorisations individuellement à chaque utilisateur.

### 4. Attribution des rôles administratifs

Afin d'appliquer le principe du moindre privilège, les rôles administratifs ont été attribués selon les responsabilités de chaque utilisateur.

Répartition des rôles :

| Utilisateur     | Rôle                            |
|-----------------|---------------------------------|
| Amar OUNNAS     | Administrateur général          |
| Marie Dupont    | Administrateur des utilisateurs |
| Henri Durand    | Utilisateur standard            |
| Alexandre Dupont| Utilisateur standard            |

Le rôle Administrateur des utilisateurs permet à Marie Dupont de gérer les comptes utilisateurs sans disposer des droits complets d'un Administrateur général.

Cette configuration limite les risques en cas de compromission d'un compte administrateur.

### 5. Configuration des méthodes d'authentification

Les méthodes d'authentification disponibles dans Microsoft Entra ID ont été étudiées afin de comprendre les mécanismes permettant de sécuriser les connexions.

Méthodes observées :

- Microsoft Authenticator
- Clés de sécurité FIDO2
- SMS
- Jetons OATH
- Authentification basée sur certificat
- Code QR

Ces méthodes permettent de renforcer la sécurité des comptes en ajoutant des mécanismes supplémentaires lors de l'authentification.

### 6. Analyse des journaux de connexion

Les journaux de connexion Microsoft Entra ID permettent de surveiller les accès des utilisateurs.

Ils fournissent des informations telles que :

- l'utilisateur connecté ;
- l'application utilisée ;
- l'adresse IP ;
- le résultat de la connexion (réussite ou échec)

Ces journaux permettent de détecter des comportements inhabituels et d'analyser les incidents de sécurité.

### 7. Ajout d'une application d'entreprise

Une application d'entreprise GitHub Enterprise Cloud a été ajoutée dans Microsoft Entra ID.

Les applications d'entreprise permettent de centraliser l'authentification des utilisateurs et de contrôler les accès aux applications utilisées par l'organisation.

Application ajoutée :

- GitHub Enterprise Cloud - Enterprise Account

Cette intégration permet à Microsoft Entra ID de devenir le fournisseur d'identité pour l'application. Ainsi, les employés peuvent se connecter avec leur compte Entra ID sans créer un nouveau compte pour chaque service. L'application fait en quelque sorte confiance à Microsoft Entra ID pour authentifier les utilisateurs.

### 8. Attribution d'un utilisateur à une application

Afin de contrôler les accès, l'utilisateur Alexandre Dupont a été affecté à l'application GitHub Enterprise Cloud.

Cette configuration permet de définir précisément quels utilisateurs peuvent accéder à une application.

Utilisateur autorisé :

- Alexandre Dupont

### 9. Désactivation d'un compte utilisateur

Lorsqu'un collaborateur quitte une entreprise, son compte doit être désactivé afin d'empêcher toute nouvelle connexion.

Le compte d'Henri Durand a été désactivé afin de simuler le départ d'un utilisateur.

Cette action permet de bloquer immédiatement l'accès tout en conservant les informations nécessaires aux audits.

### 10. Réinitialisation d'un mot de passe

Une procédure de réinitialisation du mot de passe a été réalisée sur le compte d'Alexandre Dupont.

Cette opération permet à un administrateur de rétablir l'accès d'un utilisateur ayant perdu son mot de passe.

Le mot de passe temporaire généré doit ensuite être remplacé par l'utilisateur lors de sa prochaine connexion.

### 11. Analyse des journaux d'audit

Les journaux d'audit Microsoft Entra ID permettent de suivre les actions réalisées par les administrateurs.

Les événements observés comprennent notamment :

- Réinitialisation d'un mot de passe utilisateur ;
- Désactivation d'un compte ;

Ces journaux assurent la traçabilité des actions et facilitent l'analyse des incidents.

## Bonnes pratiques de sécurité appliquées

Durant ce projet, plusieurs bonnes pratiques de sécurité ont été mises en place afin de renforcer la protection de l'environnement Microsoft Entra ID.

### Principe du moindre privilège

Les utilisateurs ne disposent que des autorisations nécessaires à leurs missions.

Exemple :

- Amar OUNNAS : Administrateur général
- Marie Dupont : Administrateur des utilisateurs
- Utilisateurs standards : aucun privilège administratif

Cette approche limite les risques en cas de compromission d'un compte.

---

### Gestion centralisée des identités

Microsoft Entra ID permet de centraliser :

- les utilisateurs ;
- les groupes ;
- les rôles ;
- les applications ;
- les accès.

Cette centralisation facilite l'administration et améliore la visibilité sur les ressources.

---

### Contrôle des accès aux applications

Les accès aux applications d'entreprise sont attribués uniquement aux utilisateurs autorisés.

Exemple :

- Alexandre Dupont → GitHub Enterprise Cloud

Cette méthode évite de donner des accès inutiles.

---

### Traçabilité et audit

Les journaux de connexion et d'audit permettent de suivre :

- les connexions des utilisateurs ;
- les modifications réalisées ;

Ces informations sont essentielles lors d'une analyse d'incident.

## Compétences acquises

### Administration des identités

- Création et gestion des utilisateurs Microsoft Entra ID
- Création de groupes de sécurité
- Gestion des rôles administratifs
- Gestion du cycle de vie des comptes utilisateurs

### Gestion des accès

- Attribution d'accès aux applications d'entreprise
- Gestion des autorisations utilisateurs
- Application du principe du moindre privilège

### Sécurité

- Compréhension de la MFA (Multi-factor authentication)
- Gestion des méthodes d'authentification
- Analyse des journaux de connexion
- Analyse des journaux d'audit

### Cloud

- Découverte de Microsoft Entra ID
- Administration d'un environnement cloud Microsoft
- - Gestion des identités dans un environnement SaaS (Software as a Service)

## Conclusion

Ce projet m'a permis de découvrir l'administration d'un environnement Microsoft Entra ID et de mettre en pratique les concepts fondamentaux de la gestion des identités et des accès.

Les différentes étapes réalisées m'ont permis de comprendre comment une entreprise peut :

- gérer ses utilisateurs ;
- contrôler les accès aux ressources ;
- sécuriser les comptes ;
- suivre les activités grâce aux journaux ;
- appliquer des bonnes pratiques de cybersécurité.