# Deuxième partie du SDZ 
Index 
* Partie 1 : Manipuler le DOM 
    * Comprendre le DOM 
    * Accéder aux éléments du DOM 
    * Modifier le DOM 
    * Les événements 
    * Récupérer des données utilisateur avec les événements 
* Partie 2 : Communiquer avec un service web 
    * Comprendre un service web 
    * Récupérer les données d'un service web 
    * Valider les données saisies par l'utilisateur 
    * Sauver les données sur un service web 
* Partie 3 : Programmation asynchrone 
    * Comprendre comment fonctionne l'asynchrone 
    * Gérer du code asynchrone 
    * Paralléliser plusieurs requêtes HTTP 
* Partie 4 : Environnement de travail 
    * Optimiser son code 
    * Gérer les dépendances 
    * Compiler et exécuter son code 

# Partie 1 : manipuler le dom 
## Comprendre le DOM 

Le DOM = Document Object Model est une API (Application Programming Interface) entre JS et des documents XML / HTML 

Structure du DOM : arborescente (un noeud peut avoir plusieurs noeuds enfants mais chaque enfant a un seul parent)

Utilité du DOM 
* CRUB sur des éléments HTML en fonction (ou pas) d'événements 

## Accéder aux éléments du DOM 

Récupérer les éléments (via l'objet document qui représente la balise <html>)
* document.getElementById('id'); // ex let title = document.getElementById('important_title'); 
* document.getElementsByClassName('classe'); //sous forme d'un tableau ordonné 
    * ex let elements = document.getElementsByClassName('classe1 classe2'); //pas seulement sur l'objet document d'ailleurs 
* document.getElementsByClassName('...'); 
* document.querySelector('...'); //retourne le premier élément qui colle avec le sélecteur CSS 
* document.querySelectorAll('...'); //retourne un tableau numéroté avec tous les éléments qui collent 

Récupérer les éléments depuis un élément (hyper light de nouveau)
* element.children; //retourne un tableau des enfants directs de element
* element.parentNode; //retourne le parent de element 
* element.nextElementSibling; //ou encore element.previousElementSibling ... Sibling = fratrie 

## Modifier le DOM 
### Modifier le contenu d'un élément 
2 méthodes (en lecture et écriture)
* innerHTML 
* textContent //pas interprété comme du HTML donc sans les balises 
Exemple : 
```
element.innerHTML = '<ul><li>Puce</li><li>Puce</li></ul>'; 
```

### Modifier les classes 
Tout passe par element.classList qui possède plusieurs méthodes 
* element.classList.add('nouvelle_classe'); 
* element.classList.remove('ancienne_classe'); 
* element.classList.toggle('nom_classe'); 
* element.classList.contains('nom_classe'); //true ou false 
* element.classList.replace('old', 'new'); 

### Modifier les styles 
Quelques exemples
* element.style.color = '#FFFFFF'; 
* element.style.backgroundColor = 'rgb(255,0,0)'; //background-color --> backgroundColor 

### Modifier les attributs 
element.setAttribute('nom_attribut', 'valeur'); 
* let url = link.getAttribute('href'); 
* link.removeAttribute('href'); //aucun sens mais juste pour la syntaxe 

### Créer de nouveaux éléments 
* const new_element = document.createElement('p'); //création d'une nouvelle balise p avec une référence constante 
* (Perso) : séquence quand on crée de nouveaux éléments 
    * on crée l'élément en question 
    * on lui ajoute du texte au besoin (soit avec document.createTextNode('du texte') ou via textContent)
    * on lui ajoute des attributs (syntaxe selon que attribut accessible ou non, si pas -> setAttribute)
    * Ensuite on l'ajoute (voir plus loin) au DOM , cette séquence permet d'éviter de bouffer des ressources 

### Ajouter des enfants 
* parentNode.appendChild(new_child); //ex my_div.appendChild(new_element); 
* parentNode.insertBefore(newNode, referenceNode); 

### Supprimer et remplacer 
* parentNode.removeChild(child_to_remove); 
* parentNode.replaceChild(new_child, former_child); 