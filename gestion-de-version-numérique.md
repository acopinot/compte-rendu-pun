### Git et GitHub : Logiciels libres de gestion de versions
### Exemple d’utilisation en publication numérique 
##### Compte rendu de la présentation de Mr Frank Taillandier
**Jeudi 19 octobre 2017**
**Contact frank.taillandier@gmail.com, @dirtyF**
*Par Anne Laure Copinot et Marlène Tognifode*

###	Introduction : 
Le web est un univers en expansion constante depuis sa création, dont les standards ouverts, édités par le **[W3C](https://www.w3.org/)** (World Wide Web consortium), ont pour but d’assurer une croissance pérenne du Web.  
Le graphe très visuel sur [l'évolution du web]( http://www.evolutionoftheweb.com/) montre le développement du web avec la multiplication des navigateurs et technologies (en particulier depuis 2008), et la rapidité croissante des nouvelles versions (livrables) de toutes ces technologies.
Dans ce monde en mouvement constant, où les cycles de livraison sont raccourcis, le logiciel libre permet une grande collaboration dans la création de ce contenu web. 

###	Des outils collaboratifs de gestion de versions 
Afin d’assurer le développement de tout ce contenu web, il est indispensable d’utiliser **des outils de gestion de versions**, qui permettent de garder trace des modifications faites sur les documents (code ou autres) et de pouvoir revenir à tout moment sur ces modifications. 
Il existe de nombreux outils de gestion de versions : Git et GitHub sont des plateformes open source qui se développent.
Git et Github permettent de travailler de manière collaborative, en créer des branches du projet : cela permet de faire des modifications sur un projet dans un espace précis : ces modifications seront ensuite fusionnées dans la branche maitresse, la *master branch* du projet. C’est cette capacité de branchements et les techniques collaboratives Open source (échanges avec par exemple des révisions de fichiers par paires – *peer to peer review*-), qui donnent à Git et GitHub toute leur force dans un environnement Web où il faut être très réactif.
**Git** est un outil de gestion de versions, principalement utilisé par des développeurs, qui fonctionne avec des lignes de commandes.
**Github** fonctionne tel un réseau social de développeurs, et inclut les fonctionnalités de Git avec en plus un service en ligne permettant d’héberger du code open source.
En 2017, on compte dans le monde 24 millions d’utilisateurs (dont la moitié d’étudiants), 67 millions de projets, 1.5 millions d’organisations (dont des grands noms tels Microsoft et google) et a eu lieu le 1 milliardième merge, qui se trouve être un document.  Voir https://octoverse.github.com/

###	Utilisation de Git et GitHub : 
#####	Git : 
Git est utilisé principalement par des développeurs, car fonctionnant avec des lignes de commandes dans la base de la console, ce qui rend son utilisation assez technique. 
Les principales commandes pour naviguer dans la ligne de commande sous Linux sont :
•	***ls*** qui permet de voir la liste des fichiers et des répertoires dans le dossier courant
•	***cd nomDeRepertoire*** qui permet de se place dans un répertoire
•	***mv nomDeFichier1 nomDeFichier2*** qui permet de déplacer un fichier ou à le renommer dans les répertoires
Les principales commandes Git sont les suivantes :
•	***Git add nomDeFichier*** qui permet d’ajouter le fichier dans l’index Git
•	***Git commit nomDeFichier*** qui permet à Git d’enregistrer les modifications
Voir une liste plus complète des [commandes Git]( https://ndpsoftware.com/git-cheatsheet.html)
Il y a plusieurs espaces de travail avec Git, avec deux espaces de dépôt :
•	Dépôt local :
o	L’espace de travail local qui contient réellement les fichiers
o	Le second espace est l’**Index** qui joue le rôle d’espace de transit pour les fichiers
o	Le troisième espace est la **Tête** ou **Head** qui pointe sur la dernière validation (ou version) des fichiers. 
•	Après le dépôt local, se fait le dépôt distant, c’est-à-dire que les fichiers sont « poussés » ou *« pushed »* vers le dossier distant (serveur) 
####	Github :
GitHub fonctionne via une interface plus facile d’utilisation que Git, c’est cet outil que nous devrions utiliser. 
Le guide sur [GutHub](https://guides.github.com/) détaille le WorkFlow et son flux de travail dans l’utilisation de GitHub.

###	Implémentation d’un projet existant – Vocabulaire du Workflow Git/ GitHub
Il semble important de connaitre et d’utiliser le vocabulaire en anglais, qui est la langue la plus utilisée dans le monde informatique. 

- *Etapes du workflow* 
**1. Create a branch**
Avec la création d’une branche dans un projet, on crée un environnement permettant de développer de nouvelles idées qui n’affectent pas la branche principale du projet. Par définition, une branche est destinée à mourir assez rapidement. 
**2. Add Commits**
Après la création de la branche, on peut faire des changements dans les fichiers (ajout, édition, suppression). Cela permet à tous de voir les différentes versions des fichiers et de comprendre l’évolution du travail.
**3. Open a pull request**
A pull request permet d’entamer une discussion avant de faire un commit. C’est un point fort dans les projets open source, puisque que valorisant la collaboration. 
**4. Discuss and review code**
Une fois la *pull request* ouverte, les personnes faisant partie de l’équipe de révisions font des remarques ou posent des questions sur les changements proposés. En théorie, deux personnes doivent relire ces modifications.
**5. Deploy**
Une fois la *pull request* revue et acceptée, il est possible de déployer le changement (*deploy*). Cependant, en cas de problème ultérieur, il est toujours possible de revenir en arrière et d’utiliser une autre version du fichier.
**6. Merge**
Une fois tous les changements revus et acceptés, la branche créer converge vers la branche principale ou branche master, c’est-à-dire faire un *merge*.
Le [tutoriel suivant](https://try.github.io/levels/1/challenges/1) permet une introduction au fonctionnement de GitHub.

### GitHub et la publication numérique : le projet Getty
Le [musée Getty]( http://www.getty.edu/), situé à Los Angeles, a un centre de publication dédié, qui produit des livres papier ou numériques dans les domaines de l’histoire de l’art, l’architecture, la photographie… 
Le musée Getty utilise un nouvel outil d’édition développé en interne, **Quire**, qui permet l’optimisation de la chaine de publication, utilisant un générateur de site statique, [**Hugo**]( https://gohugo.io/) et un template (ou modèle) de livre numérique **Middleman** . 
Quire, une chaine de production de site statique, a plusieurs objectifs complémentaires, et permet notamment : 
-	De rendre le travail de publication accessible le plus longtemps possible, car les contraintes technologiques sont moindres qu’avec un déploiement basé sur un logiciel complexe tel un CMS (*Content Management System*). 
-	D’assurer aux auteurs et éditeurs le contrôle de leurs documents grâce à l’utilisation d’outils open source et non propriétaires (et non pas des outils propriétaires qui peuvent ne plus être maintenus à échéance variée)
-	De produire un travail de design et typographique de qualité dans cet environnement de site « statique ».
Les fichiers sont écrits sur l’ordinateur local de l’éditeur, dans un langage de balisage léger, *Markdown*. 

L’utilisation de **Markdown** étant facile à maitriser, l’éditeur de contenu peut travailler rapidement et directement sur les fichiers source qu’il souhaite modifier puis publier. 
Avec le générateur de site statique, les fichiers utilisés par l’éditeur sont chargés sur le serveur et l’utilisateur final (le lecteur) y accède directement online. Afin de changer quelque chose dans le contenu éditorial, il suffit donc de changer le fichier de l’éditeur en local, de remettre à jour les fichiers sur le serveur grâce au software Quire, et le lecteur a ainsi directement accès aux dernières modifications de l’édition. 
La chaine de publication est donc réduite au minimum et est ainsi extrêmement souple et rapide, limitant aussi les erreurs qui se multiplient plus l’environnement technique se complexifie.
Malgré le nom de « statique », les sites statiques peuvent être dynamiques et interactifs grâce à l’utilisation des outils de plateformes web (HTML5, CCS3 et Javascript). 
On peut retrouver tout le projet de publication numérique sur https://github.com/gettypubs.

**A noter :**
- **Le Getty propose des stages à Los Angeles...** Voir http://www.getty.edu/about/opportunities/intern_opps.html
- Nous avons utilisé l'éditeur **dillinger** pour éditer le texte en Markdown : voir https://dillinger.io/


###	En conclusion
Le monde de l'open-source est d'une grande puissance, puisqu'il permet de collaborer afin de partager l'expérience de tous et ainsi d'obtenir le meilleur résultat possible.  Git et GitHub sont des produits nés de cette émulation. 




 






   
