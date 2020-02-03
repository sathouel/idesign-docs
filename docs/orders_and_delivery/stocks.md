# Gestion des stocks

Le stock d'un produit peux avoir 4 status differents:

1. **Disponible**: Le produit **est physiquement disponible** en entrepot et **disponible a la vente**
2. **Reservé**: Le produit **est physiquement disponible** en entrepot mais **non disponible a la vente**
3. **En arrivage disponible**:  Le produit **n'est pas disponible physiquement** en entrepot mais **disponible a la vente**
4. **En arrivage reservé**: Le produit **n'est pas disponible physiquement** en entrepot et **non disponible a la vente**

Ci dessous un screenshot du rapport des stocks.
![Rapport Stock exemple 1](/img/orders_and_delivery/stocks/stocks_rapport_1.png)

## Creation de stock

Lorsqu'un produit est créer la creation de son stock est **automatique** elle ne sera donc jamais faite par un utilisateur. A sa creation le stock du produit est a zero (valeurs 0 dans les quatres etats voir exemple ci dessus).

## Modification de stock

Pour modifié de stock d'un produit vous devez cree un **ajustement de stock** puis l'excecuter.

Pour cree un ajustement il faut soummetre un formulaire valide de type **ajustement de stock** dans la sections **stocks**
Un Ajustement de stock peux etre de 5 type differents:

1. **Arrivage**: Reception d'un conteneur, le stock en arrivage passe en physiquement diponible. **cela ne modifie pas la disponibilité a le vente du produit**
2. **Conteneur commandé**: Commande d'un conteneur -> le stock en arrivage est modifié a la hausse.
3. **Retirer du stock**: Retirer du stock qui est physiquement disponible **et** disponible a la vente.
4. **Ajouter au stock**: Ajouter du stock physiquement disponible **et** disponible a la vente.
5. **Annulation arrivage**: Retirer du stock en arrivage **et** disponible a la vente.

La Raison de l'ajustement dois egalement etre renseigner ainsi que la liste des produits et quantitées de l'ajustement (exemple ci dessous).

![Ajustement de stock exemple 1](/img/orders_and_delivery/stocks/ajustement_example_1.png)

Une fois l'ajustement crée, pour l'executé rendez vous dans le rapport de **stock ajustement** dans la section **stocks** puis cliquez sur le bouton *Perform Ajustement* situé dans l'entrée correspondante (exemple ci dessous), si l'ajustement créer est valide le stock sera ajusté. les entrées des ajustement effectué auront leur boutton *Perform Ajustement* grisé.

![Ajustement de stock exemple 2](/img/orders_and_delivery/stocks/ajustement_example_2.png)

