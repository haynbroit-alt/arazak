# OUTILS — couche d'exécution LASTO

Étape 4 de la feuille de route. Le repo devient exécutable :
une session Claude Code ici EST LASTO en mode exécutant.

## Architecture

| Brique | Fichier | Rôle |
|---|---|---|
| Mode exécution | `CLAUDE.md` | Toute session Claude Code du repo charge les règles + la mémoire |
| Rituels exécutables | `.claude/skills/` | `/matin` `/soir` `/revue` `/post-mortem` — lisent la mémoire ET l'état réel GitHub, écrivent la mémoire |
| Mémoire persistée | git | Chaque màj mémoire = commit + PR draft → historique complet, rollback possible |
| Site | Cloudflare | Mémoire lisible partout, déploiement auto à chaque merge |

## Boucle complète

"matin" (Projet Claude ou Claude Code) → travail → "soir" →
JOURNAL/CONTEXTE mis à jour par commit → site à jour → le
lendemain, "matin" repart de l'état réel. Zéro copier-coller.

## Automatisations planifiées (Routines)

Candidates — activées une par une, sur validation explicite
(LASTO.md, Amélioration continue) :

| Routine | Cadence | Action |
|---|---|---|
| Brief matin | Jours ouvrés 7h | Session fraîche : exécute /matin, résultat par notification |
| Rappel revue | Vendredi 17h | Exécute /revue, PR draft avec l'audit |
| Sentinelle ressources | Quotidien | Vérifie seuils CONTEXTE (abonnements, budget) → alerte si critique |

État : [PROPOSÉ] — aucune active. Dire "active [nom]" pour lancer.

## n8n — moteur d'automatisation

| Brique | Mécanisme | État |
|---|---|---|
| n8n-mcp (serveur MCP) | `.mcp.json` du repo → chargé auto par toute session Claude Code ici (`npx n8n-mcp`) | [FAIT] mode docs (531 nœuds, validation, templates) sans instance |
| Mode gestion d'instance | Variables d'env `N8N_API_URL` + `N8N_API_KEY` | [ACTION NOM] nécessite une instance n8n |
| n8n-skills (14 skills : expressions, patterns, validation, code JS/Python, agents IA…) | Dans Claude Code : `/plugin install czlonkowski/n8n-skills` | [ACTION NOM] 1 commande |

Règles de sécurité n8n (source : doc n8n-mcp) :
- Jamais d'édition directe de workflows de production par l'IA —
  copie, test en dev, backup exporté.
- Si instance connectée : clé API en lecture seule d'abord ;
  écritures bloquables via `DISABLED_TOOLS`.

## Sécurité d'exécution
- Écriture mémoire : jamais de push direct sur main — PR systématique.
- Actions externes (email, event, merge) : confirmation explicite.
- Une Routine n'exécute que son rituel — pas d'initiative hors périmètre.
