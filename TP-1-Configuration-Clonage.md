# 🚀 TP 1 : Configuration et Clonage d'un Projet Distant

Ce premier TP vous met directement dans un contexte de travail réaliste : récupérer un projet existant sur un dépôt distant (GitLab).

## 🎯 Objectifs
* Configurer votre identité pour vos futurs commits.
* Créer un dépôt initial sur GitLab.
* Cloner le projet distant sur votre machine locale (`git clone`).
* Vérifier la connexion avec le dépôt distant.

## 🛠️ Instructions Détaillées

### Étape 1 : Configuration de l'Identité Git

Ouvrez votre terminal ou votre ligne de commande Git.

1.  **Définir votre Nom d'Utilisateur** :
    ```bash
    git config --global user.name "Prénom Nom"
    ```
2.  **Définir votre Adresse E-mail** :
    ```bash
    git config --global user.email "prenom.nom@exemple.com"
    ```
    > **Note Importante** : Cette adresse sera liée à tous vos commits. Utilisez l'e-mail que vous avez configuré sur GitLab.

3.  **Vérification (Optionnel)** :
    ```bash
    git config --global -l
    ```
    > Vérifiez que votre nom et votre e-mail apparaissent dans la liste.

### Étape 2 : Création du Projet sur GitLab

1.  Connectez-vous à votre instance **GitLab**.
2.  Créez un **Nouveau Projet Vide** (ex: `tp-git-clonage`).
3.  **Action Cruciale** : Cochez la case pour **initialiser le dépôt avec un fichier README**.
4.  Une fois le projet créé, copiez l'**URL de clonage** (privilégiez l'**HTTPS** pour commencer).

### Étape 3 : Clonage du Dépôt

Dans votre terminal :

1.  Naviguez vers le répertoire où vous souhaitez placer vos projets (ex: `cd ~/Documents/Cours-Git`).
2.  **Cloner le projet** en utilisant l'URL copiée :
    ```bash
    git clone <URL_de_clonage_gitlab>
    ```
3.  **Entrer dans le nouveau répertoire** créé par Git :
    ```bash
    cd tp-git-clonage
    ```

### Étape 4 : Inspection et Connexion

1.  **Vérifier l'état local** :
    ```bash
    git status
    ```
    > Le résultat doit indiquer : `working tree clean` (rien à commiter).

2.  **Voir l'historique** :
    ```bash
    git log
    ```
    > Vous devriez voir un seul commit : celui de l'initialisation du `README` sur GitLab.

3.  **Vérifier les dépôts distants** :
    ```bash
    git remote -v
    ```
    > Vous devriez voir le lien vers GitLab, nommé par défaut `origin`, pour les opérations `fetch` (récupérer) et `push` (envoyer).

---
