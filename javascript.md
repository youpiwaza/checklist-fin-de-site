# Javascript

## Checklist

1. Charger en fin de fichier HTML
   1. Attribut `async` / `defer` ou je sais plus, cf. pagespeed insights
2. Linted
3. Concaténer les librairies externes
   1. Webpack ou autre
4. Minifier
5. Si pas trop lourd > injection inline
6. .htaccess inline security (SHA-256) (XSS prevention)
7. Utilisation d'évènements / écouteurs
    1. Ne pas oublier des les retirer
    2. Considérer l'utilisation de la librairie underscore
       1. [debounce](https://underscorejs.org/#debounce)
       2. [throttle](https://underscorejs.org/#throttle)

## Bonnes pratiques

1. (Typescript)
2. Remplacer JS par HTML/CSS pur
   1. [dev.to > You can create these elements without JavaScript](https://dev.to/adrianbdesigns/you-can-create-these-elements-without-javascript-525a)
3. Librairies d'optimisations de perfs de fonctions
   1. [underscore.js](https://underscorejs.org/)
   2. [lodash](https://lodash.com/)
4. Virer le js inutilisé, article [dev.to](https://dev.to/dailydevtips1/chrome-find-unused-code-3g9c)
