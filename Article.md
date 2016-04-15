L'entité **Article** représente un produit abstrait disponible sur votre site, le plus souvent un livre (à la différence de l'entité [[Item]] qui représente un objet concret) avec les informations bibliographiques liées.

## Propriétés

* `article.authors` : la liste des auteurs, séparés par des virgules
* `article.contents` : le sommaire de couverture (format HTML)
* `article.ean` : le code EAN (sans tiret)
* `article.id` : l'identifiant unique du livre dans la base
* `article.isbn` : le code ISBN pour un livre (au format ISBN-13)
* `article.summary` : la quatrième de couverture du livre (format HTML)
* `article.title` : le titre de l'article

## Méthodes

### article.has(property)

Permet de tester la présence de la propriété `property` pour cet article.

```twig
{% if article.has('summary') %}
	<h2>Résumé du livre</h2>
	{{ article.summary }}
{% endif %}
```

### article.hasCover()

Permet de tester la présence d'une image de couverture pour cet article.
Retourne un booléan (`true` ou `false`).

```twig
{% if article.hasCover() %}
  {{ article.getCoverTag()|raw }}
{% endif %}
```

### article.getCoverTag(options)

Retourne la couverture de l'article sous la forme d'une balise HTML (image et lien vers l'image haute résolution). L'argument options est un tableau qui peut prendre les propriété suivantes :

* `class` : la valeur de l'attribut `class` de la balise image (par défaut : aucun)
* `rel` : la valeur de l'attribut `rel` du lien (par défaut : aucun)
* `link` : l'url vers laquelle doit pointer le lien (par défaut : l'image en haute résolution)
* `size` la taille de l'image sous la forme `wXXX` pour fixer la largeur ou `hXXX` pour la hauteur (par défaut : pleine résolution).

```twig
article.getCoverTag({ class: 'cover', rel: 'lightbox', size: 'w300' });
```

générera le code HTML suivant :

```html
<a href="http://media.biblys.fr/book/05/13005.jpg" rel="lightbox">
  <img src="http://media.biblys.fr/book/05/13005-w300.jpg" class="cover" alt="Titre du livre">
</a>
```

### article.getAvailableItems()

Retourne un tableau d'entité [[Item]] représentant les exemplaires en stock pour cet article.

```twig
{% for item in article.getAvailableItems() %}
  {{ item.getCartButton('Ajouter au panier')|raw }}
  {{ item.selling_price|currency(true)|raw }}
{% endfor %}
```

### article.getCheapestAvailableItem()

Retourne une unique entité [[Item]] représentant l'exemplaire en stock le moins cher.

```twig
{% set item = article.getCheapestAvailableItem() %}
{{ item.getCartButton('Ajouter au panier')|raw }}
{{ item.selling_price|currency(true)|raw }}
```