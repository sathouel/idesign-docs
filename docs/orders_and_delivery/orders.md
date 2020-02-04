# Gestion des commandes

## Creation d'une commande

La Creation d'une commande s'effectue lorsqu' un formulaire valide de type commande est soumis.

Une **commande** est lié a un **client** qui est lui meme lié a une **listing prix** ainsi qu'a des données de facturation tel que l'adresse de facturation, le franco, la TVA et la comptabilisation de l'ecotaxe si c'est un client Francais etc. (voir [Gestion des clients](orders_and_delivery/clients.md) et [Gestion des prix](orders_and_delivery/prices.md) pour plus d'informations)

**Par consequent la premiere etape de la creation d'une commande est la selection d'un client.**

L'adresse de livraison de la commande peux etre selectionner parmis les adresses de livraison lié au client ou peux etre modifié a la main, de meme pour les autres informations de livraison (ex: *mode de livraison, date de livraison min/max*). Cette selection s'effectue exclusivement a la creation de la commande et ne poura etre modifié par la suite.

Enfin, les produit commandés sont a saisir via des lignes de saisie ou **line item**, a la selection du produit les autres champs sont automatiquement renseigné en fonction de la listing prix du client ou des infos du produit (voir [Gestion des produit](orders_and_delivery/products.md) et [Gestion des prix](orders_and_delivery/prices.md) pour plus d'info).

**Par consequent les seul information a renseigner lors de la saisi des line items sont le produit et le nombre de lot commandés**

*Ci dessous, saisie de commande avec 2 line items*
![Saisie de produits](/img/orders_and_delivery/orders/order_line_items.png)


## Cycle de vie d'une commande

A la creation d'une commande, l'application associe a la commande un **statut**. **Apres sa creation** une commande peux avoir **3 statuts possible**:

1. **En cours**
2. **En attente**
3. **Invalide**

Le statut d'une commande est difinit par rapport au statut de ses **line items**. En effet, chaque line item ou ligne de saisie (voir exemple dans la section Creation de commande) peux avoir **4 statuts possible**

1. **En stock**: le produit de la line item est **disponible dans la quantité demandée en entrepot**. Autrement dit la quantité demandé est inferieur au stock **disponible en entrepot** du produit.
2. **En arrivage**: La quantité demandé est inferieur au stock en **arrivage disponible** du produit mais superieur au stock **disponible en entrepot**.
3. **Hybride**: Seul la somme des stock disponible en entrepot et en arrivage disponible est superieur a la quantitée demandée
4. **Invalide**: Il n'y a pas assez de quantitée en stock disponible ou/et en arrivage disponible.

Par consequent apres creation/modification d'une commande son statut sera:

* **En cours**: Si le statut de toutes ses line items est **En stock** par consequent la commande partira en preparation (voir [Gestion logistique](orders_and_delivery/logistics.md)). Par consequent le stock sera **reservé**.
* **En attente**: Si le statut de ses line items est un melage de **En cours** et **En arrivage**. Dans ce cas il faudra contacter le client pour voir si il prefere attendre l'arrivage, annuler la commande ou bien separer/**spliter** la commande en deux. Dans ce cas egalement le stock sera **reservé**.
* **Invalide**: Le statut d'au moin une line item est **Hybride** ou **Invalide**. Par consequent **les stock de la commande ne seront pas reservés**, le client devra etre contacter pour annuler ou modifier la commande en fonction des stocks disponible.

*Ci dessous un diagram recapitulatif*

![Statut commande 1](/img/orders_and_delivery/orders/order_status_1.png)

### Operation sur commande

Nous avons vue plus haut que dans certain cas, nous devons modifié une commande pour differente raisons. Pour ce faire vous pouvez interagir avec les entrées de type commande sur les differents rapports de la section Commandes via **5 operations**:

#### **1. Operation Restock**

Dans le cas ou le statut de la commande n'est pas **Invalide**, la creation de la commande a automatiquement **reservé** les stocks. Par consequent, si vous voullez modifier ou bien annulé la commande vous devez **restocker** les articles precedement **reservés**. Le bouton **Restock** permet donc de restocker les articles reservé d'une commande.

**Toute commande non restockée ne poura JAMAIS etre modifiée ou annulée**

#### **2. Operation Process Commande**

Une fois une commande modifié vous devais la faire "analyser" par l'application pour voir si elle est valide.



<!-- Le Diagram ci dessous presente le cycle de vie d'une commande.

![Cycle de vie commande](/img/orders_and_delivery/orders/order_lifecycle.png) -->



## Modifitcation d'une commande