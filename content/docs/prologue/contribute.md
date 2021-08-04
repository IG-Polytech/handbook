---
title: "Contribuer"
description: "L'handbook IG est collaboratif. Cela signifie que n'importe qui peut proposer d'ajouter ou modifier du contenu dans le but de compléter, corriger ou mettre à jour celui-ci."
lead: "L'handbook IG est collaboratif. Cela signifie que n'importe qui peut proposer d'ajouter ou modifier du contenu dans le but de compléter, corriger ou mettre à jour celui-ci."
date: 2021-08-04T07:45:07+02:00
lastmod: 2021-08-04T07:45:07+02:00
draft: false
menu:
  docs:
    parent: "prologue"
images: []
weight: 200
toc: true
---

## Pourquoi contribuer ?

Le monde de l'informatique change rapidement et des choses qui étaient vrais hier peuvent facilement ne plus l'être demain. Mais il n'y a pas que l'informatique qui change, la formation au seins d'IG change elle aussi chaque année afin de s'adapter au monde du travail, à l'emploi du temps des enseignants-chercheurs, mais aussi aux retours des étudiants vis-à-vis de celle-ci.

C'est pourquoi le contenu de l'handbook IG peut être moins pertinent d'une année sur l'autre. Il est donc important que chaque année, les étudiants d'IG contribuent à maintenir le contenue de cet handbook à jour.

## Puis-je contribuer ?

Si tu es un étudiant d'IG alors oui bien-sûr, il ne faut pas hésiter ! Si ce n'est pas le cas tu peux toujours essayer, nous étudierons toute proposition de changement à l'handbook, mais nous rappelons que le contenu de cet handbook vise les étudiant de la formation en informatique et gestion de Polytech Montpellier.

## Comment contribuer ?

### Pré-requis

Afin de pouvoir contribuer il y a cependant quelques pré-requis techniques (n'ayez pas peur).

#### Git

Connaître le fonctionnement basique de Git semble être primordiale. En effet, il va falloir fork le projet, effectuer les changements voulus dessus puis effectuer une pull request sur Github et potentiellement échanger avec d'autres collaborateurs sur le contenu de cette pull request directement sur Github.

Si certains passagent du paragraphe précédent vous semblent flous, alors il est probable que nous n'ayez pas ce pré-requis.

#### Node

Afin de pouvoir visualiser vos changements en direct vous allez devoir setup ce projet qui utilise Node. Ce pré-requis n'est en réalité pas bloquant car il suffit de suivre les instructions de mise en place sans même trop savoir comment cela fonctionne.

#### Markdown

Le contenu du site est rédigé en Markdown qui est un langage de markup (balisage) assez simple à prendre en main. Ici aussi nous sommes face à un pré-requis qui est très facile à dépasser.

#### Hugo

Pour générer le contenu de ce site depuis tous les fichiers en Markdown, nous utilisons Hugo qui est un framework pour créer des sites grâce auquel nous pouvons nous concentrer essentiellement sur le contenu. Nous utilisons le thème Doks qui introduit de plus certaines syntaxes qui pourraient vous être utiles pendant la rédaction. Il est intéressant de lire la documentation de Hugo et de Doks avant de contribuer.

### Installation

#### Cloner le projet

Clonez le projet depuis Github :

`git clone https://github.com/IG-Polytech/handbook ig-handbook && cd ig-handbook`

#### Installer les dépendances

Pour cela il vous faut installer [NodeJS](https://nodejs.org/fr/) si vous ne l'avez pas déjà sur votre ordinateur.

{{< alert icon="💡" >}}
Pour vérifier si NodeJS est installé sur votre ordinateur, exécutez `node --version` dans un terminal. Si une version s'affiche, alors NodeJS est installé.
{{< /alert  >}}

Une fois que vous avez vérifier que NodeJS est installer, installer les dépendances du projet avec `npm install`.

#### Lancement du serveur de développement

Pour lancer le serveur de développement, exécutez `npm start`. Une fois le site généré, il devrait être accessible à l'adresse [http://localhost:1313](http://localhost:1313).

### Modification du contenu

Le contenu des pages du site se trouve dans le dossier `content`, pour en savoir plus, visitez le site de [Doks](https://getdoks.org/).

Une fois toutes les modifications voulues effectuées, vérifiez que vous n'avez pas d'erreur de format de fichier avec la commande `npm run lint`, cette vérification permet de garder un style cohérent entre tous les fichiers.

Une fois toutes les erreurs indiquées par `npm run lint` corrigées et le texte relu (pour limiter les fautes d'orthographe), il faut juste commit vos changements `git add . && git commit -m "le message de commit"`.

#### Format du message de commit

Le format du message du commit doit être le suivant : `<type>(<scope>): <message>`

Avec `type` :

- `typo` : correction d'une faute d'orthographe
- `workflow` : modification du workflow de développement / déploiement / build
- `style` : correction d'une erreur de format (identifiée par `npm run lint` par exemple)
- `content` : ajout de nouveau contenu ou mise à jour d'un contenu existant

Avec `scope` :

- pour tout sauf `toolchain` :
  - `docs` : modification de la documention
  - `blog` : modification de du blog
  - `home` : modification de la page d'accueil
  - `privacy` : modification de la page de la politique de condidentialité
  - `contrib` : modification de la page des contributeurs
- pour `toolchain` :
  - `chore` : mise à jour de dépendances (ou toute autre tâche de corvée)
  - `feat` : ajout d'une fonctionnalité
  - `fix` : correction d'une fonctionnalité

Tout le message de commit doit être en minuscule (sauf en cas d'initiales, de nom propre, etc ...).

Vous pouvez écrire les messages de commit en anglais ou français.

##### Exemples de messages de commit

- `content(docs): les JWT`
- `toolchain(chore): bump clipboard to v2.0.8`
- `content(blog): comment j'ai développé un handbook pour les IGs`
- `typo(home): correction d'une erreur dans le titre de la page`
- `toolchain(feat): ajout d'une commande pour mettre à la jour la date de modification`

### Création de la pull request

Utilisez [le système de pull request de Github](https://github.com/IG-Polytech/handbook/pulls) pour proposer vos changements. Ces derniers seront acceptés si `npm run lint` ne renvoie pas d'erreur, que le build de l'application passe sans erreurs (`npm run build`), que votre contenu a été relu, que toutes les fautes ont été corrigées, et que le contenu est pertinent vis à vis de cet handbook.

Si vous avez des doutes sur le fait que votre contenu soit acceptable dans cet handbook, n'hésitez à [ouvrir une issue](https://github.com/IG-Polytech/handbook/issues) sur le Github du projet pour en discuter.
