### Async ###
- Fonction Asynchrone
- La fonction en question va toujours retourner une promesse.
- Les fonctions définies avec async vont donc toujours retourner une promesse qui sera résolue avec la valeur renvoyée par la fonction asynchrone
ou qui sera rompue s’il y a une exception non interceptée émise depuis la fonction asynchrone.

```javascript
async function bonjour(){
  return 'Bonjour';
}

//La valeur retournée par bonjour() est enveloppée dans une promesse
bonjour().then(alert); // Bonjour
```

### await ###
- Le mot clef await est uniquement valide au sein de fonctions asynchrones définies avec async.
- Il permet d’interrompre l’exécution d’une fonction asynchrone tant qu’une promesse n’est pas résolue ou rejetée.
La fonction asynchrone reprend ensuite puis renvoie la valeur de résolution.

```javascript
async function test(){
    const promise = new Promise((resolve, reject) => {
        setTimeout(() => resolve('Ok !'), 2000)
    });
    
    let result = await promise; //Attend que la promesse soit résolue ou rejetée
    alert(result);
}

test();
```

### Promise ###
- L'objet Promise (pour « promesse ») est utilisé pour réaliser des traitements de façon asynchrone. Une promesse représente une valeur qui peut être disponible maintenant, dans le futur voire jamais.

```javascript
const promise1 = new Promise(function(resolve, reject) {
  setTimeout(function() {
    resolve('foo');
  }, 300);
});

promise1.then(function(value) {
  console.log(value);
  // expected output: "foo"
});

console.log(promise1);
// expected output: [object Promise]
```
