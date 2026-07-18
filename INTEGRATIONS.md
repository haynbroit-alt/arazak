# INTÉGRATIONS — module LASTO (connaissance projet)

Étend LASTO sans toucher au prompt (v2.0 gelé). À charger en
connaissance projet aux côtés de CONTEXTE.md.

## Architecture

| Surface | Mécanisme | Intégrations |
|---|---|---|
| Projet Claude (claude.ai) | Connecteurs (Paramètres → Connecteurs) | Gmail, Google Calendar, GitHub |
| Claude Code / Cowork | Serveurs MCP | GitHub (natif), autres via registre MCP |

Une seule règle : les intégrations alimentent les rituels et
l'anticipation — elles n'ajoutent jamais de bruit hors rituel.

## Règles d'usage par LASTO

### Email (Gmail)
- "matin" → scanner la boîte : urgent / attend une réponse de [NOM] /
  engagement pris par écrit. Max 5 items, le reste ignoré.
- Jamais d'envoi sans "CONFIRMER : envoyer ?" (règle sécurité §4).
- Détection : abonnement facturé repéré dans un email → vérifier
  section Ressources de CONTEXTE.md, alerter si absent.

### Calendrier (Google Calendar)
- "matin" → charge du jour : réunions, temps de focus restant,
  conflit ou surcharge → "⚡ Anticipé".
- "soir" → préparer demain : 1er rendez-vous, préparation requise.
- Proposition de créneau : toujours vérifier la disponibilité réelle
  avant de proposer ([FAIT] vs [HYPOTHÈSE]).

### GitHub
- "matin" → PRs en attente de review, issues assignées, CI rouge.
- Projet actif dans CONTEXTE.md ↔ repo : lier l'état réel
  (dernier commit, PRs ouvertes) au champ "état / next action".
- Exécution : Claude Code peut pousser, ouvrir des PRs, surveiller
  la CI — déléguer l'opérationnel, LASTO garde la vue d'ensemble.

## Confidentialité (étend §4)
- Lecture seule par défaut ; toute écriture (email, event, push)
  → confirmation explicite.
- Aucun contenu d'email/calendrier recopié dans CONTEXTE.md sauf
  décision ou engagement durable — et alors résumé, pas verbatim.

## Mise en place (action [NOM], ~10 min)

1. claude.ai → Paramètres → Connecteurs → connecter :
   - Gmail (lecture ; activer l'envoi seulement si confiance établie)
   - Google Calendar
   - GitHub (org haynbroit-alt)
2. Dans le Projet LASTO : activer les 3 connecteurs pour le projet.
3. Ajouter ce fichier en connaissance projet.
4. Test : lancer "matin" → la réponse doit citer calendrier + boîte
   mail + GitHub réels. Une source inaccessible doit être signalée
   [FAIT]/[HYPOTHÈSE], jamais inventée.

## État

- [FAIT] Module d'intégration (ce fichier) + règles d'usage
- [ACTION NOM] Connexion OAuth des 3 comptes (étape 1-2 ci-dessus)
- [SUIVANT] Étape 4 feuille de route : outils d'exécution
  (automatisations Claude Code, Routines planifiées)
