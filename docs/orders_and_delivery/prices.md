# Gestion des prix

A chaque produit est associé lors de sa creation un **prix de revient**, un **prix de vente HT** et une **ecotaxe**.
Le prix de vente HT est un prix de vente par defaut cependant si nous voullons proposer a un client un prix negocier il sera possible de créer un **listing prix** a associer a ce client.

## Listing Prix

Un listing prix permet d'associer aux produit un prix de vente different de celui par defaut. Par la suite il peux etre associer a un ou plusieur client voir **[Gestion des clients](orders_and_delivery/clients.md)**.

Un **listing prix** peux etre de deux types differente:

1. Pourcentage de reduction appliqué a **tout les produits**
2. Prix personnalisé pour chaque produit

### Creation de Listing prix

Pour crée une nouvelle listing prix utilisez le formulaire de la section **Listing Prix**.
Donnez lui un nom **unique**, selectionnez le type de listing prix a créer ainsi que le pourcentage si necessaire.

Si vous créez une listing prix personnalisée, l appliquation copiera dans un priemier temps tous les prix par defaut dans cette listing prix, il vous faudra par la suite modifié **individuelement** le prix de chaque produit. voir section **Modification de Listing prix** plus bas.

![Listing Prix Formulaire](/img/orders_and_delivery/prices/form_pricelist.png)

### Modification de Listing prix

**Seul les listing prix personnalisé (type 2) peuvent etre modifiées**
