# Promise

Explication des promesses : https://www.youtube.com/watch?v=u1kqx6AenYw&t=837s

Promise : Permet d'enchainer des fonctions sans pour autant devoir passer en param la fonction à chaque fois.

Callback : Une fonction passée en param, qui est appelée une fois la fonction terminée.



Le processus de promesse est considéré comme assychrone, il va d'abord finir l'exécution du code et ensuite seulement résoudre la promesse.

![1539258711561](/home/joel/.config/Typora/typora-user-images/1539258711561.png)

Ici il crée la promesse ( exécuter son contenu ) et continue l'exécution du code. Une fois tout le code exécuter, il va résoudre la promesse -> (exécuter les `.then` qui suivent) à la fin seulement.

```
Promise.resolve()
  .then(
    () => { throw new Error('Woups!'); },
    () => { console.log('c1'); },
  )
  .catch(() => { console.log('c2'); });
```

Donc au dessus, le premier argument est exécuté et comme il lève une exception, celle-ci est catchée.



```
function test() {
  new Promise(resolve => resolve('ok'))
    .then(data => {
      return data;
    });
}
```

Ne retourne rien ici, car il n'y a pas de return dans la functoin test.

```
function test() {
    return new Promise(resolve => resolve('ok'))
      .then(data => {
        return data;
      });
  }
```

Avec le `return`, la function `test`, va retourner **la promesse.**   Celle-ci doit donc être résolue pour obtenir le 'ok'  



```
new Promise((resolve) => { throw new Error('Woups'); })
  .catch(error => console.log(error.message))
  .then(() => console.log('done'));
```

Quand l'erreur est levée, on va dans le premier catch trouvé. --> si l'erreur est gérée on laisse le code continuer.
Si dans le premier catch on `throw` un nouvelle erreur, le `then` qui suit n'est pas exécuté et le code va sauter jusqu'au prochain catch.

```
new Promise((resolve) => { throw new Error('Woups'); })
  .catch(throw;)
  .then(() => console.log('done'))  	-> // n'est pas exécuté ici
  .catch(error => console.log(error.message))
```