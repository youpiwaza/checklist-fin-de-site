# Checklist de fin de site

Une TODO liste de vérifications à effectuer avant de passer un site en ligne.

Il n'y aura pas forcément l'ensemble des liens, il s'agit plutôt d'une description exhaustive, après appliquer la méthode SSLDDC.

À noter que la liste est über longue après plus de 12 ans à galérer ; à minima passer un coup de [pagespeed insight](https://pagespeed.web.dev/?hl=fr) pour virer le plus gros.

## Utilisation recommandée

1. Cloner ce repo pour chaque projet
2. Valider & cocher ✅ chaque point pertinent

## Sommaire

- [Checklist de fin de site](#checklist-de-fin-de-site)
  - [Utilisation recommandée](#utilisation-recommandée)
  - [Sommaire](#sommaire)
  - [Projet git](#projet-git)
    - [Créer un README.md propre](#créer-un-readmemd-propre)
    - [Communauté](#communauté)
  - [Optimisations du code](#optimisations-du-code)
    - [Robots.txt reco pour WordPress](#robotstxt-reco-pour-wordpress)
  - [Optimisations du projet](#optimisations-du-projet)
    - [Images \& vidéos](#images--vidéos)
  - [Validateurs +- en ligne](#validateurs---en-ligne)
  - [Optimisations côté serveur](#optimisations-côté-serveur)
  - [Listes dédiées aux technologies](#listes-dédiées-aux-technologies)
  - [Liste de ressources supplémentaires](#liste-de-ressources-supplémentaires)
  - [Credits](#credits)

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

### Robots.txt reco pour WordPress

À partir des ~5 articles populaires en 2023

```txt
User-agent: *
Allow: /wp-admin/admin-ajax.php
Disallow: /wp-admin/
Disallow: /wp-content/uploads/wpo-plugins-tables-list.json
Disallow: /wp-login.php
Disallow: /wp-includes/
Disallow: /readme.html
Disallow: /refer/
Disallow: /?s=/
Disallow: /search/

Sitemap: https://blog-new.masamune.fr/sitemap.xml
Sitemap: https://blog-new.masamune.fr/sitemap.rss
```

---

## Optimisations du projet

1. Virer les fichiers inutilisés
2. Mise en place d'une page 404 propre
3. SEO
   1. Correcteur orthographe
   2. Balises title pour chaque page
   3. Page Plan du site
   4. [Vérifier l'absence de liens morts](https://www.deadlinkchecker.com/website-dead-link-checker.asp)
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
2. [Scan Problèmes, SEO, 100k trucs](https://geekflare.com/tools/toolbox)
3. Standards HTML > [W3C validator](https://validator.w3.org/)
4. Sécurité
   1. [Security headers](https://securityheaders.com/)
5. SEO
   1. ~google crawler / [totheweb > search engine simulator](https://totheweb.com/learning_center/tools-search-engine-simulator/)
      1. Fait ressortir les mots clés, recos d'utilisation de balises
6. Accéssibilité (tags dédiés, contrastes, etc.)
   1. [AccessiBe > Scan](https://accessibe.com/accessscan)
7. Responsive
   1. Inspecteur du navigateur lel
   2. avec inscription : [Lambda test](https://www.lambdatest.com/)
8. Ecologie (.. ui ui)
   1. Empreinte carbone de ton site [websitecarbon.com](https://www.websitecarbon.com/)
9. Validateur de robots.txt autre que google console [websiteplanet](https://www.websiteplanet.com/fr/webtools/robots-txt/)

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
   3. Sécurité / Spam
      1. 📝 Possibilité d'ajouter ces entrées dans les DNS d'ovh maintenant
      2. SPF
         1. 📝 [Doc](https://dmarcadvisor.com/fr/creer-un-enregistrement-spf/)
         2. ~~`blog IN TXT "v=spf1 a mx ip4:169.169.169.169 ip6:2001:169:169::169 -all"`~~
            1. sous domaine, autoriser ip associée au domaine + spécifier ip en dur & empécher tout le reste
         3. Reco OVH  si utilisation de leur mailing `"v=spf1 include:mx.ovh.com ~all"`
         4. [Test](https://dmarcadvisor.com/fr/spf-check/)
      3. DKIM
         1. Pas possible sur heberg mutualisé
      4. DMARC
         1. 📝 [Doc](https://dmarcadvisor.com/fr/qu-est-ce-que-dmarc/)
         2. [Générateur](https://dmarcadvisor.com/dmarc-generator/)
      5. OVH Manager > hébergement > scripts emails > destinataire
   4. [Liste de liens > Emails](https://docs.google.com/spreadsheets/d/1COXPrsJgAJyfXOT7aNZULCDMOYhctlzI5kXOxw7vE64/edit#gid=222850098)
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
10. Ai1SEO > [Article guide ref nat 2023](https://aioseo.com/ultimate-wordpress-seo-guide/)

---

## Credits

Masamune / Maxime Chevasson
