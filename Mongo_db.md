# Mongo db

NoSQL database

Les données sont stockée sous forme d'objet directement. 
Il n'y a donc pas besoin de faire de conversion après avoir récupérer des données.


#### index 

Un **index** permet de retrouver les éléments très rapidement. Par défaut les l'id permet de faire les requêtes  rapidement. 
Sans index il faut regarder chaque entrée pour retrouver une valeur. 
Si un index est appliqué sur un champs il sera possible de faire les requêtes rapidmeent sur ces valeurs.

#### Rich document data model

On regroupe tous les éléments lié à un objets lié directement à celui-ci. ( exemple pour un article on stocke directement tous les éléments qui y sont liés dans l'objet de celui-ci.) -> dans ce cas on ne fais pas des liaison vers des objets multiple, mais on fait de l'**inclusion** des données dans l'objet.

Il est donc important de se poser la question de l'utilisation et des besoins de l'application.

#### References

Les références se font avec des identifiants générés par la db.

#### inclusion vs références

**préférer l'inclusion si  :**

- dans le cas de relation de "contient"
- quand on à des relation de "one to few".  1 à quelques

pas d'inclusion si :

- il y a un risque d'atteindre le max de 

**préférer les références**

- si l'inclusion provoquerait de le redondance mais pas d'amélioration significatives des perf.
- ..

Dans une base Normalisée, il faudrait faire plusieurs requêtes dans le cas d'un élément avec des relation.
Dans une base Inclusive, il ne faut faire qu'une requête pour obtenir toutes les données liées à l'élément.

exemple : (contact avec user) : avec l'inclusion. On obtient directement l'adresse liée à un contact. Il n'est pas contre pas possible d'obtenir l'adresse toute seule. La requêtes est automatiquement liée au contact.



### insert in database

La base de donnée est une db schéma less. Il est possible d'entrer des données de types différents dans les même tables.

```
db.users.insertOne(
)
```



On utilise un JDBC driver

Exemple connect and insert:

![Screenshot from 2018-10-18 13.21.23](/home/joel/Switchdrive/HEIG/S-5/TWEB/Notes/img/Screenshot from 2018-10-18 13.21.23.png)

### Mongoose (ORM), ODM

"Object Document Mapping"





Il est possible de remplacer le exec d'une commande par un .then. En faisant cela il est possible d'ajouter des conditions avant de l'exécuter au moment de l'exécution. Par contre si on appel .then 2 fois dessus, elle est exécutée 2 fois aussi.-> exec évite cela



Studio3T : permet de voir les données Mongo
MongoDB Atlas : hébergement.

