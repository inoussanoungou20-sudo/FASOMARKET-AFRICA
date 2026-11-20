# Sécurité et données

## Règles obligatoires
- Ne jamais exposer `service_role`, clés secrètes, mots de passe de base de données ou tokens privés dans le navigateur ou dans Git.
- Les variables `VITE_*` sont publiques par conception.
- Activer RLS sur chaque table exposée et écrire des policies fondées sur l'identité et la propriété des lignes.
- Les rôles vendeur et administrateur ne doivent jamais être déterminés depuis des métadonnées modifiables par l'utilisateur.
- Vérifier les webhooks avec la signature officielle du prestataire et empêcher le rejeu.
- Recalculer côté serveur les prix, remises, frais, taxes, commissions et stocks.
- Journaliser les transitions de commande et paiement sans stocker de données de carte.

## Revue SQL préalable
Le SQL initial présent dans l'archive est une base de travail, pas une migration prête à lancer. Les points signalés dans `PRE-MIGRATION-SECURITY-REVIEW.md` doivent être résolus avant application : auto-attribution de rôle, gestion d'approbation des boutiques, lecture des lignes de commande, contraintes pays/devise et privilèges Data API.

## Données sensibles
Ne pas demander à l'utilisateur de publier des secrets dans une issue, un commit, un fichier source ou une conversation publique. Utiliser les variables d'environnement protégées du fournisseur d'hébergement.
