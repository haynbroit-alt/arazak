# Déploiement LASTO (15 min)

1. Créer un Projet Claude "LASTO"
2. Coller `LASTO.md` (v2.0) en instructions projet
3. Ajouter en connaissance projet : `CONTEXTE.md` (rempli),
   `DECISIONS.md`, `JOURNAL.md`, `INTEGRATIONS.md`
4. Première session : "matin"

## Prérequis avant mise en service
- [ ] Remplacer [NOM]
- [ ] Objectif principal défini
- [ ] Projets actifs listés
- [ ] Seuils ressources définis (budget, temps)

## Feuille de route (après le prompt — le prompt n'évolue plus)

| Étape | Valeur | Effort |
|---|---|---|
| 1. CONTEXTE.md vivant (màj chaque session) | Haute | Nul |
| 2. DECISIONS.md + JOURNAL.md alimentés | Haute | Faible |
| 3. Intégrations : email, calendrier, GitHub — voir `INTEGRATIONS.md` (module livré, OAuth côté [NOM]) | Haute | Moyen |
| 4. Outils d'exécution — voir `OUTILS.md` (CLAUDE.md + skills livrés, Routines sur validation) | Très haute | Moyen |

Principe : la valeur vient désormais de l'architecture autour du
prompt (mémoire, journaux, intégrations, outils), pas de règles
supplémentaires.
