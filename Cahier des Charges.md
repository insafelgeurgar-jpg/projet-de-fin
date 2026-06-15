Cahier des Charges — PaymentModule
Plateforme de Gestion des Paiements

1. Présentation du projet
Le projet PaymentModule est une plateforme web de gestion des paiements développée en PHP natif selon l'architecture MVC. Elle permet aux utilisateurs de souscrire à des plans d'abonnement et d'effectuer des paiements sécurisés via Stripe et PayPal, tandis que les administrateurs disposent d'un tableau de bord complet pour superviser l'activité financière.

2. Objectifs du projet
L'objectif principal est de concevoir et développer une application web sécurisée permettant la gestion complète du cycle de paiement, depuis la sélection d'un plan jusqu'à la génération automatique des factures. Les objectifs spécifiques sont les suivants :

Mettre en place un système d'authentification sécurisé basé sur JWT
Intégrer deux passerelles de paiement : Stripe et PayPal
Gérer les abonnements, les transactions et les factures
Offrir une interface d'administration complète
Assurer la sécurité des données et des transactions


3. Périmètre fonctionnel
3.1 Fonctionnalités côté utilisateur
Authentification

L'utilisateur peut s'inscrire, se connecter et se déconnecter. L'authentification est sécurisée par token JWT avec gestion du refresh token.
Gestion des plans

L'utilisateur peut consulter les plans d'abonnement disponibles (Starter, Professional, Enterprise), comparer les fonctionnalités et choisir un cycle de facturation mensuel ou annuel.
Paiement

L'utilisateur peut effectuer un paiement via carte bancaire (Stripe Elements) ou via PayPal (redirection vers sandbox PayPal). Il peut également appliquer un code de réduction avant validation.
Espace personnel

L'utilisateur peut consulter l'historique de ses transactions, ses abonnements actifs, ses factures téléchargeables et gérer son profil.
3.2 Fonctionnalités côté administrateur
Tableau de bord

L'administrateur dispose d'un tableau de bord affichant les statistiques globales : nombre d'utilisateurs, revenus totaux, transactions récentes, abonnements actifs.
Gestion des utilisateurs

L'administrateur peut consulter la liste des utilisateurs, modifier leurs rôles et suspendre des comptes.
Gestion des plans et coupons

L'administrateur peut créer, modifier et supprimer des plans d'abonnement ainsi que des codes de réduction.
Gestion des transactions

L'administrateur peut consulter toutes les transactions, filtrer par statut et déclencher des remboursements.

4. Exigences techniques
4.1 Architecture
L'application suit le patron de conception MVC (Modèle - Vue - Contrôleur) développé en PHP natif sans framework. L'accès à la base de données est sécurisé via PDO avec requêtes préparées.
4.2 Technologies utilisées
ComposantTechnologieLangage backendPHP 8.x natifBase de donnéesMySQLAuthentificationJWT (JSON Web Token)Paiement 1Stripe (Elements + Webhooks)Paiement 2PayPal (Orders v2 API)FrontendHTML5, CSS3, JavaScriptServeur localXAMPP (Apache)
4.3 Sécurité

Mots de passe hashés avec bcrypt
Authentification par JWT avec expiration
Protection contre les injections SQL via PDO
Validation et sanitisation de toutes les entrées utilisateur
Vérification des webhooks Stripe par signature
HTTPS obligatoire en production


5. Base de données
La base de données MySQL comprend 6 tables principales :

users : gestion des comptes utilisateurs et administrateurs
plans : plans d'abonnement avec tarification mensuelle et annuelle
subscriptions : abonnements actifs des utilisateurs
transactions : historique complet des paiements
invoices : factures générées automatiquement
coupons : codes de réduction avec gestion des limites d'utilisation
refunds : gestion des remboursements


6. Contraintes du projet
6.1 Contraintes techniques

Développement en PHP natif uniquement, sans framework
Compatibilité avec les navigateurs modernes (Chrome, Firefox, Edge)
Interface responsive adaptée aux mobiles et tablettes
Environnement de développement local sous XAMPP

6.2 Contraintes de sécurité

Aucune donnée bancaire stockée en base de données
Toutes les transactions transitent par les APIs officielles Stripe et PayPal
Conformité PCI-DSS assurée par délégation aux prestataires de paiement


7. Livrables

Code source complet de l'application
Base de données MySQL avec données de test
Documentation technique (rapport PFE)
Diagrammes UML (cas d'utilisation, classes, MCD)
Manuel d'installation et de configuration


8. Planning prévisionnel
PhaseDescriptionDuréeAnalyseÉtude des besoins et rédaction du cahier des charges1 semaineConceptionArchitecture MVC, MCD, diagrammes UML1 semaineDéveloppementImplémentation des fonctionnalités3 semainesTestsTests fonctionnels et d'intégration1 semaineDéploiementConfiguration et mise en production1 semaine

9. Acteurs du système
Utilisateur : toute personne souhaitant souscrire à un plan d'abonnement et effectuer un paiement en ligne.
Administrateur : responsable de la plateforme, disposant d'un accès complet à la gestion des utilisateurs, plans, transactions et statistiques.
Stripe / PayPal : prestataires externes de paiement intervenant lors du traitement des transactions et de la validation des webhooks.
