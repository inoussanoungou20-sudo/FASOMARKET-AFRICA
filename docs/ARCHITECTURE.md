# Architecture technique

## Source applicative retrouvée
La source locale récupérée dans l'archive de travail est organisée en :
- `src/App.tsx` : composition principale et état d'interface.
- `src/components/` : sections d'accueil, navigation, modales, panier et composants PWA.
- `src/config/localization.ts` : pays, devises et métadonnées locales.
- `src/data/catalog.ts` : catalogue de démonstration.
- `src/types/marketplace.ts` : types métier.
- `src/modules/architecture/roadmap.ts` : contrats et feuille de route métier.
- `supabase/migrations/` : SQL initial à auditer et corriger avant usage.

## Flux front-end observé
Le composant racine conserve le pays, la devise, les filtres, la recherche, le panier et l'ouverture des modales dans l'état React. Le panier n'est pas persisté dans la base de données. La fenêtre de compte affiche un message de démonstration et ne réalise pas d'appel d'authentification.

## Architecture cible
1. Client React : catalogue, panier, espace acheteur et vendeur.
2. Supabase Auth : identité et sessions.
3. PostgreSQL + RLS : profils, candidatures vendeurs, boutiques, produits, commandes et lignes de commande.
4. Fonctions serveur : création atomique de commande, calcul du total, réservation du stock et initiation de paiement.
5. Webhooks prestataires : confirmation vérifiée, remboursement et rapprochement.
6. Logistique : tarifs versionnés par zone/poids, transporteurs, événements de suivi.

## Règle de confiance
Le navigateur ne doit jamais décider qu'un paiement est payé, qu'un vendeur est approuvé, ni qu'une commande est validée. Ces décisions appartiennent au serveur après vérification des droits et des réponses signées des prestataires.
