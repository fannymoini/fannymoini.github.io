---
title: "Créer un site avec Hugo et Github pages"
description: Partage d'expérience sur la création de ce site
date: 2024-01-02T18:58:12+01:00
---

<!--Skills:
- Hugo, Git, Github, Github pages, Github Actions, CI/CD, YAML, Markdown, Powershell
-->

Mon but était de créer et mettre en ligne **rapidement** et **gratuitement** un site **simple**, pouvant accueillir :
- un portfolio de projets pour illustrer mes compétences en Data Science.
- un blog pour partager l'expérience et les connaissances acquises en chemin.

<!--more-->

J'ai choisi d'utiliser un générateur de sites statiques, **Hugo**, et d'héberger le site gratuitement via **Github Pages**. La génération et le déploiement du site se font grâce à **Github Actions**.

## Important à savoir
1. L'usage de Github Pages version gratuite nécessite de garder le **dépôt public**. Cette solution ne convient pas si le code source des projets du portfolio doit rester confidentiel. 
	A l'inverse, si le but est justement d'offrir un aperçu de la manière dont vous avez structuré et documenté votre code - ce qui est mon cas - c'est une solution intéressante.
2. L'**URL par défaut** pour votre site sur Github Pages sera `<username>.github.io/<nom_du_dépôt>`. 
	Dans un second temps, il est possible d'acheter un nom de domaine séparément puis de configurer Github Pages pour l'utiliser.
	
## Prérequis
- savoir utiliser un **terminal**
- savoir écrire des fichiers **markdown**
- savoir utiliser **Git**
- avoir un compte **Github** et un token d'authentification
- avoir des connaissances basiques en **CI/CD** (principalement savoir consulter et interpréter les logs de Github Actions)

## Ressources
- installation de Hugo et prise en main : [Quick start](https://gohugo.io/getting-started/quick-start/)
- [Explication de la structure d'un site Hugo](https://jamstatic.fr/2017/06/07/migration-de-jekyll-a-hugo/)
- le thème que j'ai utilisé : [personal-web](https://github.com/bjacquemet/personal-web). Il est possible de customiser le thème via le système des layouts.
- déploiement : [Hugo + Github Pages](https://gohugo.io/hosting-and-deployment/hosting-on-github/)

Note : a priori il est possible d'intégrer des **Notebooks Jupyter**, comme suggéré [ici](https://romankurnovskii.com/en/posts/howto-render-notebook-in-hugo/) et [là](https://github.com/vlunot/nb2hugo-demo/blob/master/notebooks/blogging-with-jupyter-notebooks-and-hugo/blogging-with-jupyter-notebooks-and-hugo.ipynb)

## Troubleshooting
- Si vous rencontrez un problème avec le thème, pensez à vérifier que vous utilisez une version récente de Hugo.
- Dans le fichier de configuration principal, formattez les URL relative **sans** les préfixer par un `/` (`images/mon_image.jpg` plutôt que `/images/mon_image.jpg`). Sinon, le build en local ne montrera aucun problème, mais au déploiement Github Pages ne saura plus interpréter l'URL générée et ne trouvera plus les images.

## Pourquoi Hugo ?
Hugo est réputé pour sa rapidité et permet de refléter des modifications du site presque en temps réel. J'étais curieuse de tester ce framework dont la prise en main est simple au démarrage, avec de bonnes possibilités de customisation du site une fois qu'on a compris comment le dossier racine est structuré et les fonctionnalités qui sont proposées.