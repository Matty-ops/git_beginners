# 🌳 TP 2 : Cycle de Vie, Commits et Branches

Ce TP vous fait pratiquer le flux de travail fondamental de Git : faire des modifications, les enregistrer (commiter) et travailler sur des lignes de développement isolées (branches).

## 🎯 Objectifs
* Exécuter le cycle de versionnement : Modifier -> `git add` -> `git commit`.
* Envoyer les modifications sur GitLab (`git push`).
* Maîtriser les commandes pour créer et basculer entre les branches (`git branch`, `git checkout`).

## 🛠️ Instructions Détaillées

### Prérequis
* Vous devez être dans le dossier `tp-git-clonage` et sur la branche `main` (ou `master`).

### Étape 1 : Le Premier Commit Local

1.  **Créer un nouveau fichier** :
    ```bash
    touch index.html
    ```
2.  **Ajouter du contenu** : Ouvrez `index.html` avec votre éditeur et ajoutez une simple structure HTML (ex: un titre `<h1>Mon Super Projet</h1>`).
3.  **Vérifier l'état** :
    ```bash
    git status
    ```
    > Le fichier doit apparaître en rouge (Non suivi / `Untracked`).

4.  **Indexer le fichier** :
    ```bash
    git add index.html
    ```
    > Il est maintenant dans la **Staging Area** (Zone d'index) et prêt à être enregistré.

5.  **Committer la modification** :
    ```bash
    git commit -m "Ajout de la page d'accueil (index.html)"
    ```

### Étape 2 : Synchronisation avec GitLab

1.  **Envoyer le commit** vers le dépôt distant (`origin`), sur la branche sur laquelle vous êtes (`main`) :
    ```bash
    git push origin main
    ```
2.  **Vérification** : Allez sur l'interface GitLab. Le fichier `index.html` doit apparaître, et votre commit doit être visible dans l'historique.

### Étape 3 : Création d'une Branche de Travail

Il est courant de travailler sur une branche séparée pour développer une fonctionnalité.

1.  **Créer une nouvelle branche** nommée `feature/ajout-css` :
    ```bash
    git branch feature/ajout-css
    ```
2.  **Basculer sur cette branche** :
    ```bash
    git checkout feature/ajout-css
    ```
    > **Raccourci :** Vous pouvez combiner les deux commandes avec : `git checkout -b feature/ajout-css`

3.  **Vérifier les branches** :
    ```bash
    git branch
    ```
    > L'astérisque (`*`) doit être devant `feature/ajout-css`.

### Étape 4 : Nouveau Commit sur la Nouvelle Branche

1.  **Créer le fichier de style** :
    ```bash
    touch style.css
    ```
2.  **Ajouter du contenu** : Mettez une règle CSS simple dans `style.css` (ex: `body { background-color: lightblue; }`).
3.  **Indexer et Commiter** :
    ```bash
    git add style.css
    git commit -m "Ajout du fichier de style initial"
    ```
    > **Rappel :** Ce commit est **UNIQUEMENT** sur la branche `feature/ajout-css` en local.

4.  **Pousser la branche entière** vers GitLab :
    ```bash
    git push -u origin feature/ajout-css
    ```
    > Le drapeau `-u` (ou `--set-upstream`) est utilisé pour lier votre branche locale à la branche distante nouvellement créée.

---
