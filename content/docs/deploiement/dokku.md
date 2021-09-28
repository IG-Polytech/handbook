---
title: "Dokku"
description: "Dokku est un outil de PaaS auto-hébergé dont des instances sont mises à disposition par Polytech pour les étudiants d'informatique et gestion"
lead: ""
date: 2021-09-24T11:25:28+02:00
lastmod: 2021-09-24T11:25:28+02:00
draft: false
images: []
menu: 
  docs:
    parent: "deploiement"
toc: true
contributors: ["Florent Hugouvieux"]
---

## Qu'est-ce que Dokku

[Dokku](https://dokku.com/) est un outil de PaaS (Platform as a Service) auto-hébergé construit sur Docker qui vous permet de déployer vos applications web. Dokku est grandement inspiré d'[Heroku](https://www.heroku.com/) qui est un service en ligne faisant aussi du PaaS, ainsi, vous pouvez utiliser tout [buildpack](https://devcenter.heroku.com/articles/buildpacks) supporté par [herokuish](https://github.com/gliderlabs/herokuish) directement sur une instance Dokku.

## Déployer sur Dokku à Polytech

En tant qu'étudiant en informatique et gestion à Polytech Montpellier, vous pouvez avoir accès à une instance de Dokku déployée directement sur les serveurs de l'école.

Pour avoir accès à une instance, vous devez [contacter Luca Cimini sur le Mattermost](https://mattermost.polytech.umontpellier.fr/ig/messages/@luca.cimini) et lui envoyer votre **clé publique** SSH afin qu'il puisse l'ajouter à la machine virtuelle correspondant à votre année :

- IG3 : cluster-ig3.igpolytech.fr
- IG4 : cluster-ig4.igpolytech.fr
- IG5 : cluster-ig5.igpolytech.fr

{{< alert icon="💡" >}}
Si vous n'avez pas de paire de clé SSH vous pouvez en créer une en suivant les instructions indiquées [ici](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).
{{< /alert >}}

Une fois votre clé publique SSH ajoutée sur le cluster correspondant à votre année, vous pouvez accéder à l'instance Dokku par SSH sur ce dernier. Exemple, si je suis en IG3 :

```txt
$> ssh dokku@cluster-ig3.igpolytech.fr help
    apps                     Manage apps
    buildpacks               Manage buildpack settings for an app
    certs                    Manage SSL (TLS) certs
    checks                   Manage zero-downtime settings
    cleanup                  Cleans up exited/dead Docker containers and removes dangling images
    config                   Manage global and app-specific config vars
    docker-options           Manage docker options for an app
    domains                  Manage domains used by the proxy
    enter                    Enter running app containers
    events                   Manage event logging
    git                      Manage app deploys via git
    help                     Print the list of commands
    logs                     Manage log integration for an app
    network                  Manage network settings for an app
    nginx                    Manage the nginx proxy
    plugin                   Manage installed plugins
    proxy                    Manage the proxy integration for an app
    ps                       Manage app processes
    repo                     Manage the app's repo
    resource                 Manage resource settings for an app
    run                      Run a command in a new container using the current application image
    scheduler-docker-local   Manage the docker-local scheduler integration for an app
    shell                    Interactive dokku prompt
    ssh-keys                 Manage public ssh keys used for deployment
    storage                  Manage mounted volumes
    tags                     Manage docker image tags
    tar                      Manage app deploys via tar
    trace                    Manage trace mode
    url                      Show the first URL for an application (compatibility)
    urls                     Show all URLs for an application
    version                  Print dokku's version
    acl             Plugin to manage app-level Access Control Lists
    elasticsearch   Plugin for managing Elasticsearch services
    letsencrypt     Plugin for managing letsencrypt app integration
    mongo           Plugin for managing MongoDB services
    postgres        Plugin for managing Postgres services
    redis           Plugin for managing Redis services
$>
```

Pour tout ce qui concerne les commandes liées à Dokku lui-même, vous pouvez vous référer à la [documentation de Dokku](https://dokku.com/docs/deployment/application-deployment/).
