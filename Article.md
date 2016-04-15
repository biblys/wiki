L'entité **Article** représente un produit abstrait disponible sur votre site, le plus souvent un livre (à la différence de l'entité [[Item]] qui représente un objet concret) avec les informations bibliographiques liées.

## Propriétés

* `article.authors` : la liste des auteurs, séparés par des virgules
* `article.contents` : le sommaire de couverture (format HTML)
* `article.ean` : le code EAN (sans tiret)
* `article.id` : l'identifiant unique du livre dans la base
* `article.isbn`: le code ISBN pour un livre (au format ISBN-13)
* `article.summary` : la quatrième de couverture du livre (format HTML)
* `article.title` : le titre de l'article

## Méthodes

### `article.has(property)`

Permet de tester la présence de la propriété `property` pour cet article.

```twig
{% if article.has('summary') %}
	<h2>Résumé du livre</h2>
	{{ article.summary }}
{% endif %}
```