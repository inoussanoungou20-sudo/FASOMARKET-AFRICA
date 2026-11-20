# Périmètre produit et feuille de route

## Phase 1 — Base fiable
- Publier la source applicative complète.
- Installer les dépendances à partir d'un lockfile cohérent.
- Obtenir un build reproductible et corriger les erreurs TypeScript.
- Configurer le projet Supabase et les URL de redirection.
- Corriger et tester RLS avant migration.

## Phase 2 — Commerce opérationnel
- Authentification acheteur et inscription vendeur.
- Workflow de candidature et approbation des vendeurs.
- Boutiques et gestion de catalogue persistants.
- Panier persistant et checkout serveur transactionnel.
- Calcul des prix et disponibilité côté serveur.

## Phase 3 — Paiements
- Choisir un prestataire et signer un contrat marchand.
- Configurer les moyens effectivement disponibles au Burkina Faso.
- Implémenter initiation, vérification serveur, webhooks signés, idempotence, remboursements et rapprochement.
- Effectuer des tests sandbox puis de faibles transactions réelles contrôlées.

## Phase 4 — Livraison
- Sélectionner les transporteurs et relais réellement contractualisés.
- Définir zones, prix, poids, délais, retours et responsabilités.
- Générer les expéditions et synchroniser les statuts de suivi.

## Phase 5 — Mise en production
- Tests fonctionnels, sécurité, accessibilité et mobile.
- Surveillance des erreurs et sauvegardes.
- Déploiement Preview puis Production.
- Procédure de support et de retour arrière.

## Critère de lancement
Ne pas annoncer « opérationnel » tant que les flux réels de bout en bout n'ont pas été testés et confirmés.
