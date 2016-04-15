L'entité **Item** représente un objet concret, comme un exemplaire physique dans votre stock ou un exemplaire numérique dans la bibliothèque d'un utilisateur. **Item** est toujours lié à une entité [[Article]] qui contient les données bibliographiques liées (titre, auteur, éditeur, etc.).

## Propriétés

* `item.id` : l'identifiant unique de l'item dans la base
* `item.selling_price` : le prix de vente TTC en centimes

## Méthodes

### item.getCartButton(text)

Retourne le code HTML du bouton d'ajout au panier pour cet exemplaire. L'argument `text` permet de préciser le texte du bouton (par défaut, il y a juste une icône).

```twig
{{ item.getCartButton('Ajouter au panier') }}
```