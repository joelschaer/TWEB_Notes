# JavaScript

ECMAScript6.com : contient toutes les nouvelles syntaxes js

#### instancier une fonction

pour cela il faut donner les paramètres comme `this.`

```
class Point {
	constructor(a,b){
        this.a = a;
        this.b= b;
	}
	methode(){
        
	}
}
```

Il faut ensuite donner accès aux autre fichier à notre fonction.

```
module.exports{point};
ou
exports.Point = Point;
```

