# Gestion des produits

**Seul les produits disponnible a la vente peuvent etre ajoutés a l'application de gestion des commandes et livraisons**
Pour la gestion des produits en cours de referencement voir section **[Gestion des fournisseurs](/)**

## Definitions Importante

* Le SKU identifie de facon **unique** un produit **avec son colisage**, par consequent **un SKU correspond a un lot de 1 ou plusieurs pieces repartit en 1 ou plusieurs colis**
* Le EAN identifie de facon **unique** un SKU
* Toutes les mesures et prix (*prix HT, ecotaxe, poids total*) d'un sku doivent **correspondre au nombre de pieces et de colis du sku**
* Dorénavant **Produit == SKU**

## Creation d'un produit

La creation d'un produit s'effectue via le **formulaire** Produit de la **section Produits**.
Un produit ne peut etre crée dans cette application seulement si il est disponible a la vente par consequent, son prix HT, prix de revient et son ecotax doivent etre precedement calculés et valide.
Toutes les données du produit qui ne sont pas *utiles* a la gestion de la commande et de la livraison (ex: *couleur, materiaux, dimension produit ...*) ne doivent pas etre renseignées lors de la creation du produit. Pour modifier/consulter les information technique/marketing du produit voir section **[Gestion du catalogue produit](/)**.

## Gestion des produits

Les entrées produits ne contiennent que des information static sur le produit cad celle qui ne changent pas dans le temps.
Par consequent, la gestion des produit se limite a la consultation de ceux ci exclusivement. Pour toute modification ou suppression contactez un administrateur.