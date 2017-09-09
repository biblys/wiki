### active_stock (default: null)
Permet de définir le ou les emplacement(s) de stock actif(s). Si une valeur est entrée, seul les exemplaires dont l'emplacement est égale à cette valeur sont disponibles. Il est possible de préciser plusieurs emplacements séparés par une virgule.

### admin_entries (defaut: null)
Permet d'ajouter des entrées dans un menu personnalisé de l'interface d'administration sous la forme [{"name": "Nom de l'entrée", "url": "/pages/page", "icon": "icon"}]

### articles_per_page (default: 10)
Nombre d'articles à afficher par page.

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
* `articles` : affiche les cents derniers articles parus
* `posts` : affiche les dix derniers billets (template: home-posts.html.twig)
* `post_category:{id}` : affiche les dix derniers billets de la catégorie {id} (template: home-posts.html.twig)
* `page:{id}` : affiche la page statique {id}
* `rayon:{id}` : affiche les livres du rayon {id}
* `old_controller` : utiliser l'ancien controleur

### home_preview_image et home_preview_text (default: null)
Permet de définir une image et un texte qui seront utilisés pour la prévisualisation de la page d'accueil sur les réseaux sociaux (Twitter Cards et Facebook Open Graph).

### isbn_checker_start (default: null)
Permet de définir la valeur de départ pour le générateur d'ISBN libres du catalogue éditeur. Doit être un code EAN à 13 chiffres sans tiret.

### minimum_virtual_stock (default: 3)
Nombre de livres en stock en dessous duquel une ligne apparaîtra en rouge sur
la page de gestion du stock virtuel.

### publisher_filter (default: null)
Permet de n'afficher sur le site que les articles associés à un ou plusieurs éditeurs en entrant leurs identifiants, séparés par des virgules.

### name_for_check_payment (default: site_title)
Nom à l'afficher pour l'ordre des chèques sur la page de paiement. Si le paramètre n'est pas spécifié, le nom du site sera utilisé.

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

### weight_required (default: 0)
Si ce paramètre est spécifié, un exemplaire ne pourra être créé et ne pourra être ajouté au panier s'il a un poids inférieur à la valeur définie pour le paramètre.