## DOM
Le DOM est une interface de programmation qui représente une page HTML et qui permet d'accéder aux éléments de cette page web et de les modifier.

## Accédez aux éléments du DOM
Chaque élément du DOM est un objet JavaScript avec ses propriétés et ses fonctions pour le manipuler.<br>
L'objet `document`
```javascript
const element = document.getElementById("id");
const element = document.getElementsByClassName("classe");
const element = document.getElementsByTagName("input")
const element = document.querySelector("#myId p.classe > a");
```
Parcourir les enfants et le parent d'un élément.
```javascript
element.children
element.parentElement
element.nextElementSibling
element.previousElementSibling
```

## Modifier les éléments du DOM
### Modifiez le contenu d'un élément
`innerHTML` et `textContent`<br>
la propriété textContent est interprété comme du texte et non pas comme du HTML
```javascript
elt.innerHTML = "<ul><li>Elément 1</li><li>Elément 2</li></ul>";
```
### Modifiez des classes
```javascript
elt.classList.add("nouvelleClasse");
elt.classList.remove("nouvelleClasse"); 
elt.classList.replace("oldClass", "newClass")
```
### Changez les styles d'un élément
```javascript
elt.style.color = "#fff"; 
```
### Modifiez les attributs
```javascript
element.setAttribute(<name>, <value>)
```
### Ajoutez Supprimez et remplacez des elements
```javascript
elt.appendChild(newElt);
elt.removeChild(newElt);
elt.replaceChild(oldELt, newElt);
```

### Écoutez des événements
Un événement en JavaScript est représenté par un nom ( `click` ,  `mousemove` ...) et une fonction que l'on nomme une `callback` <br>
[Listing des événements](https://developer.mozilla.org/fr/docs/Web/Events)
```javascript
elt.addEventListener('click', function(event){
    event.preventDefault();        // empêcher le comportement par défaut de cet élément
    event.stopPropagation();       // empêcher le parent de recevoir l'événement
});
```

## Récupérez des données utilisateurs avec les événements

## Récupérez et envoyez des données d'un service web à travers son API
L’API Fetch est un ensemble d'objets et de fonctions mis à disposition par le langage JavaScript.<br>
Fetch renvoie une Promise qui est un objet qui fournit une fonction then qui sera exécutée quand le résultat aura été obtenu, et une fonction catch qui sera appelée s’il y a une erreur.
```javascript
fetch("https://mockbin.com/request")
  .then(function(res) {
    if (res.ok) { 
      return res.json();
    }
  })
  .then(function(value) {  // la méthode json() retourne aussi une Promise qui qui sera résolue avec un objet JavaScript
    console.log(value);
  })
  .catch(function(err) {
    // Une erreur est survenue
  });
```

```javascript
fetch("http://url-service-web.com/api/users", {
	method: "POST", // PUT, delete ...
	headers: { 
        'Accept': 'application/json', 
        'Content-Type': 'application/json' 
    },
	body: JSON.stringify(jsonBody)
});
```

## Gérez du code asynchrone (callbacks,Promise,Async/Await)
### Callbacks et gérez des erreurs callbacks
```javascript
fs.readFile(filePath, function(err, data) {
    if (err) {
        throw err;
    }
    // Do something with data
});
```
### Les Promesses
Les promise, ou promesses en français, sont un peu plus complexes mais bien plus puissantes et faciles à lire que les callbacks.
```javascript
functionThatReturnsAPromise()
    .then(function(data) {
        // Do something with data 
    })
    .catch(function(err) {
        // Do something with error
    });
```
### Async/await
```javascript
async function fonctionAsynchrone1() {/* code asynchrone */}
async function fonctionAsynchrone2() {/* code asynchrone */}

async function fonctionAsynchrone3() {
  const value1 = await fonctionAsynchrone1();
  const value2 = await fonctionAsynchrone2();
  return value1 + value2;
}

N()
.then(function(res){})
.catch(function(err){})
```
Pour intercepter cette erreur, par contre, il suffit d'exécuter notre code asynchrone dans un bloc  `try {} catch (e) {}` , l'erreur étant envoyée dans le catch.

## Parallélisez plusieurs requêtes HTTP
```javascript
Promise.all([get(url1), get(url2)])
    .then(function(results) {
        return Promise.all([results, post(url3)]];
    })
    .then(function(allResults) {
        // We are done here !
});

async function requests() {
    var getResults = await Promise.all([get(url1), get(url2)]);
    var postResult = await post(url3);
    return [getResults, postResult];
}

requests().then(function(allResults) {
    // We are done here !
});
```

