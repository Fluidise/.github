# ADR: 2026-10-25 - Modernisation de la Gouvernance d'Organisation et de l'Outillage DX

- **Date :** 2026-10-25
- **Statut :** Accepté
- **Palier d'intervention :** Tier 3 : Remplacement Moderne / Standard Fluidise
- **Pilier concerné :** CI/CD & DevOps, Transverse : Gouvernance & Hygiène
- **Auteur(s) :** Acrazie / Fluidise Team

---

## 1. Contexte & Problématique

Le dépôt spécial `Fluidise/.github` abrite le profil public de l'organisation Fluidise ainsi que les configurations d'organisation par défaut pour l'ensemble des dépôts de l'écosystème.

À l'état initial, le dépôt ne disposait d'aucune brique de gouvernance standard (`SECURITY.md`, `CONTRIBUTING.md`, `LICENSE`), d'aucun template d'organisation (Issue Forms modernes, template de PR), et d'aucun workflow d'intégration continue dans `.github/workflows/`. De plus, bien que le projet phare de Fluidise soit `fluidise-clint` (validateur autonome de messages de commit au format Conventional Commits avec zéro dépendance d'exécution), le dépôt d'organisation n'appliquait pas encore ce propre standard dans sa CI.

---

## 2. Décision & Changement Opéré

Nous avons décidé de déployer la gouvernance d'organisation complète et la suite DX native Fluidise au palier **Tier 3** :

1. **Gouvernance d'organisation :**
   - Formalisation de `LICENSE` (Licence MIT conforme aux spécifications publiques de Fluidise).
   - Déploiement de `SECURITY.md` (politique de divulgation responsable, SLA de réponse, signalement via GitHub Security Advisories).
   - Déploiement de `CONTRIBUTING.md` (règles de contribution axées sur les 4 invariants Fluidise : Agent-First, Zero Runtime Dependencies, Strict Safety, Standalone Modularity).
   - Formalisation de la politique Git dans `docs/git-workflow.md`.

2. **Hygiène & Outillage :**
   - Mise à niveau de `.gitignore` (isolation des worktrees et artefacts locaux).
   - Normalisation du formatage via `.editorconfig`.

3. **Templates d'Organisation & CI/CD :**
   - Déploiement de GitHub Issue Forms modernes en YAML (`bug_report.yml`, `feature_request.yml`) et configuration d'issues (`config.yml`).
   - Déploiement du template de Pull Request (`pull_request_template.md`).
   - Mise en place d'un workflow CI dans `.github/workflows/ci.yml` utilisant `actions/checkout@v7`, intégrant la validation des commits Conventional Commits via `fluidise-clint` et la vérification des liens de documentation via l'action ultra-rapide `lycheeverse/lychee-action@v2`.

### Alternatives Évaluées :
- **Option 1 (Tier 1 : Minimaliste) :** Se limiter à `.gitignore` et `.editorconfig`. Écartée car elle laisse le dépôt d'organisation sans gouvernance ni CI, affaiblissant l'image de la vitrine Fluidise.
- **Option 2 (Tier 2 : Gouvernance classique) :** Ajouter des fichiers Markdown de gouvernance basiques sans templates d'organisation ni validation automatisée. Écartée car elle ne tire pas parti du propre outil de l'organisation (`fluidise-clint`) ni des Issue Forms YAML modernes.
- **Option 3 (Tier 3 : Standard Fluidise & Excellence DX) :** Retenue car elle dote toute l'organisation de standards de gouvernance partagés, automatise le contrôle qualité sans ajouter aucune dépendance runtime lourde (Node, npm), et illustre directement les capacités de la suite Fluidise.

---

## 3. Conséquences & Bénéfices

### Bénéfices (Conséquences Positives) :
- **Héritage automatique :** Tous les dépôts de l'organisation Fluidise héritent automatiquement des templates d'issues, de PR et de la politique de sécurité sans duplication de configuration.
- **Zéro dépendance d'exécution :** Respect strict de l'invariant *Zero Runtime Dependencies* — aucune installation de `package.json`, `node_modules` ou environnement Python lourd pour maintenir un dépôt de documentation.
- **Validation continue intégrée :** Détection précoce des liens cassés (`lychee`) et garantie de commits conformes (`fluidise-clint`).
- **Isolation Git exemplaire :** Travail mené sous git worktree dédié (`modernize/governance-dx`), préservant la branche `main` et les assets non suivis.

### Compromis & Points de Vigilance (Conséquences Négatives) :
- Nécessite le respect strict de la syntaxe Conventional Commits sur les PRs (attendu et souhaité pour le projet).

---

## 4. Validation & Conformité

- **Outils utilisés :** `git worktree`, `actions/checkout@v7`, `lycheeverse/lychee-action@v2`, `fluidise-clint`.
- **Résultats des vérifications :**
  - Git Isolation : ✅ Worktree dédié `.worktrees/modernize-governance-dx`
  - Hygiène : ✅ `.gitignore` et `.editorconfig` configurés
  - Gouvernance : ✅ `LICENSE`, `SECURITY.md`, `CONTRIBUTING.md`, `git-workflow.md` conformes
  - CI : ✅ Workflow `.github/workflows/ci.yml` configuré avec `actions/checkout@v7`
