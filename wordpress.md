# WordPress

## Checklist

1. 💬 Informations du site posées
   1. Réglages > Général
   2. Apparence > Logo
   3. Thème > Favicon
   4. 🚨 Même si cela n'apparaît pas explicitement sur le site souvent ça ressort dans les moteurs de recherche
2. 🖼️ Médias
   1. Ajout des title
   2. Ajout des alt
3. 💪 Optimisations à la maing via thème enfant
   1. Defer JS
   2. Pré-charger polices gougeul
      1. CSS > font-display > maj url google font dans theme &display=swap
4. 🔌 Plugins usuels
   1. sitemap.xml automatique
   2. `Akismet anti spam`
      1. & création compte & installation clé API
   3. `Converter for Media`
      1. Affiche les images en webp *sans niquer tout le dossier médias*
   4. Optimisation de la base de données `WP-Optimize`
   5. Sécurité `WordFence`
      1. Scan & appliquer recos
   6. `Reduce Unused CSS Solution with Critical CSS For WP`
      1. Met en place du critical css de manière automatique
      2. 🚨 mais peut faire sauter
   7. `Hummingbird – Optimize Speed, Enable Cache, Minify CSS & Defer Critical JS`
      1. Différer chargement ressources
5. Passer les mise à jour en automatique, mineures uniquement
6. 🔥🔌 Supprimer les plugins inutiles
7. 🔥 Supprimer les thèmes inutiles
8. Vérifier les menus
9. 👨‍⚕️ Santé du site
10. Vérifier API REST `/wp-json`
    1. Si KO vérifier compatibilité plugins
11. ⚡️🔌 Plugin de cache ~`WP Fastest Cache`
      1. 🚨 Je ne recommande pas W3 Total Cache, souvent des trucs sautent
12. ♻️ Penser à vider le cache à chaque modif
    1. Vérifier la console
    2. Un petit coup de pagespeed insight ne fait pas de mal non plus
13. Vérifier le `.htaccess`
    1. Après mise à jour des permaliens
    2. Après installation d'un plugin de cache
14. 💾 Sauvegarde du site / export aucazou
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
   4. Changer l'url de connexion
      1. Plus de `wp-admin/`
      2. Plus de `wp-login.php`
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
