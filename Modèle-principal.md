Le modèle principal contient la structure HTML de la page et l'ensemble des éléments apparaissant sur tout votre site Biblys (en-tête, menu, pied de page, etc.)

C'est le seul modèle à ne pas être au format Twig. Il s'agit d'un simple HTML, avec toutefois des variables spécifiques qu'il faut absolument inclure pour permettre le bon fonctionnement de Biblys.

## Variables

Ces variables sont obligatoires :

* `{PAGE_TITLE}` : le titre de la page, à inclure entre les balises `<title>`.
* `{CSS_CALLS}` : l'appel des fichiers CSS, à inclure dans la balise `<head>`.
* `{OPENGRAPH}` : les balises OpenGraph, à inclure dans la balise `<head>`.
* `{PAGE_CONTENT}` : le contenu de la page en cours, à inclure dans la balise `<body>`.
* `{JS_CALLS}` : l'appel des fichiers JavaScript, à inclure juste avant la balise fermante `</body>`.

Ces variables sont facultatives, mais souvent utiles :

* `{SITE_TITLE}` : le titre du site, souvent inclus dans l'en-tête du site ou le pied de page.
* `{cart_oneline}` : l'état du panier de l'utilisateur (nombre d'article et montant total)

## Exemple

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
    <div id="header">
      {SITE_TITLE}
    </div>
    <div id="menu">
  	  <!-- Menu -->
      {cart_oneline}
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