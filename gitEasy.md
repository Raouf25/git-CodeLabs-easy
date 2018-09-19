author: Gabin Darras
summary: Git Easy
id: codelabs-gitEasy
categories: git
environments: javascript
status: draft
feedback link: github.com/gabindarras
analytics account: 0

# Git - Débutant

## Présentation

Une question ? Une difficulté ? : **gabin.darras@ineat-conseil.fr**

Pré-requis:

- Avoir **git** installé sur votre machine.
- Avoir un compte Github/Gitlab pour pouvoir forker le projet

## Récupération du projet

Ouvrez un terminal à l'endroit où vous souhaitez dérouler ce CodeLabs

```
git clone le-nom-de-votre-projet-après-le-fork
```

Cette commande vous permettra de récupérer le projet 'git', pour pouvoir manipuler les différentes commandes il faut se mettre à la racine de ce dernier, pour cela :

```
cd git
```

## Branches

### Liste des branches disponibles

Pour récupérer la liste des branches, entrez la commande ci-dessous

```
git branch
```

À ce stade nous n'avons qu'une seule et unique branche "master", comme cette branche n'est destinée qu'à la production nous allons devoir en créer une autre pour le développement.

### Création d'une branche

Pour créer une nouvelle branche, entrez la commande suivante

```
git branch develop
```

La branche develop vient d'être créée, pourtant nous sommes toujours sur la branche master, pour s'en rendre compte faîtes la commande git branch que vous maitrisez maintenant parfaitement bien :)

### Changement de branche

Nous devons maintenant nous placer sur la develop pour pouvoir commencer à travailler

```
git checkout develop
```

Nous sommes maintenant prêt à travailler !

## 1e commit

**Hé la hé la pas si vite voyons, la branche develop est elle aussi protégée ! Encore ? Et oui vous imaginez si tous les développeurs travaillaient sur la même branche de travail, ça serait l'anarchie ! À chaque nouveau dev on tire une branche à partir de develop**

### Astuce pour chaque nouvelle branche

On a vu précédemment comment créer une nouvelle branche et comment se placer dessus. Mais tout dev qui se respecte est fénéant et faire 2 commandes pour une simple action ne me plaît pas ! Heureusement git nous permet de faire cette opération en une, pour cela entrez la commande suivante :

```
git checkout -b le-nom-de-ma-nouvelle-branche
```

le -b signifie ici nouvelle branche

### La branche feat/first-commit

#### Création

Maintenant que vous connaissez la commande pour créer et switcher sur une nouvelle branche vous pouvez créer la branche 'first-commit' :

```
git checkout -b first-commit
```

#### Modification

Comme vous l'avez très justement remarqué le nom de la branche est incorrect car il n'indique pas le type de branche qu'on souhaite créer. Mais pas de panique c'est très facile de renommer notre branche grâce à la commande

```
git branch -m le-nom-de-ma-branche-actuelle le-nouveau-nom
```

Ce qui donnera dans notre cas :

```
git checkout -m first-commit feat/first-commit
```

Un petit coup de 'git branch' pour s'assurer que la branche a bien été modifée.

### Modification du fichier README.md

Ouvrez le fichier README.md et recopier le texte suivant

```
Ce projet a pour but de vous enseigner les bases de git !
Pour cela, déroulez le CodeLabs : https://github.com/gabindarras/git-CodeLabs-easy
```

Vous pouvez à tout moment consulter l'état de modification avec la commande

```
git status
```

Voici ce qu'on obtient
![git-status](screenshots/git-status.png)

Le fichier est en rouge donc ça veut dire que les modifications n'ont pas encore été indexées donc nous ne sommes pas encore prêt à commit

### Indexation, commit & push

#### Indexation

Après avoir modifié un ou plus fichiers, il faut les indexer, c'est à dire indiquer à git que ces derniers sont prêts à être commit

Pour cela exécutez la commande suivante

```
git add README.md
```

puis un 'git status', vous obtenez ceci
![git-status-2](screenshots/git-status-2.png)

#### Commit

Le fichier est maintenant prêt à être commit sur la remote, voici la commande

```
git commit -m "feat(readme): add CodeLabs infos"
```

En faisant un 'git status' on s'aperçoit que les modifications ont bien été prises en compte, il ne nous reste qu'à push !

#### Push

En l'état actuel des choses les modifications sont sur la remote mais pas encore sur le repo distant, pour cela exécutez la commande suivante

```
git push origin feat/first-commit
```

### Historique

Pour consulter l'historique des commits effectués vous avez la commande suivante

```
git log
```