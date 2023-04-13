# CSS

## Checklist

1. Linted
2. Virer le css inutilisé, article [dev.to](https://dev.to/dailydevtips1/chrome-find-unused-code-3g9c)
3. Concaténer les librairies externes
4. Minifier
5. Si pas trop lourd > injection inline
6. .htaccess inline security (SHA-256) (XSS prevention)
7. Vérifier que des styles n'ont pas sautés en cas de mise en place d'optimisations

## Bonnes pratiques

1. Jeter un coup d'oeil du côté du *Critical CSS*
   1. Y'a moyen de l'automatiser maintenant, mais gaffe des fois ça fait sauter le design
2. BEM, OOCSS, Smacss (site ok en http pas s), [knacss](https://www.knacss.com/)
3. Atomique
4. Pas plus de 2 niveaux de classes
5. Utilisation de variables pertinentes
