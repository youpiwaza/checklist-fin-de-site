# WordPress

## 🔌 Plugins recommandés, simplement

1. 🔒️ `Akismet anti spam` Par Automattic - Anti Spam Team
   1. *Eviter le gros des spams de commentaires & mails*
   2. 🔧 & création compte & installation clé API
2. `All in One SEO Pack` Par L’équipe All in One SEO
3. 💾 `All in one wp migration` Par ServMask
   1. *~One clic savegarde & restauration*
   2. Particulièrement efficace pour la base de données
   3. Vérifier que les plans de sites sont activés
4. `Complianz – GDPR/CCPA Cookie Consent`
   1. *Analyse automatique des cookies & génération RGPD, par pays*
5. ⚡️ `Converter for Media` Par matt plugins
   1. *Affiche les images en webp, sans niquer tout le dossier médias*
6. `MonsterInsights – Google Analytics Dashboard for WordPress (Website Stats Made Easy)` Par MonsterInsights
   1. *Connexion à google analytics et quelques autres améliorations SEO*
7. ⚡️💄 `Reduce Unused CSS Solution with Critical CSS For WP` Par Magazine3
   1. *Met en place du critical css de manière automatique*
   2. 🚨 mais peut faire sauter
   3. 👷 Vider le cache si plugin déjà en place avant de tester
8. `Simple Sitemap` Par David Gwyer
   1. *Sitemap HTML généré automatiquement via shortcodes, possibilité de configuration*
9. 🔒️ `WordFence`
   1. *Sécurité*
   2. 🔧🛡️🔥 Configurer firewall > All Firewall Options
      1. Allowed IP > Ajouter la sienne, au cazou
      2. Immediately block the IP of users who try to sign in as these usernames > "admin"
   3. 🔧📡 Scan & appliquer recos
   4. 🔧🔒️ Login page > enable recaptcha
10. 🧹 `WP-Optimize` Par David Anderson, Ruhani Rabin, Team Updraft
    1. *Optimisation de la base de données*, entre autre (virer transients, etc.)
11. ⚡️ More speed ~~more dakka~~
    1. `WP Fastest Cache`
       1. Plugin de cache complet
       2. ⚡️⚡️⚡️ Forcer la mise en cache après activation `your-site.com/?action=wpfastestcache&type=preload`
    2. ~~`Hummingbird – Optimize Speed, Enable Cache, Minify CSS & Defer Critical JS`~~
       1. Différer chargement ressources
       2. 🚨 mais peut faire sauter
    3. ~~`LiteSpeed Cache`~~
       1. Manque des trucs (headers, etc.)
12. 🔒️ `WPS Hide Login`, par Par WPServeur, NicolasKulka, wpformation
    1. *Sécurité* / Changer l'url de login
    2. WordFence > Firewall > All Firewall Options > Immediately block IPs that access these URLs > `/wp-login.php`
13. 🤖 sitemap.xml automatique
14. 🔒️ En fin d'installations, aller sur la page des extensions et activer l'auto-update
15. En fin d'installations, lancier Complianz, que les cookies des plugins soient en place

## Checklist

1. Si hebergement ovh > [config .htaccess](https://help.ovhcloud.com/csm/fr-web-hosting-htaccess-wordpress?id=kb_article_view&sysparm_article=KB0056291)
2. 💬 Informations du site posées via l'administration WordPress
   1. Réglages > Général
   2. Apparence > Personnaliser > Paramètres généraux > Identité du site > Logo
   3. Admin > Divi > Options du thème > Général > Logo
   4. Thème > Favicon
   5. Admin > Réglages > Médias > Tailles fixées
   6. 🚨 Même si cela n'apparaît pas explicitement sur le site souvent ça ressort dans les moteurs de recherche
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
9. 👨‍⚕️ Admin > Outils > Santé du site
   1. 🚨 Laisser tourner, l'analyse n'est pas instantanée
10. Vérifier API REST `/wp-json`
    1. Si KO vérifier compatibilité plugins
11. Vérifier le `.htaccess`
    1. Après mise à jour des permaliens
    2. Après installation d'un plugin de cache
    3. 💾 Backup local
12. 🧹 Ti coup de WP-Optimize avant sauvegarde
    1. D'abord virer les tables inutiles (2eme onglet) avant d'optimiser

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
3. WP-CLI

### Robots.txt reco pour WordPress

À partir des ~5 articles populaires en 2023

Possibilité de passer par le plugin all in one seo > outils > editeur robots.txt

```txt
User-agent: *
Allow: /wp-admin/admin-ajax.php
Disallow: /wp-admin/
Disallow: /wp-content/uploads/wpo-plugins-tables-list.json
Disallow: /wp-login.php
Disallow: /wp-includes/
Disallow: /readme.html
Disallow: /refer/
Disallow: /*/?s=*
Disallow: /search/
Disallow: /*/?query*
Disallow: /*/?cst*
Disallow: /author/

Sitemap: https://masamune.fr/sitemap.xml
Sitemap: https://masamune.fr/sitemap.rss
```

---

## Thème Divi / Thème Enfant

Faire un thème enfant afin de corriger certains trucs.

### Styles & Google web fonts

Chargement des polices Google web fonts en self host

1. Inspecter la vitrine du site afin d'identifier les polices utilisées, ainsi que leurs **poids** `font-weight`
2. Se servir du [Helper heroku](https://gwfh.mranftl.com/fonts)
   1. Télécharger les fichiers de polices
   2. Les ajouter au dossier du thème enfant (et upload)
   3. Ajuster le code fourni vers chemin vers les ressources (inclus dans le helper)
   4. Ajouter au style.css

---

### JS en général

Surcharger Thème enfant Divi > `functions.php`

```php
<?php
// * ⚡️🔌 Optimisation des chargements des scripts, avec async/defer
//          L'attribut defer va permettre d'exécuter les scripts dans l'ordre donné
//              dès la fin du chargement de la page
//          au contraire de async qui va exécuter les scripts dès que ceux-ci sont prêts
//  @see    https://thibautsoufflet.fr/blog/ajouter-les-attributs-defer-et-async-aux-scripts-wordpress/
//              Edit : 🔧 script corrigé

// * Add async
function add_async_attribute($tag, $handle) {
    // @use : Ajouter le nom du script ici
    $scripts_names = [];
    
    if ( !in_array($handle, $scripts_names) )
    return $tag;

    return str_replace( ' src', ' async src', $tag );
}
add_filter('script_loader_tag', 'add_async_attribute', 10, 2);



// * Add defer
function add_defer_attribute($tag, $handle) {
    // @use : Ajouter le nom du script ici
    $scripts_names = ['gtag-script-load', 'google-recaptcha', 'my_custom_script_load'];

    if ( !in_array($handle, $scripts_names) )
        return $tag;
    
    return str_replace( ' src', ' defer src', $tag );
}
add_filter('script_loader_tag', 'add_defer_attribute', 10, 2);



// ---



// * 🔌 Charger un Google Tag Manager / Google Analytics
add_action( 'wp_enqueue_scripts', 'gtag_script_load' );
function gtag_script_load(){
    wp_enqueue_script( 'gtag-script-load', 'https://www.googletagmanager.com/gtag/js?id=G-XXX' );
}



// * 🔌 Charger le script de google recaptcha de manière propre
add_action( 'wp_enqueue_scripts', 'script_load_google_recaptcha' );
function script_load_google_recaptcha() {
    wp_enqueue_script('google-recaptcha', 'https://www.google.com/recaptcha/api.js');
}



// * 🔌 Charger un fichier javascript personnalisé
add_action( 'wp_enqueue_scripts', 'my_custom_script_load' );
function my_custom_script_load(){
    wp_enqueue_script( 'my-custom-script', get_stylesheet_directory_uri() . '/max.js' );
}



// * Changer les url des projets et catégories projets avec divi
//          `masamune.fr/project/bp-projet/` > `masamune.fr/projet/bp-projet/`
function et_projects_custom_slug( $slug ) {
    $slug = array( 'slug' => 'projet' );
    return $slug;
}
add_filter( 'et_project_posttype_rewrite_args', 'et_projects_custom_slug', 10, 2 );

//          `masamune.fr/category_project/bp-projet/` > `masamune.fr/categorie-projet/bp-projet/`
add_filter( 'register_taxonomy_args', 'change_taxonomies_slug', 10, 2 );
function change_taxonomies_slug( $args, $taxonomy ) {
    if ( 'project_category' === $taxonomy ) {
        $args['rewrite']['slug'] = 'categorie-projet';
    }
    return $args;
}



// * ⚡️ Virer la barre d'admin du haut pour l'ensemble des utilisateurs
// add_filter( 'show_admin_bar', '__return_false' );



// * ⚡️ Désactiver heartbeat
add_action( 'init', 'stop_heartbeat', 1 );
function stop_heartbeat() {
    wp_deregister_script('heartbeat');
}



// ! Pagespeed insights
//      L'attribut [user-scalable="no"] est utilisé dans l'élément <meta name="viewport">, ou l'attribut [maximum-scale] est inférieur à 5.
//      @see    https://help.elegantthemes.com/en/articles/2190905-how-to-enable-pinch-to-zoom-on-mobile
function remove_my_action() {
    remove_action('wp_head', 'et_add_viewport_meta');
}

function custom_et_add_viewport_meta(){
    echo '<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=6.0, user-scalable=1" />';
}

add_action( 'init', 'remove_my_action');
add_action( 'wp_head', 'custom_et_add_viewport_meta' );
?>

```

---

### Utilisation de la galerie > ajout de l'accessibilité

Charger un fichier js depuis le thème enfant, `functions.php`

```php
<?php
// * 🔌 Charger un fichier javascript personnalisé
add_action( 'wp_enqueue_scripts', 'my_custom_script_load' );
function my_custom_script_load(){
    wp_enqueue_script( 'my-custom-script', get_stylesheet_directory_uri() . '/max.js' );
}
?>
```

Ajout en javascript dynamique

```js
// * Gallery accessibility > Adding Aria labels
//      @see        https://dequeuniversity.com/rules/axe/4.7/link-name
//      @see        https://divi.help/threads/adding-accessibility-attributes-to-slider.2990/
function onLoad(){
    const previousLabel = "Précédent";
    const nextLabel     = "Suivant";
    
    // Get the elements
    let arrowsPrev = document.getElementsByClassName('et-pb-arrow-prev');
    let arrowsNext = document.getElementsByClassName('et-pb-arrow-next');
    // console.log(arrowsPrev);

    // Set the aria-label attributes
    for (let arrowPrev of arrowsPrev) {
        arrowPrev.setAttribute('aria-label', previousLabel);
    }
    for (let arrowNext of arrowsNext) {
        arrowNext.setAttribute('aria-label', nextLabel);
    }
}

window.addEventListener("load", onLoad);
```

---

### 💾 Sauvegarde du site / export aucazou

1. Noter la version du site
2. Copie des fichiers racine & `wp-content/`
   1. Virtuellement pas besoin de `wp-admin/` ni `wp-includes/`, préférer installation propre
   2. Préférer récupérer manuellement les dossiers à l'intérieur de `wp-content/`
      1. Exclure cache, logs, upgrade, etc.
      2. Récupérer principalement `themes/`, `plugins/`, `uploads/`
3. Export de la base de données [~blog masamune > Bonne pratiques pour la gestion de la base de données #export](https://blog.masamune.fr/dev-et-prog/bonne-pratiques-gestion-base-de-donnees/)
4. Plugin All in one wp migration
   1. Export BDD uniquement, permet de réimporter par fichier si poids pas lourd
5. 🔥 Supprimer plugin
   1. Noter version du plugin lors de l'export
   2. On le ré-installe au besoin
6. Si sauvegarde sur github, utiliser un `.gitignore` [adapté](https://github.com/youpiwaza/base-repository-github/blob/main/.gitignore)

---

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
