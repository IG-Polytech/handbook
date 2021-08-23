---
title: "Tout savoir sur npm"
description: "Le gestionnaire de paquets node n'aura plus de secrets pour vous."
lead: "Le gestionnaire de paquets node n'aura plus de secrets pour vous. Dans la suite de cet article vous en saurez davantage sur cet outil dont vous ne pourrez plus vous passer."
date: 2021-08-04T07:45:07+02:00
lastmod: 2021-08-04T07:45:07+02:00
draft: false
menu:
  docs:
    parent: "technos"
images: []
weight: 200
toc: true
---
## Qu'est-ce que npm ?

Npm est le gestionnaire de paquets officiels de Node.js.
À l’origine, son nom était probablement un acronyme pour **N**ode **P**ackage **M**anager mais la société qui gère la bibliothèque (npm, Inc.) a toujours contredit cette affirmation, probablement en raison de possibles litiges juridiques autour du nom "Node".

{{< alert icon="💡" >}}
Cet outil a été racheté par Github en 2020.
{{< /alert  >}}

Pour toute information complémentaire, referez-vous à la [documentation officielle](https://docs.npmjs.com/) 📗

## A quoi ça sert ?

Il y a un dicton très célèbre qui dit:

> << Les développeurs sont des faignants, ils ne veulent jamais coder deux fois la même chose >>

Certes, je viens de l'inventer mais croyez-moi il est inutile de recréer la roue quand tout le monde roule déjà en Mercedes. Il en est de même pour les fonctionnalités que vous allez coder. Sachez que quelqu'un les a déjà écrite, en mieux.

Vous pouvez télécharger des morceaux de code (paquets) que vous trouvez sur internet et les intégrer à votre projet en tant que dépendance mais le mieux reste d'utiliser l'outil crée dans ce but précis: **npm**. Il permet notamment de télécharger, installer, mettre à jour et désinstaller très facilement des ressources. De plus, il permet de gérer efficacement les dépendances et les conflits entre paquets.

Avec plus d'1M de paquets disponibles gratuitement vous trouverez surement votre bonheur dans cette immense bibliothèque.

Il existe de nombreux équivalents à **npm** pour les autres languages de programmation:

- [Maven](https://maven.apache.org/) (java)
- [Bundler](https://bundler.io/) (ruby)
- [Composer](https://getcomposer.org/) (php)
- etc …

## Des alternatives ?

Si npm est le gestionnaire de paquets le plus populaire de l’écosystème JavaScript, plusieurs alternatives ont le mérite d’exister.

Fin 2016, Facebook a annoncé la disponibilité de [Yarn](https://yarnpkg.com/), un gestionnaire de paquets qui se veut rapide, fiable et sécurisé.

Si Yarn propose de nouvelles fonctionnalités et un cœur adapté aux très grosses entreprises, il se base tout de même sur le registre de npm. Les paquets disponibles sont donc les mêmes, et Yarn est simplement un autre outil pour installer et gérer les paquets, différent de celui installé nativement avec npm.

Yarn reste donc dépendant du gestionnaire de paquets le plus populaire, dont la suprématie n’est pas sans inconvénients.

## Installer npm

Pour bénéficier des fonctions de gestion de paquets et d’utilitaire en ligne de commandes de npm, il faut commencer par installer npm sur son système.

Depuis la version 0.6.3 de Node.js, npm est livré par défaut avec Node. Pour l’installer, il suffit donc d’installer Node.js sur votre système.

Si vous n'avez pas encore installé Node.js vous pouvez l'installer en suivant ces [instructions](https://www.ganatan.com/tutorials/installer-nodejs).

Pour connaître la version de npm installée sur votre système vous pouvez taper la commande `npm -v`.

Pour mettre à jour votre version de npm sur Linux et MacOs tapez la commande `npm install -g npm@latest`, sur Windows tapez `npm-windows-upgrade`.

## Installer son premier paquet

Afin de créer le ficher qui va gérer les dépendances du projet lancez simplement la commande `npm init`.

Un assistant de configuration sera alors lancé, vous devrez renseigner quelques informations. Pour éviter cette étape vous pouvez taper "entrer" plusieurs fois ou lancer la commande `npm init -y`.

Une fois l'assistant fermé vous devrez avoir vu apparaître un vouveau ficher appelé `package.json` à la racine de votre projet. C'est ce fichier qui liste les dépendances de votre projet.

Pour installer votre premier paquet rien de plus simple, nous allons installer un petit utilitaire appelé [Lodash](https://www.npmjs.com/package/lodash). Tapez la commande `npm install lodash`. Regardez votre fichier `package.json`, il devrait y avoir une nouvelle dépendance.

Pour importer lodash dans un fichier javascript il vous suffit d'utiliser `require('lodash')`. Pour plus d'informations sur l'utilisation de lodash, veuillez suivre [ce lien](https://www.npmjs.com/package/lodash).

{{< alert icon="💡" >}}
Vous avez surement constaté que lorsque vous avez installé votre premier paquet un nouveau dossier est apparu à la racine de votre projet. Ce dossier appelé `node_modules` contient les dépendances que vous avez ajoutées avec npm. Il ne faut pas toucher à ce dossier à moins de savoir exactement ce que vous faites. Si par mégarde vous avez altéré le contenu de ce dossier ou que vous avez des problèmes avec vos paquets, vous pouvez supprimer ce dossier car il est possible de le régénérer en lançant la commande `npm install`.
{{< /alert  >}}

## Quelques commandes npm

- `npm install` Installer les dépendances du fichier package.json
- `npm install <paquet>` Installer un paquet
- `npm uninstall <paquet>` Désinstaller un paquet
- `npm update <paquet>` Mettre à jour un paquet
- `npm install --global <paquet>` Installer globalement un paquet
- `npm install --save-dev <paquet>` Installer un paquet pour le développement
- `npm list` Lister les paquets du projet
- `npm run` Lister les scripts
- `npm run <script>` Lancer un script

{{< alert icon="💡" >}}
Pour aller plus vite :

- `install` = `i`
- `uninstall` = `un`
- `update` = `up`
- `--global` = `-g`
- `--save-dev` = `-D`

{{< /alert  >}}

## Publier son premier paquet

Il est très simple de publier son premier paquet sur npm. Vous devez premièrement créer un compte sur le [site officiel npm](https://www.npmjs.com/) puis suivre ce [tutoriel Youtube](https://www.youtube.com/watch?v=J4b_T-qH3BY).

## Les dangers de npm

En Mars 2016, un développeur du nom de Azer Koçulu a retiré plus de 250 de ses paquets du registre de npm. La raison : l’un de ses modules s’appelait “Kik”, le même nom que porte une célèbre application de messagerie instantanée, ce qui a retenu l’attention des avocats de cette dernière qui ont demandé à Azer Koçulu de renommer son module. Après son refus, les avocats ont porté une réclamation à l’administration de npm qui ont retiré le module pour atteinte aux droits de la marque.

Furieux, Koçulu a alors dépublié tous ses paquets dont le module "left-pad" composé de 11 lignes de code permettant d’ajouter des 0 ou des espaces devant une chaîne de caractères.

Le problème, c’est que des milliers de projets dépendaient de ce module dont Node.js ou Babel qui se sont retrouvés inutilisables en l’état pour des millions d’utilisateurs.

La situation a forcé les dirigeants de npm à restaurer une version précédente du module, qui a par la suite été déprécié, mais l’anecdote est représentative des risques liés à une dépendance trop importante à un seul et même registre.

C’est pourquoi de gros acteurs du marché tels que Google, Amazon ou Microsoft proposent désormais des alternatives pour stocker des paquets privés.

[Consulter l'article](https://qz.com/646467/how-one-programmer-broke-the-internet-by-deleting-a-tiny-piece-of-code/) 👀
