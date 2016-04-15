Le modèle principal contient la structure HTML de la page et l'ensemble des éléments apparaissant sur tout votre site Biblys (en-tête, menu, pied de page, etc.)

C'est le seul modèle à ne pas être au format Twig. Il s'agit de simple HTML, avec toutefois des balises spécifiques qu'il faut absolument inclure pour permettre le bon fonctionnement de Biblys :

* `{PAGE_TITLE}` : le titre de la page, à inclure entre les balises `<title>`.
* `{CSS_CALLS}` : l'appel des fichiers CSS, à inclure dans la balise `<head>`.
* `{OPENGRAPH}` : les balises OpenGraph, à inclure dans la balise `<head>`.
* `{PAGE_CONTENT}` : le contenu de la page en cours, à inclure dans la balise `<body>`.
* `{JS_CALLS}` : l'appel des fichiers JavaScript, à inclure juste avant la balise fermante `</body>`.

Ainsi qu'une balise facultative, mais souvent utile :

* `{SITE_TITLE}` : le titre du site, souvent inclus dans l'en-tête du site.

Voici un exemple très simple de modèle principal avec les différentes balises :

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>{PAGE_TITLE}</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    {CSS_CALLS}
    {OPENGRAPH}
  </head>
  <body>
    <div id="menu">
  	  <!-- Menu -->
    </div>
    <div id="content">
  	  {PAGE_CONTENT}
    </div>
    <div id="footer">
  	  &copy {SITE_TITLE}
    </div>
    {JS_CALLS}
  </body>
</html>
```