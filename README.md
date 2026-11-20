# FASOMARKET AFRICA

Marketplace panafricaine orientée commerce local, avec une première expérience centrée sur le Burkina Faso.

> **État du dépôt au 20 novembre 2026 : initialisation documentaire uniquement.** Le dépôt GitHub était vide. Les archives du projet ont été retrouvées dans les fichiers de travail, mais le code source complet, ses médias et son verrou de dépendances ne sont pas encore publiés dans ce dépôt. L'interface actuelle est une maquette front-end : les comptes, commandes, paiements et livraisons ne doivent pas être présentés comme opérationnels.

## Vision
Permettre aux acheteurs de découvrir des produits locaux et régionaux, et aux vendeurs de développer leurs boutiques au Burkina Faso puis dans les marchés africains.

## Fonctionnalités présentes dans la version source retrouvée
- Interface React + TypeScript construite avec Vite.
- Catalogue de démonstration, catégories et recherche.
- Mise en avant des produits et des vendeurs.
- Sélecteur de pays et de devise, avec données de localisation panafricaines.
- Panier côté interface et aperçu rapide des produits.
- Composants PWA et indicateur de connexion.
- Documentation de cadrage paiements, devises, livraison et sécurité Supabase.

## État fonctionnel — à ne pas confondre avec une mise en production
| Domaine | État vérifié dans la source |
|---|---|
| Catalogue / recherche | Démonstration front-end |
| Panier | État local de l'interface, non persisté |
| Authentification | Formulaire de démonstration, aucun appel serveur |
| Boutiques vendeurs | Parcours à finaliser |
| Commandes | Pas de création transactionnelle |
| Paiements Mobile Money / carte | Passerelle non connectée |
| Livraison / suivi | Tarifs et transporteurs non contractualisés |
| Supabase | Schéma SQL initial présent, non appliqué et à corriger avant migration |
| Déploiement Vercel | Configuration préparatoire présente dans l'archive, déploiement non réalisé |

## Stack technique de la source retrouvée
- React 19, TypeScript, Vite 8
- Tailwind CSS 4
- Supabase JS (dépendance prévue)
- vite-plugin-pwa
- Lucide React

## Démarrage local
Prérequis : Node.js 22 ou version LTS compatible et npm.

```bash
npm install
cp .env.example .env.local
npm run dev
```

Variables publiques attendues :
- `VITE_SUPABASE_URL`
- `VITE_SUPABASE_ANON_KEY` (ou clé publishable)

Ne jamais placer une clé `service_role` ou une clé secrète dans une variable `VITE_*`.

## Scripts prévus
- `npm run dev` : serveur de développement Vite
- `npm run build` : compilation de production
- `npm run preview` : aperçu du build
- `npm run lint` : vérification TypeScript

## Déploiement Vercel
Le projet est préparé pour Vercel avec Vite :
- Build command : `npm run build`
- Output directory : `dist`
- Install command : `npm install`

Le déploiement doit attendre la publication du code source complet, un build réussi et la configuration des variables d'environnement dans Vercel.

## Documentation du dépôt
- [Architecture et modules](docs/ARCHITECTURE.md)
- [Sécurité et données](docs/SECURITY.md)
- [Périmètre fonctionnel et feuille de route](docs/PRODUCT-ROADMAP.md)
- [Liste de contrôle avant lancement](docs/RELEASE-CHECKLIST.md)
- [Configuration paiements, devises et livraison](CONFIGURATION-PAIEMENTS-DEVISES-LIVRAISON.md)
- [Connexion Supabase](SUPABASE-CONNEXION.md)
- [Revue sécurité avant migration](PRE-MIGRATION-SECURITY-REVIEW.md)
- [Déploiement Vercel](DEPLOIEMENT-VERCEL.md)

## Principe de lancement
Aucun paiement ne doit être simulé ou marqué comme réussi sans confirmation du prestataire. Aucune commande ne doit être confirmée sans validation serveur des prix, du stock et du statut du paiement. Les transporteurs, zones, délais et frais doivent être configurés et testés avant ouverture commerciale.
