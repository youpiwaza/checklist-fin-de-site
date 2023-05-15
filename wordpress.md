# WordPress

## 🔌 Plugins recommandés, simplement

1. 💾 `All in one wp migration`
   1. *~One clic savegarde & restauration*
   2. Particulièrement efficace pour la base de données
2. 🔒️ `Akismet anti spam`
   1. *Eviter le gros des spams de commentaires & mails*
   2. 🔧 & création compte & installation clé API
3. ⚡️ `Converter for Media` Par matt plugins
   1. *Affiche les images en webp, sans niquer tout le dossier médias*
4. ⚡️💄 `Reduce Unused CSS Solution with Critical CSS For WP`
   1. *Met en place du critical css de manière automatique*
   2. 🚨 mais peut faire sauter
5. 🔒️ `WordFence`
   1. *Sécurité*
   2. 🔧🛡️🔥 Configurer firewall
   3. 🔧📡 Scan & appliquer recos
6. 🧹 `WP-Optimize` Par David Anderson, Ruhani Rabin, Team Updraft
   1. *Optimisation de la base de données*, entre autre (virer transients, etc.)
7. ⚡️ More speed ~~more dakka~~
   1. `WP Fastest Cache`
      1. Plugin de cache complet
      2. Forcer la mise en cache après activation `your-site.com/?action=wpfastestcache&type=preload`
   2. ~~`Hummingbird – Optimize Speed, Enable Cache, Minify CSS & Defer Critical JS`~~
      1. Différer chargement ressources
      2. 🚨 mais peut faire sauter
   3. ~~`LiteSpeed Cache`~~
      1. Manque des trucs (headers, etc.)
8. 🔒️ `WPS Hide Login`, par Par WPServeur, NicolasKulka, wpformation
   1. *Sécurité* / Changer l'url de login
9. 🤖 sitemap.xml automatique

## Checklist

1. Si hebergement ovh > [config .htaccess](https://help.ovhcloud.com/csm/fr-web-hosting-htaccess-wordpress?id=kb_article_view&sysparm_article=KB0056291)
2. 💬 Informations du site posées via l'administration WordPress
   1. Réglages > Général
   2. Apparence > Logo
   3. Thème > Favicon
   4. Médias > Tailles fixées
   5. 🚨 Même si cela n'apparaît pas explicitement sur le site souvent ça ressort dans les moteurs de recherche
3. 🖼️ Médias
   1. Ajout des title
   2. Ajout des alt
4. 💪 Optimisations à la maing via thème enfant
   1. Defer JS
   2. Pré-charger polices gougeul
      1. CSS > font-display > maj url google font dans theme &display=swap
5. Passer les mise à jour en automatique, mineures uniquement
6. 🔥🔌 Supprimer les plugins inutiles
7. 🔥 Supprimer les thèmes inutiles
8. Vérifier les menus
9. 👨‍⚕️ Santé du site
   1. 🚨 Laisser tourner, l'analyse n'est pas instantanée
10. Vérifier API REST `/wp-json`
    1. Si KO vérifier compatibilité plugins
11. ⚡️🔌 Plugin de cache ~`WP Fastest Cache`
12. ♻️ Penser à vider le cache à chaque modif
    1. Vérifier la console
    2. Un petit coup de pagespeed insight ne fait pas de mal non plus
13. Vérifier le `.htaccess`
    1. Après mise à jour des permaliens
    2. Après installation d'un plugin de cache
14. 🧹 Ti coup de WP-Optimize avant sauvegarde
    1. D'abord virer les tables inutiles (2eme onglet) avant d'optimiser
15. 💾 Sauvegarde du site / export aucazou
    1. Noter la version du site
    2. Copie des fichiers racine & `wp-content/`
    3. Export de la base de données ~blog masamune > Bonne pratiques pour la gestion de la base de données #export
    4. Plugin All in one wp migration
       1. Export BDD uniquement, permet de réimporter par fichier si poids pas lourd
    5. 🔥 Supprimer plugin
       1. Noter version du plugin lors de l'export
       2. On le ré-installe au besoin

## Bonnes pratiques

1. Masquer la version de WordPress en publique
2. Utilisateurs
   1. Mots de passes **ET noms de comptes** aléatoires 🔀
      1. Identifiants utilisateurs : plus de 40 caractères, pas de caractères spéciaux
      2. Mots de passe
         1. plus de 50 caractères
         2. Comprenant **certains** caractères spéciaux `! ? % ^ & ) /`
         3. 💥 Mais surtout pas `$ ' "`
      3. Mettre à jour nom d'affichage
3. 🔒️ Sécurité
   1. plugins 'tout en un'
   2. firewall
   3. anti brute force
   4. Changer l'url de connexion avec plugin `WPS Hide Login`
      1. Plus de `wp-admin/`
      2. Plus de `wp-login.php`
      3. Ajouter règle wordpress ban ip automatique si ça tape sur l'une de ces deux urls
4. WP-CLI

### 🧹 Maintenance, à minima ♻️ tous les 6 mois

1. Site
   1. Sauvegarder avant de goyer, au cas ou
      1. Passer les modifications sur un domaine dev c'est encore mieux
         1. Possibilité de [changer l'url du site via wp-config.php](https://wordpress.org/documentation/article/changing-the-site-url/) maintenant, plus obligé de passer un script sur la BDD pour changer les urls en dur
   2. Nettoyer la base de données
   3. Mettre à jour les versions majeures
      1. WordPress
      2. Thème
      3. Plugin
   4. Virer `/wp-content/upgrade` et autres joyeusetés
   5. Nettoyer la base de données
   6. Vider le cache
   7. 📌 Testay putaing
2. 🔒️ Changer les mots de passe, voir les noms d'utilisateurs
3. Maj hébergement / serveur
   1. 🚨 Peut clairement faire tomber le site, je reco de tester avant sous 🐳 `docker` ou `VM`
   2. Régénérer Certificats SSL / HTTPS
   3. Maj de la version de PHP
   4. Maj de la version de la base de données
4. Checker les résultats google analytics ou alternative
   1. Mettre en avant les articles / pages qui marchent le mieux
5. Vérifier les liens morts
    1. Y compris **vos** liens qui pointent vers les liens mort > remplacer ou retirer
