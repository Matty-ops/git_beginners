# 🤝 TP 3 : Flux de Collaboration et Synchronisation

Ce TP simule l'étape de revue de code et de fusion (Merge) d'une fonctionnalité, puis la synchronisation du travail collaboratif.

## 🎯 Objectifs
* Créer une **Merge Request (MR)** sur GitLab.
* Récupérer des changements distants et les appliquer localement (`git pull`).
* Supprimer des branches inutiles.
* Utiliser le fichier `.gitignore` pour exclure des éléments du suivi Git.

## 🛠️ Instructions Détaillées

### Prérequis
* La branche `feature/ajout-css` a été poussée sur GitLab.

### Étape 1 : Fusion via GitLab (Merge Request)

1.  **Créer une Merge Request (MR)** : Sur l'interface GitLab, une notification doit apparaître vous proposant de créer une MR.
    * Créez la MR de la source `feature/ajout-css` vers la cible `main`.
2.  **Simuler la Revue et Fusionner** :
    * Remplissez le titre et la description.
    * **Validez la fusion** (bouton "Merge").
    * **Cochez l'option** pour supprimer la branche source sur GitLab après fusion (pour le nettoyage distant).
    > **Résultat :** Le contenu de `feature/ajout-css` est maintenant sur la branche `main` de GitLab.

### Étape 2 : Synchronisation Locale

Votre branche locale `main` n'est pas encore à jour.

1.  **Basculer sur la branche principale** :
    ```bash
    git checkout main
    ```
2.  **Récupérer et fusionner les modifications** de GitLab :
    ```bash
    git pull origin main
    ```
    > **Note :** Le `pull` est un raccourci pour `git fetch` suivi de `git merge`.

3.  **Vérification** : Le fichier `style.css` doit maintenant apparaître dans votre répertoire local, sur la branche `main`.

### Étape 3 : Nettoyage des Branches Locales

Comme la fonctionnalité a été fusionnée, la branche de travail n'est plus nécessaire.

1.  **Supprimer la branche locale** :
    ```bash
    git branch -d feature/ajout-css
    ```
    > **Si la suppression échoue :** C'est que Git pense que le merge n'est pas complet (même si vous l'avez fait manuellement). Utilisez le drapeau `-D` (majuscule) pour forcer la suppression : `git branch -D feature/ajout-css`.

### Étape 4 : Ignorer des Fichiers avec `.gitignore`

Il y a des fichiers que vous ne voulez pas versionner (logs, fichiers de compilation, dépendances, etc.).

1.  **Créer un fichier à ignorer** (ex: un fichier de log) :
    ```bash
    touch error.log
    ```
2.  **Vérifier son état** : `git status` doit l'afficher comme non suivi.
3.  **Créer le fichier d'exclusion** :
    ```bash
    touch .gitignore
    ```
4.  **Ajouter la règle d'exclusion** : Ouvrez `.gitignore` et ajoutez le nom du fichier à exclure :
    ```
    # Fichiers de log à ignorer
    error.log
    ```
5.  **Vérifier l'état à nouveau** : `git status` ne doit plus afficher `error.log`.
6.  **Commiter et Pousser le `.gitignore`** (car il doit être partagé avec les autres développeurs) :
    ```bash
    git add .gitignore
    git commit -m "Configuration: Ajout du fichier .gitignore"
    git push origin main
    ```

---
