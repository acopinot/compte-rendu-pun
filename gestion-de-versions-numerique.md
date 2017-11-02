---
title: "Git et GitHub : gestion de versions et publication numérique"
date: 2017-10-19
description: Compte-rendu d'Anne-Laure Copinot et de Marlène Tognifode de l'intervention du 19 octobre 2017 de Frank Taillandier au master en publicaition numérique de l'ENSSIB de Lyon
slug: gestion-de-versions-numerique
authors:
  - acopinot
  - dirtyf
---

# Présentation de Frank Taillandier

Contact: [Mail](mailto:frank@taillandier.me) · @DirtyF ·
[Twitter](https://twitter.com/DirtyF)

*Jeudi 19 octobre 2017*

*Compte-rendu par [Anne Laure Copinot](https://github.com/acopinot) et Marlène Tognifode*

##	Introduction

Le web est un univers en expansion constante depuis sa création, dont les standards ouverts, édités par le **[W3C](https://www.w3.org/)** (World Wide Web consortium), ont pour but d’assurer une croissance pérenne du Web.

Le graphe très visuel sur [l'évolution du web](http://www.evolutionoftheweb.com/) montre le développement du web avec la multiplication des navigateurs et technologies (en particulier depuis 2008), et la rapidité croissante des nouvelles versions (livrables) de toutes ces technologies.

Dans ce monde en mouvement constant, où les cycles de livraison sont raccourcis, la gestion de versions open-source permet une grande collaboration dans l'industrie du logiciel.

##	Des outils collaboratifs de gestion de versions

Afin d’assurer le développement de tout ce contenu web , il est indispensable d’utiliser **des outils de gestion de versions**, qui permettent de garder trace des modifications faites sur les documents (que ce soit du code ou de la documentation) et de pouvoir revenir à tout moment sur ces modifications.

Il existe de nombreux outils de gestion de versions : Git s'est rapidement imposé et a entrainé l'apparition de plate-formes comme GitHub.

Git et Github permettent de travailler de manière collaborative, en créant des branches du projet : cela permet de faire des modifications sur un projet dans un espace précis. Ces modifications seront ensuite fusionnées dans la branche maitresse, la *master branch* du projet.

C’est cette capacité de branchements et les techniques collaboratives Open source (échanges avec par exemple des révisions de fichiers par paires – *peer to peer review*-), qui donnent à Git et GitHub toute leur force dans un environnement Web où il faut être très réactif.

**Git** est un outil de gestion de versions, principalement utilisé par des développeurs, qui fonctionne en ligne de commande.

**Github** est devenu le plus grand réseau social pour les développeurs, et inclut une partie des fonctionnalités de Git avec en plus un service en ligne permettant d’héberger du code open source et d'échanger à propos du code et des modifications.

En 2017, on compte dans le monde 24 millions d’utilisateurs (dont la moitié d’étudiants), 67 millions de projets, 1.5 millions d’organisations (dont des grands noms tels Microsoft et Google) et a eu lieu le 1 milliardième merge, qui se trouve être un document. Voir [https://octoverse.github.com/](https://octoverse.github.com/)

##	Utilisation de Git et GitHub

###	Git

Git est utilisé principalement par des développeurs, car fonctionnant en ligne de commande dans un terminal, ce qui rend son utilisation assez technique.

Cela demande en effet d'être un minimum familiarisé avec la ligne de commande.

#### La ligne de commande

Voici quelques commandes unitaires de base :

•	`ls` qui permet de voir la liste des fichiers et des répertoires dans le dossier courant
•	`cd nomDeRepertoire` qui permet de se déplacer dans les répertoires
•	`mv nomDeFichier1 nomDeFichier2` qui permet de déplacer un fichier ou de le renommer.

#### La commande `git`

Parmi les commandes Git les plus usuelles on peut citer :
•	`git add nomDeFichier.ext` qui permet d’ajouter le fichier dans l’index Git
•	`git commit nomDeFichier -m "message du commit"` qui permet à Git d’enregistrer un instantané et de lui affecter une référence.

Une aide interactive est disponible en ligne de commande en tapant `git help` ou `git <sous-commande> --help`, exemple `git add --help`
pour la sous-commande `add` de `git`.

**Aide en ligne**

* La documentation de référence est disponible en ligne sur le site officiel : [https://git-scm.com/docs](https://git-scm.com/docs)
* [Le livre Pro Git est disponible en ligne et en français](https://git-scm.com/book/fr/v2) et détaille toutes les commandes.

On pourra aussi se référer à cet aide-mémoire visuel des [commandes Git](https://ndpsoftware.com/git-cheatsheet.html).

Cet aide-mémoire a le mérite de bien distinguer les différents étapes nécessaires à la publication dans Git :

* L’espace de travail local qui correspond aux fichiers présents dans le dossier — mais pas forcément encore versionnés.
* l’**index**, parfois aussi appelé `staging` qui joue le rôle d’espace de transit pour les sélection les fichiers à versionner et à regrouper dans un `commit`.
* **Le dépôt local** : L'état des fichiers et des branches, ainsi que l'historique des modifications.
* Le **dépôt distant** : c'est une instance du dépôt sur un serveur distant où les fichiers sont « poussés » grâce à la commande `git push` après chaque `commit` afin que chaque contributeur du projet puisse ensuite récupérer ces modifications. C'est souvent un service comme GitHub ou GitLab qui servira de dépôt distant. Lorsqu'on récupére un projet Git depuis GitHub via la commande `git clone` l'URL du dépôt distant est automatiquement ajoutée comme `origin`. Chaque dépôt distant possède un nom pour pouvoir y faire référence plus facilement.

Commande Git : `git remote -v` pour afficher tous les dépôts distants (il peut y en avoir plusieurs, en général un par collaborateur, il est ainsi possible de suivre le travail de chacun). La commande `git remote add` permet d'ajouter un dépôt distant.

###	Github
GitHub propose un service gratuit pour les projets sous licence libre ainsi qu'une interface plus simple d’utilisation que Git et vient offrir en plus de l'interaction et de la gestion de projet. C'est ce service que nous devrions utiliser.

Le guide de [GitHub](https://guides.github.com/) détaille le WorkFlow et son flux de travail dans l’utilisation de GitHub.

##	Versionner un projet avec Git et GitHub

### Vocabulaire et workflow

Comme tout logiciel en ligne de commande Git est en anglais. Il en va de même pour GitHub dont l'interface n'est pas disponible en français. Il est donc important de connaitre les termes  de référence en anglais.

GitHub propose également [`hub`](https://hub.github.com/) un utilitaire en ligne de commande qui permet d'interagir avec GitHub.

#### Étapes du workflow

1. **Créer une branche**: avec la création d’une branche dans un projet, on crée un environnement permettant de développer de nouvelles idées qui n’affectent pas la branche principale du projet.
   En général, la durée de vie d'une branche correspond au temps qui se sera écoulé entre les modifications faites dessus et la fusion dans la branche principale. La branche pourra ensuite être supprimée puisque toutes les modifications ainsi que l'historique auront été intégrés.
Commande git : `git branch ma-branche-de-travail; git checkout ma-branche-de-travail` ou en une seule fois `git checkout -b ma-branche-de-travail` pour créer la branche et se positionner dessus pour commencer à travailler.
2. **Enregistrer ses modifications** : après la création de la branche, on peut faire des changements dans les fichiers (ajout, édition, déplacement, suppression). On enregistre ensuite ses changements en faisant des `commits`. Pour chaque `commit` on pourra afficher les différences avant/après des modifications apportées. Cela permet à tous de voir les différentes versions des fichiers et de comprendre l’évolution du travail.
Commandes git : `git diff`, `git diff --staged` et `git commit -m "mon message de commit"`.
La consultation des différences est beaucoup plus lisible sur GitHub.
3. **Ouvrir une pull request**: une `pull request` est une étape nécessaire pour faire une demande de fusion de branche. Comme créer des branches est très simple avec Git ou GitHub, cela permet d’entamer une discussion même si peu ou pas de modifications ont été effectuées. On peut ensuite continuer de travailler sur la branche correspondante à la PR et ajouter des commits supplémentaires suite aux retours. C'est dans les pull requests qu'ont lieu les discussions importantes.
La `pull request` se fait une fois que la branche de travail a été poussée sur le dépôt distant avec `git push`.
Se reporter à l'aide de GitHub pour apprendre à créer des pull requests : [https://help.github.com/articles/about-pull-requests/](https://help.github.com/articles/about-pull-requests/)
À noter qu'il est possible d'ajouter des fichiers, de les modifier, de créer des branches et des pull requests entièrement depuis GitHub et donc sans passer par la ligne de commande. Cela demande donc d'avoir un accès internet.
Pour les modifications importantes, on préfèrera travailler tranquillement sur son dépôt local et soumettre les modifications une fois le travail terminé, cependant pour de petites modifications, passer uniquement par GitHub simplifie beaucoup le processus.
4. **Discussions et revue de code** : c'est également dans les *pull request* que les personnes en charge du projet vont pouvoir valider les changements proposés via la revue de code. GitHub permettant d'insérer des commentaires sur les changements apportés, c'est très pratique pour faire des retours très précis à l'auteur de la *pull request*. Sur les projets logiciels importants, il est souvent exigé que deux personnes relisent ces modifications afin de favoriser la connaissance partagée du projet.
5. **Fusion des branches** : une fois tous les changements revus et acceptés, la branche créée converge - en général vers la branche `master`. En anglais cette opération se dit `merge`.
GitHub facilite la fusion de branches en s'affranchissant de la ligne de commande, mais c'est une commande de base de Git (`git merge`).
6. **Déploiement** : une fois la `pull request` revue et acceptée, la branche peut être fusionnée (`merge`) et les changements déployés (`deploy`).
Grâce au versionnement, en cas de problème ultérieur, il est toujours possible de revenir en arrière et de se positionner dans un état précédent.
Pour démarrer et se familiariser avec le workflow, le mieux est de commencer par faire [ce tutoriel en ligne](https://try.github.io/levels/1/challenges/1) qui constitue une bonne introduction au fonctionnement de GitHub.

## GitHub et la publication numérique : le projet Getty

Le [musée Getty](http://www.getty.edu/), situé à Los Angeles, a un centre de publication dédié, qui produit des livres papier et numériques dans les domaines de l’histoire de l’art, l’architecture, la photographie…

Le musée Getty développe un nouvel outil d’édition, **Quire**, qui permet l’optimisation de la chaine de publication numérique, à l'aide d'un générateur de site statique, [**Hugo**](https://gohugo.io/) et d'un gabarit de livre numérique prêt à l'emploi.

[Quire](https://www.getty.edu/publications/digital/platforms-tools.html) a plusieurs objectifs complémentaires, et permet notamment :

-	de rendre le travail de publication moins coûteux car les contraintes technologiques sont moindres qu’avec un déploiement basé sur un logiciel complexe de type CMS (*Content Management System*),
-	d’assurer aux auteurs et éditeurs la pérennité et de leurs documents grâce à l’utilisation de formats standards en texte brut, contrairement aux outils propriétaires où l'on est dépendant d'un éditeur pour ouvrir un document,
-	de produire un travail de design et typographique de qualité grâce aux possibilités de CSS,
-	de faciliter les mises à jour en continu, car le temps de génération est extrêmement court, de l'ordre de quelques secondes avec Hugo.
-	de simplifier l'export au format Epub et de proposer des formats de livres numériques pour différentes plate-forme en ligne (Amazon, Google, Apple).

Les fichiers sont écrits sur l’ordinateur local de l’éditeur, dans un langage de balisage léger, *Markdown*.

L’utilisation de **Markdown** étant facile à maitriser, l’éditeur de contenu peut travailler rapidement et directement sur les fichiers source qu’il souhaite modifier puis publier.

Le générateur de site statique va ensuite transformer les fichiers Markdown en HTML, puis ils seront publiés sur un serveur distant via `git`. L’utilisateur final (le lecteur) peut donc y accèder directement en ligne.

Afin de faire une modification dans le contenu éditorial, il suffit donc de changer le fichier de l’éditeur en local puis de remettre à jour les fichiers sur le serveur grâce au logiciel Quire : le lecteur a ainsi directement accès aux dernières modifications de l’édition.

La chaine de publication est donc réduite au minimum et est ainsi extrêmement souple et rapide, limitant aussi les erreurs qui se multiplient quand l’environnement technique se complexifie.

Malgré le nom de « statique », les sites statiques peuvent être dynamiques et interactifs grâce à l’utilisation des outils de plateformes web (HTML5, CCS3 et Javascript). Quire permet par exemple aux lecteurs de faire des recherches dans le livre.

On peut retrouver tout le projet de publication numérique sur [https://github.com/gettypubs.](https://github.com/gettypubs.)

##	En conclusion

Git et GitHub permettent de collaborer afin de partager l'expérience de tous et ainsi d'obtenir le meilleur résultat possible. Ce sont de plus des solutions très accessibles, Git étant un logiciel libre, et GitHub ne faisant payer chaque utilisateur que pour héberger des dépôts privés. Le coût de fabrication d'un livre numérique est donc réduit à son strict minimum, grâce à des solutions comme Quire.


*Notes*:

- **Le Getty Museum propose des stages à Los Angeles...** Voir [http://www.getty.edu/about/opportunities/intern_opps.html](http://www.getty.edu/about/opportunities/intern_opps.html)
- Nous avons utilisé l'éditeur [**dillinger**](https://dillinger.io) pour éditer le texte en Markdown.
