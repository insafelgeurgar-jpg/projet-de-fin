# Planification du Projet — Gestion des Paiements

**Étudiant :** insafelguergar  
**Encadrante :** abdlatif soklabi
**Établissement :** Solicode  
**Année académique :** 2026–2027  

---

## 📅 Tableau de planification

| Phase | Tâches | Durée | Semaine |
|-------|--------|-------|---------|
| **Phase 1** — Analyse & Conception | Analyse des besoins, architecture MVC, schéma BDD, maquettes | 1 semaine | S1 |
| **Phase 2** — Développement Back-end | XAMPP, structure projet, authentification JWT, API REST, Stripe | 2 semaines | S2–S3 |
| **Phase 3** — Développement Front-end | Pricing, login, register, checkout, dashboard user & admin | 2 semaines | S3–S4 |
| **Phase 4** — Tests & Corrections | Tests fonctionnels, débogage, optimisation | 1 semaine | S5 |
| **Phase 5** — Documentation | Rapport, captures d'écran, finalisation | 1 semaine | S6 |

---

## 🗓️ Détail par semaine

### Semaine 1 — Analyse & Conception
- [ ] Analyse des besoins fonctionnels et non fonctionnels
- [ ] Définition de l'architecture MVC
- [ ] Conception du schéma de base de données (11 tables)
- [ ] Réalisation des maquettes des interfaces
- [ ] Choix des technologies (PHP, MySQL, JWT, Stripe)

### Semaine 2 — Développement Back-end (partie 1)
- [ ] Installation et configuration de XAMPP
- [ ] Mise en place de la structure du projet
- [ ] Configuration du fichier `.env`
- [ ] Implémentation de l'autoloader PSR-4
- [ ] Développement du Router et des routes API
- [ ] Développement de l'authentification JWT (register, login, logout, refresh)

### Semaine 3 — Développement Back-end (partie 2)
- [ ] Intégration de la passerelle Stripe
- [ ] Développement du CheckoutController
- [ ] Système de coupons de réduction
- [ ] Génération automatique des factures
- [ ] Développement de l'AdminController
- [ ] Système de remboursements

### Semaine 4 — Développement Front-end
- [ ] Page de tarification (pricing.php)
- [ ] Page de connexion / inscription
- [ ] Page de paiement (checkout.php)
- [ ] Page de succès / échec paiement
- [ ] Tableau de bord utilisateur
- [ ] Tableau de bord administrateur complet

### Semaine 5 — Tests & Corrections
- [ ] Tests fonctionnels de toutes les fonctionnalités
- [ ] Correction des bugs (autoloader, .env, rate limiting, paths)
- [ ] Tests de sécurité (JWT, bcrypt, rate limiting)
- [ ] Tests d'interface (responsive, compatibilité navigateurs)
- [ ] Optimisation des requêtes SQL

### Semaine 6 — Documentation
- [ ] Rédaction du rapport de projet
- [ ] Captures d'écran des interfaces
- [ ] Rédaction du guide d'utilisation
- [ ] Finalisation et relecture

---

## 🎯 Fonctionnalités réalisées

| Fonctionnalité | Statut |
|----------------|--------|
| Authentification JWT | ✅ Réalisé |
| Page de tarification dynamique | ✅ Réalisé |
| Paiement Stripe | ✅ Réalisé |
| Système de coupons | ✅ Réalisé |
| Génération de factures | ✅ Réalisé |
| Dashboard utilisateur | ✅ Réalisé |
| Dashboard administrateur | ✅ Réalisé |
| Remboursements | ✅ Réalisé |
| Gestion des plans | ✅ Réalisé |
| Logs de paiement | ✅ Réalisé |
| PayPal / Paymob / CMI | ⚠️ Coming Soon |

---

## 🔧 Technologies utilisées

| Technologie | Rôle |
|-------------|------|
| PHP 8.2 | Back-end, logique métier |
| MySQL 8 | Base de données |
| HTML / CSS | Structure et design |
| JavaScript | Interactions front-end |
| JWT | Authentification stateless |
| Stripe API | Passerelle de paiement |
| XAMPP | Serveur local de développement |
| Visual Studio Code | Éditeur de code |

---

*Rapport complet disponible dans : `Rapport_Gestion_des_Paiements.docx`*