# Gestion des commandes

## **Creation d'une commande**

La Creation d'une commande s'effectue lorsqu' un formulaire valide de type commande est soumis.

Une **commande** est lié a un **client** qui est lui meme lié a une **listing prix** ainsi qu'a des données de facturation tel que l'adresse de facturation, le franco, la TVA et la comptabilisation de l'ecotaxe si c'est un client Francais etc. (voir [Gestion des clients](/orders_and_delivery/clients.md) et [Gestion des prix](/orders_and_delivery/prices.md) pour plus d'informations)

**Par consequent la premiere etape de la creation d'une commande est la selection d'un client.**

L'adresse de livraison de la commande peux etre selectionner parmis les adresses de livraison lié au client ou peux etre modifié a la main, de meme pour les autres informations de livraison (ex: *mode de livraison, date de livraison min/max*). Cette selection s'effectue exclusivement a la creation de la commande et ne poura etre modifié par la suite.

Enfin, les produit commandés sont a saisir via des lignes de saisie ou **line item**, a la selection du produit les autres champs sont automatiquement renseigné en fonction de la listing prix du client ou des infos du produit (voir [Gestion des produit](/orders_and_delivery/products.md) et [Gestion des prix](/orders_and_delivery/prices.md) pour plus d'info).

**Par consequent les seul information a renseigner lors de la saisi des line items sont le produit et le nombre de lot commandés**

*Ci dessous, saisie de commande avec 2 line items*
![Saisie de produits](/img/orders_and_delivery/orders/order_line_items.png)


## **Cycle de vie d'une commande**

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

* **En cours**: Si le statut de toutes ses line items est **En stock** par consequent la commande partira en preparation (voir [Gestion logistique](/orders_and_delivery/logistics.md)). Par consequent le stock sera **reservé**.
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

Une fois une commande modifié vous devais la faire "analyser" par l'application pour voir si elle est valide. Cette operation (re)check que chaque line item est valide suite a la modification et associe a la commande un nouveau statut parmis les 3 cités plus haut.

#### **3. Operation Split Commande**

Si la commande est **En attente** car elle contient des line items a la fois disponible et en arrivage il est possible de **spliter** la commande en deux commandes distincte (dans le cas ou le client a ete contacter et decide d'etre livré en deux commandes). Deux nouvelles commandes seront donc crée:

* Une premiere contenant les line items disponible physiquement et qui passera directement au statut **En cours**
* Un seconde contenant les line items en arrivage (qui lui sont reservé) et qui aura le statut **En attente**

#### **4. Operation Annuler Commande**

* Pour annuler une commande vous devez tout d'abord la **restocker** puis l'annulé. 
* L'annulation de commande est **ireversible**.
* Une commande **facturée** ne peux pas etre **annulée**

#### **5. Operation Facturer Commande**

* Seul les commandes en attente de livraison ou livrée peuvent etre facturée


### Preparation de la commande

Une fois que la commande est valide (le stock est physiquement disponible a l'entrepot et reservé pour la commande), la commande est **automatiquement** associée a un **preparateur** et passe en preparation. (voir [Gestion de la logistique](/orders_and_delivery/logistics.md))

### Livraison de la commande

Une fois que la commande est pres a etre livrer, une livraison est organiser en fonction de la commande et du client (voir [Gestion des livraison](/orders_and_delivery/delivery.md) )

## Diagram - cycle de vie d'une commande

![Cycle de vie commande](/img/orders_and_delivery/orders/order_lifecycle.png)