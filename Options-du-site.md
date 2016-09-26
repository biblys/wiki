### active_stock (default: null)
Permet de définir le ou les emplacement(s) de stock actif(s). Si une valeur est entrée, seul les exemplaires dont l'emplacement est égale à cette valeur sont disponibles. Il est possible de préciser plusieurs emplacements séparés par une virgule.

### cgv_page (default: null)
Identifiant de la page des Conditions Générales de Vente. Si cette option est précisé, une case à cocher "Je reconnais avoir pris connaissance des conditions de vente" est affichée avec un lien pointant vers cette page, et devra être obligatoirement cochée pour pouvoir enregistrer une commande.

### closed (default: 0)
Si la valeur est 1, le site est en maintenance et n'est plus accessible, sauf pour les administrateurs identifiés.

### currency (default: EUR)
Permet de changer le sigle de la monnaie affichée sur le site.
Valeurs acceptées :
* `EUR`
* `FCFA`

### home (default: custom)
Permet de définir le comportement de la page d'accueil.
Valeurs acceptées :
* `custom` : affiche le template home.html.twig
* `posts` : affiche les dix derniers billets (template: home-posts.html.twig)
* `page:{id}` : affiche la page statique {id}
* `old_controller` : utiliser l'ancien controleur 

### isbn_checker_start (default: null)
Permet de définir la valeur de départ pour le générateur d'ISBN libres du catalogue éditeur. Doit être un code EAN à 13 chiffres sans tiret.

### minimum_virtual_stock (default: 3)
Nombre de livres en stock en dessous duquel une ligne apparaîtra en rouge sur
la page de gestion du stock virtuel.

### newsletter (default: 0)
Si la valeur est 1, l'abonnement à la newsletter est proposé au moment de
l'enregistrement d'une nouvelle commande.

### shipping_date (default: null)
Si précisé, ce texte apparaîtra avec pour titre "Date d'expédition" au moment
de la validation de la commande.

### show_elibrary (default: 0)
Afficher le lien vers "ma bibliothèque" dans le menu Axys

### special_offer_amount (default: 0) / special_offer_article (default: null)
Ces deux options permettent de créer une offre promotionnelle, valable uniquement pour l'achat d'articles physiques. Si le montant total des articles dans le panier de l'utilisateur est supérieur ou égale à `special_offer_amount`, l'article dont l'identifiant correspond à `special_offer_article` sera ajouté à la commande. 

### virtual_stock (default: 0)
Active le mode stock virtuel : un exemplaire est créé automatiquement si
aucun n'est disponible lors de l'ajout d'un article physique dans un panier.