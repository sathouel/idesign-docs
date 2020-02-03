# Presentation de l'interface

## Vue d'ensemble

L'interface vous permet de creer, modifier et afficher des **entrées** de different **type** a travers les differentes sections de l'interface. Ci dessous un screenshot de l'interface.

![screenshot de l'interface](/img/orders_and_delivery/interface/interface_screenshot.png)

L'interface contient plusieurs **sections** (ex: *Produits, Clients, Stocks, etc..*) composer de **formulaire** et/ou de **rapports** (voir section Conceptes pour plus de details).

## Conceptes

Chaque section de l'interface peux regrouper (en fonction de vos autorisation):

* Des formulaires
* Des rapports

### Les rapports

Un **rapport** presente des données d'un type donné sous forme de liste ou de tableaux. Chaque ligne d'un rapport est appeler une **entrée** et correspond a une instance de type donné. (Voir exemple ci dessous).

### Les formulaires

Un **formulaire** permet de créer une entrée d'un type donné. Un formulaire contient differents champs qui peuvent etre obligatoire ou facultatif a la creation d'une entrée.

### Exemple

![Formulaire Produit](/img/orders_and_delivery/interface/form_product.png)

Ce screenshot presente le **formulaire** de type **Produit** qui permet donc de créer des entrées de type **Produit**. Ce formulaire possede des champs (ex: *sku, EAN, Nom, Colisage ...*) qui peuvent etre obligatoires (distingable par l'etoile rouge) ou facultatif (sans etoile ex: *Image*).
Par consequent pour creer une entrée de type Produit il faudra remplir au moin les champs obligatoire du **formulaire** Produit puis le soumettre. Le Formulaire peux renvoyer des erreur si jamais certaine conditions ne sont par remplit (ex: *le sku renseigné existe deja dans la base*).

![Rpport Produit](/img/orders_and_delivery/interface/rapport_product.png)

Ce screenshot presente le **rapport** de type **Produit** qui affiche les entrées de type **Produit** precedement crées via le **formulaire**. Il est possible de trier / filtrer les differentes entrées via leur attribut (en cliquant sur le nom de l'attribut en haut de chaque colone ou bien en utilisant la recherche en haut a droite). Il est possible d'avoir une vue detaillé d'une entrée en cliquant sur celle ci (voir screenshot ci dessous).

![Rapport detail Produit](/img/orders_and_delivery/interface/rapport_detail_product.png)
