# CONTEXTE — màj 2026-07-18

## Objectif principal
Lancer arazak.

## Projets actifs
- Système LASTO : livré (v3.0 + mémoire + site + skills) /
  next action : l'utiliser au quotidien ("matin", "soir") /
  blocage : aucun
- Lancement arazak : à cadrer / next action : définir ce que
  "lancé" veut dire (produit ? site public ? premiers
  utilisateurs ?) + 3 premières étapes / blocage : périmètre flou
  [HYPOTHÈSE — à préciser par l'utilisateur]

## Ressources
- Temps disponible / semaine : [à compléter]
- Budget mensuel : [à compléter]
- Abonnements : Cloudflare Workers (site arazak — plan actuel à
  confirmer), Claude [ESTIMATION]
- Seuils critiques : [à compléter]

## Modèle de travail
- Heures productives : [à compléter]
- Style décision : rapide — valide et merge en quelques minutes,
  délègue l'exécution, tranche par "carte blanche" [FAIT — observé
  en session]
- Outils : Claude (Projet LASTO), Claude Code, GitHub
  (haynbroit-alt/arazak), Cloudflare Workers [FAIT]

## Ne pas répéter
- Brancher un déploiement sur un repo sans config de build →
  deploy rouge (résolu par wrangler.jsonc + assets, 2026-07-18)

## Leçons & règles apprises
- La valeur vient de l'architecture autour du prompt (mémoire,
  intégrations, outils), pas de l'allongement des règles
  (adopté en v2.0→v3.0)

## Automatisations validées
- Déploiement Cloudflare auto à chaque merge sur main [FAIT]
- Routines planifiées (brief matin, revue, sentinelle ressources) :
  [PROPOSÉ — aucune activée]
