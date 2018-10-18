 # Tests

Pourquoi utiliser les tests !?

Cela permet de s'assurer qu'une fonction s'exécute tjr de la bonne manière et évite qu'en modifiant du code celui-ci ne fasse plus ce qui était prévu.



### JS Training

#### Mocha 

framework de tests

using “Mocha”:
install : `npm install --save-dev mocha`
run : `./node_modules/.bin/mocha`

`npx mocha`	

-> **package.json:** "mocha": "^5.2.0"

```
 "scripts": {
    "test": "mocha test/*/.js"
  },
```



il faut créer une fichier "test", doit s'appeler "test" pour que mocha le retrouve.
Dans celui-ci on crée les fichiers de test.

#### Chai.js

librairie d'assertions.

install : `npm install --save-dev chai`
-> **package.json: ** "chai": "^4.1.2",

inclure chai dans les fichiers de test : `const chai = required(chai) `

toutes les fonction possible : [chaijs.com](chaijs.com)





#### structure du fichier de test

```
const chai = require('chai');
const { arraySum, nonUniqueElements, longRepeat } = require('../src/training'); 

describe('Synchronous', () => {
  it('should sum values in an array', () => {
  });
  it('should return nonUniqueElements', () => {
  });
});	
```

`it ` permet de décrire le comportement.
on va poser les assertion

Au début il faut inclure la librairie d'assert (chai)

il faut inclure les fonctions du fichier que l'on veut tester. ( ici: { arraySum, ...,  ... })



```
chai.should();
```

permet ensuite d'appeler should sur tous les objects js.

Il est aussi possible de l'instancier directement. Avec l'object destructuring

```
const { should } = require('chai');
```





#### Eslint

Pour configurer Eslint pour qu'il fonctionne avec mocha. On va créer un fichier `.eslintrc.js` dans lequel on configurer mocha pour eslint comme ici.

```
/**
 * ESLint configuration for the `test` directory
 */
module.exports = {
    "env": {
        // adds all of the Mocha testing global variables such as `describe` and `it`
        "mocha": true,
    },
    "rules": {
        // Mocha recommend using anonymous functions instead of arrow callback
        // in order to access mocha context. So weed to disable those rules.
        // https://mochajs.org/#arrow-functions
        "prefer-arrow-callback": "off",
        "func-names": "off"
    }
};
```

