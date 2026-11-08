# Health Score Builder

Outil du CS Lab : pondérez vos indicateurs de santé client, repérez les comptes à risque et obtenez le playbook recommandé.

## Fonctionnement

- Score = moyenne pondérée de 5 indicateurs (usage, adoption, NPS/CSAT, tickets, engagement du sponsor), de 0 à 100.
- Seuils réglables : rouge sous 60, vert à partir de 80 (par défaut).
- Le facteur principal est l'indicateur dont la pondération multipliée par l'écart à 100 est la plus forte.
- Les playbooks sont déterminés par règle (statut et facteur principal).
- Les données de démo sont fictives.

## Import CSV

Colonnes obligatoires : `account, arr, usage, adoption, nps, tickets, sponsor` (scores de 0 à 100).
Colonnes facultatives : `tier, score_30j`. Séparateur virgule ou point-virgule. 1 Mo et 2 000 lignes maximum.
Un modèle est téléchargeable depuis l'outil.

## Confidentialité

Tout le calcul se fait dans le navigateur. Aucune donnée n'est envoyée à un serveur, et la politique CSP du fichier `netlify.toml` bloque les connexions sortantes.

## Déploiement

Site statique, sans build : publier le dossier tel quel sur Netlify (glisser-déposer ou dépôt Git, répertoire de publication `.`).
