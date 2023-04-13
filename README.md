# Checklist de fin de site

Une TODO liste de vérifications à effectuer avant de passer un site en ligne.

Il n'y aura pas forcément l'ensemble des liens, il s'agit plutôt d'une description exhaustive, après appliquer la méthode SSLDDC.

À noter que la liste est über longue après plus de 12 ans à galérer ; à minima passer un coup de [pagespeed insight](https://pagespeed.web.dev/?hl=fr) pour virer le plus gros.

## Utilisation recommandée

1. Cloner ce repo pour chaque projet
2. Valider & cocher ✅ chaque point pertinent

## Sommaire

1. Projet git
   1. Créer un README.md propre
   2. Communauté
2. Optimisations du code
3. Optimisations du projet
   1. Images & vidéos
4. Validateurs +- en ligne
5. Optimisations côté serveur
6. Listes dédiées aux technologies
   1. HTML
   2. CSS
   3. Javascript
   4. PHP
   5. WordPress
   6. Docker
7. Liste de ressources supplémentaires

---

## Projet git

Il y a un repo dédié [base-repository-github](https://github.com/youpiwaza/base-repository-github/).

Il contient tous les fichiers usuels alakon :

1. .gitignore
   1. Pas mal de trucs à rajouter dedans, notamment concernant les OS & les packages managers
   2. Ne pas hésiter à ~~viander~~ 🔥 supprimer les fichiers concernés après la mise à jour de ce fichier
2. humans.txt
3. LICENSE
4. ~Linters
   1. .editorconfig
   2. .eslintrc
   3. .htmllintrc
   4. .jsbeautifyrc
   5. .stylelintrc
   6. whatever

### Créer un README.md propre

Il y à un boilerplate dans mon repo dédié [base-repository-github > _README.md](https://github.com/youpiwaza/base-repository-github/blob/main/_README.md).

1. Petite description du projet
2. Capture d'écran d'illustration
3. Commandes usuelles (~comment faire tourner le projet, commande de dev/build/prod)
4. Commandes de mise à jour, de maintenance
5. Commandes d'installation (one shot)
6. Problèmes usuels
7. Documentation (plus poussée, dossiers & fichiers dédiés)
8. Technologies utilisées dans le projet
9. Ressources
10. Credits

Ne pas oublier que l'on peut également rajouter un fichier `README.md` dans des dossiers dédiés afin de ne pas spammer à la racine.

Maximiser l'utilisation du langage Markdown :

1. Rajouter des liens (vers la doc interne, vers les ressources externes)
2. Rajouter des tableaux, en cas de grandes listes, en vrai [c'pas si pire](https://www.tablesgenerator.com/markdown_tables).
3. Rajouter des images
   1. `/_docs/images/`
   2. Ne pas oublier de les optimiser

Je recommande également l'utilisation de tutoriels vidéos, via la capture d'écran + micro.

Cela permet de faire des démonstrations en live, notamment pour :

1. Les processus d'installation
2. Mise en place de l'environnement de dev
3. Travaux usuels
4. Que cela soit pour les devs ou pour les utilisateurs finaux (démo d'administration)
5. Sauvegarder, exporter, importer
6. etc.

### Communauté

1. CODE_OF_CONDUCT.md
2. CONTRIBUTING.md
3. Changelog.md
4. Remerciements, liens vers ressources

---

## Optimisations du code

1. Virer le code mort / inutilisé
   1. Article [dev.to > Chrome find unused code](https://dev.to/dailydevtips1/chrome-find-unused-code-3g9c)
   2. Pas mal de packages dédiés en fonction des technos, ou voir pour compilateurs ~webpack, gulp, etc.
2. Faire une configuration propre du fichier
   1. Optimisation de cache navigateur
   2. SEO > Ignorer dossiers `~/wp-admin/`
   3. Sécurité
3. SEO
   1. Fichier `robots.txt`
   2. Fichier `sitemap.xml`
   3. `.htaccess` > Redirections anciens sites
4. Vérifier la console (inspecteur du navigateur)
   1. Ca coute rien de re-vérifier après la mise en place de cache
5. Package manager > bloquer versions pour les mineures maximum
6. 📱 Vérifier responsive
   1. Apparence
   2. Apparence entre les breakpoints
   3. Comportements

---

## Optimisations du projet

1. Virer les fichiers inutilisés
2. Mise en place d'une page 404 propre
3. SEO
   1. Correcteur orthographe
   2. Balises title pour chaque page
   3. Page Plan du site
   4. Vérifier l'absence de liens morts
   5. Vérifier les liens vers l'extérieur
      1. la pertinence
      2. ~`nofollow`
      3. attribut `target="_blank"`, voir ajout automatique d'icône d'indication
      4. attribut `title`
   6. Images
      1. Si pertinentes dans le contenu, attributs `title` & `alt`
      2. Sinon, indiquer rôle
   7. [Liste de liens > ref nat](https://docs.google.com/spreadsheets/d/1COXPrsJgAJyfXOT7aNZULCDMOYhctlzI5kXOxw7vE64/edit#gid=1893195632)
4. Analytics, trafic utilisateurs & autre
   1. Alternative à gougeul / [Matomo](https://fr.matomo.org/)
   2. [google](https://analytics.google.com/analytics/web/), may 🍪 cookies
5. Mentions légales
   1. Société exploitant le site
   2. Société hébergeant le site
   3. Pas mal de trucs, dépend du contenu du site. Grosses catégories :
      1. ~Textes et photos non contractuels
      2. ~Contenu du site
      3. ~Droits d’auteur
   4. [Site professionnel, france](https://entreprendre.service-public.fr/vosdroits/F31228/personnalisation/resultat?lang=&quest0=0)
6. 🍪 RGPD cookies [blah, france](https://www.francenum.gouv.fr/guides-et-conseils/developpement-commercial/gestion-des-donnees-clients/comment-rendre-le-fichier)

### Images & vidéos

1. Vérifier les ratios, éviter les redimensionnements
2. Si t'es maso go `src-set`, il y a un article alsacreation qui traine
3. Optimiser & minifier
   1. Utiliser les nouveaux formats `.webp` & `.webm`, ou AVIF
      1. Il y a des plugins WordPress afin de l'appliquer de manière transparente
   2. Sinon à l'ancienne
      1. JPG > Qualité 60, Progressif
      2. PNG > Mettre un [coup de panda](https://tinypng.com/)
   3. [SVG](https://github.com/svg/svgo)
4. Droits des images > [Reverse image check](https://tineye.com/)

---

## Validateurs +- en ligne

1. [Google pagespeed insights](https://pagespeed.web.dev/)
   1. Extrèmement complet
   2. Et puis bah appliquer l'ensemble des recommandations autant que possible, la doc est vraiment bien
2. Standards HTML > [W3C validator](https://validator.w3.org/)
3. Sécurité
   1. [Security headers](https://securityheaders.com/)
4. SEO
   1. [Domsignal](https://domsignal.com/website-audit)
   2. ~google crawler / [totheweb > search engine simulator](https://totheweb.com/learning_center/tools-search-engine-simulator/)
      1. Fait ressortir les mots clés, recos d'utilisation de balises
5. Accéssibilité (tags dédiés, contrastes, etc.)
   1. [AccessiBe > Scan](https://accessibe.com/accessscan)
6. Responsive
   1. Inspecteur du navigateur lel
   2. avec inscription : [Lambda test](https://www.lambdatest.com/)
7. Ecologie (.. ui ui)
   1. Empreinte carbone de ton site [websitecarbon.com](https://www.websitecarbon.com/)

---

## Optimisations côté serveur

1. Recommandations [gougeul pagespeed](https://developers.google.com/speed?hl=fr) ~modules pour Apache / Nginx / Litespeed
   1. Cache serveur
2. HTTPS ~Let's encrypt
3. HTTP2 - 3
4. CDN
5. Gestion des emails
   1. Vérification que le serveur n'est pas en spam
   2. Création de templates pour les emails sortants
   3. SPF
   4. DKIM
   5. DMARC
   6. [Liste de liens > Emails](https://docs.google.com/spreadsheets/d/1COXPrsJgAJyfXOT7aNZULCDMOYhctlzI5kXOxw7vE64/edit#gid=222850098)
6. Gestions des principaux code d'erreurs de manière propre
   1. 500 / kaput
   2. ??? / Trop de monde
   3. etc.
7. Bases de données
   1. Utilisateurs > blog masamune "Mysql / Bonnes pratiques / Créer un utilisateur"

---

## Listes dédiées aux technologies

Quand y'en a plus y'en à encore

1. [HTML](./html.md)
2. [CSS](./css.md)
3. [Javascript](./javascript.md)
4. [PHP](./php.md)
5. [WordPress](./wordpress.md)
6. [Docker](./docker.md)

---

## Liste de ressources supplémentaires

Pour aller plus loin, may faut lire & testay

1. Ma [liste de liengs](https://docs.google.com/spreadsheets/d/1COXPrsJgAJyfXOT7aNZULCDMOYhctlzI5kXOxw7vE64/edit#gid=485737622)
   1. Onglets bonnes pratiques, et autres en fonction des besoin
2. Accessibilité
   1. [dev.to > Web Accessibility: By making your website accessible, you automatically increase the target audience](https://dev.to/karkranikhil/web-accessibility-by-making-your-site-accessible-you-automatically-increase-the-target-audience-d8d)
3. SEO
4. Sécurité
   1. Principales failles expliquées / [hacksplaining](https://www.hacksplaining.com/lessons)
5. Optimisation / speed
   1. [dev.to > Making a fast website is SUPER EASY](https://dev.to/enterspeed/making-a-fast-website-is-super-easy-9lb)
6. PWA / Progressive Web Apps
   1. [WebDesignerDepot > Should You be Building Progressive Web Apps?](https://www.webdesignerdepot.com/2019/03/should-you-be-building-progressive-web-apps/)
7. [UT / Unit Testing](https://docs.google.com/spreadsheets/d/1COXPrsJgAJyfXOT7aNZULCDMOYhctlzI5kXOxw7vE64/edit#gid=899132401)
8. Documentation ~automatique : [storybook](https://storybook.js.org/)
9. [Liste de liengs > Optimisation du Responsive](https://docs.google.com/spreadsheets/d/1COXPrsJgAJyfXOT7aNZULCDMOYhctlzI5kXOxw7vE64/edit#gid=1584040677)

---

## Credits

Masamune / Maxime Chevasson
