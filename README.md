# Projet Final — Méthodologies de l’IA Générative (2026-2027)
**Université Paris Dauphine - PSL**  
**Master SIREN (Parcours IREN / MTM)**

Bienvenue dans le dépôt de votre groupe.

Ce dépôt sert à centraliser votre livrable final : code, documents, prompts, workflows et éléments de présentation.

---

## Objectif du dépôt

Ce dépôt doit permettre de :
1. **Centraliser** votre travail dans un espace unique.
2. **Assurer la reproductibilité** (exécution du code, relecture des analyses, compréhension de la démarche).
3. **Valider la partie “Partage du Code/Outil”** de l’évaluation finale.

---

## Structure conseillée

Merci de respecter autant que possible la structure suivante :

```text
/ (Racine du dépôt)
│
├── README.md              <-- Présentation rapide du projet
├── Rapport/               <-- Rapport écrit + Journal de bord IA
├── Code/                  <-- Scripts, notebooks, workflows (n8n/Make), etc.
├── Data/                  <-- Jeux de données (si partageables)
└── Presentation/          <-- Supports de soutenance (PDF)
```

---

## Contenu attendu

### 1) README.md (ce fichier)
Présentez en quelques lignes :
- Le sujet et le problème traité
- L’approche choisie
- Les principaux résultats
- Comment lancer/reproduire votre travail

### 2) Rapport/
- Rapport final (PDF)
- Journal de bord IA (prompts, itérations, limites, arbitrages)

### 3) Code/
- Scripts Python/R, notebooks, exports de workflows no-code, etc.
- Un minimum d’instructions pour exécuter les éléments fournis

### 4) Data/
- Données non confidentielles
- Si données trop lourdes : fournir un lien (HuggingFace, Dropbox, etc.) + courte explication

### 5) Presentation/
- Slides de soutenance (PDF)

---

## Recommandations pratiques

- Faites des commits réguliers avec des messages explicites.
- Ajoutez un `.gitignore` adapté à votre stack.
- Évitez de versionner des fichiers volumineux non nécessaires.
- Vérifiez qu’un tiers peut comprendre et relancer votre projet sans explication orale.

---

## LaTeX : rédiger votre rapport

Deux options pour écrire votre rapport en LaTeX.

### Option 1 — Overleaf (le plus simple pour démarrer)

[Overleaf](https://www.overleaf.com) est un éditeur LaTeX **en ligne** :
- rien à installer, la compilation et l’aperçu PDF se font dans le navigateur ;
- édition **collaborative en temps réel** (comme un Google Docs) et historique des modifications ;
- nombreux modèles prêts à l’emploi (rapports, articles, présentations Beamer).

Un compte gratuit suffit pour ce projet. Un petit tutoriel Overleaf sera présenté en cours.  
Pensez à exporter le PDF final (et éventuellement les sources `.zip`) dans le dossier `Rapport/` du dépôt.

### Option 2 — En local avec VS Code

**1. Installer une distribution LaTeX**

| Système | Distribution | Remarques |
|---|---|---|
| **Windows** | [MiKTeX](https://miktex.org/download) | Lors de l’installation, choisir *Install missing packages on-the-fly : Yes*. Installer aussi [Strawberry Perl](https://strawberryperl.com/) (nécessaire à `latexmk`). |
| **Windows** (alternative) | [TeX Live](https://tug.org/texlive/windows.html) | Plus lourd, mais complet (Perl inclus). |
| **macOS** | [MacTeX](https://www.tug.org/mactex/) | Complet (~6 Go). Avec Homebrew : `brew install --cask mactex-no-gui` |

Redémarrez ensuite VS Code (voire l’ordinateur) puis vérifiez dans un terminal :

```bash
pdflatex --version
latexmk --version
```

**2. Installer l’extension VS Code**

Dans l’onglet *Extensions* (`Ctrl+Shift+X` / `Cmd+Shift+X`), installez **LaTeX Workshop** (James Yu).

**3. Compiler**

- Ouvrez votre fichier `.tex` : la compilation se lance automatiquement à chaque sauvegarde.
- Compilation manuelle : `Ctrl+Alt+B` (Windows) / `Cmd+Option+B` (macOS).
- Aperçu du PDF : `Ctrl+Alt+V` (Windows) / `Cmd+Option+V` (macOS).

Astuce : ajoutez les fichiers temporaires au `.gitignore` (`*.aux`, `*.log`, `*.out`, `*.toc`, `*.synctex.gz`, `*.fls`, `*.fdb_latexmk`).

---

## LLM, agent et MCP : quelle différence ?

- **LLM (Large Language Model)** : un modèle qui reçoit du texte et génère du texte (GPT, Claude, Mistral, Llama…). Il ne fait que répondre : il n’agit pas sur le monde et ne connaît que ce qu’on lui met dans le contexte.
- **Agent** : un LLM placé dans une **boucle** et équipé d’**outils** (recherche web, exécution de code, lecture/écriture de fichiers, API…). Il planifie, appelle un outil, observe le résultat et recommence jusqu’à atteindre l’objectif. Exemples : Claude Code, Cursor, un nœud « AI Agent » dans n8n.
- **MCP (Model Context Protocol)** : un standard ouvert pour **brancher des outils et des sources de données** sur un agent, une sorte de « prise USB-C de l’IA ». Un *serveur MCP* expose des outils (GitHub, Google Drive, Notion, une base de données…) et n’importe quel client compatible (Claude Desktop, Claude Code, VS Code, Cursor…) peut les utiliser sans développement spécifique.

**Intérêt du MCP** : on écrit (ou on installe) une intégration une seule fois et on la réutilise avec n’importe quel agent ; on contrôle précisément à quoi l’agent a accès.

---

## Checklist avant rendu

- [ ] Le dépôt contient toutes les pièces demandées.
- [ ] L’arborescence est claire et cohérente.
- [ ] Les étapes de reproduction sont décrites.
- [ ] Les liens externes (données, modèles, ressources) fonctionnent.
- [ ] Le support de présentation est bien inclus.

Bon travail !
