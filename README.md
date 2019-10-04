# Javascript-Personnal
## SDZ First Part 
Index 
[source] (https://openclassrooms.com/fr/courses/6175841-apprenez-a-programmer-avec-javascript)
[table de compatibilité de ES6](https://kangax.github.io/compat-table/es6/)
* Partie 1 : Les données et types de données 
    * Déclarer des variables 
    * Les types de données 
    * Les objets 
    * Les collections 
* Partie 2 : Logique d'un programme 
    * La fonction main 
    * if ... et switch 
    * Les boucles 
    * Erreurs et exceptions 
* Partie 3 : Code propre et maintenable 
    * Paramètres et valeurs de retour 
    * Méthodes d'instance et champs 
    * Créer ses fonctions 
    * Tester une fonction 
    * Déboguer sa fonction 
    * La récursivité 
* Annexe (Ajouts perso)


## Partie 1 : Les données et types de données
### Déclarer des variables 
Définition d'une variable 
* Les variables sont des zones de mémoires volatiles (donc dans la RAM) 

Le nom d'une variable 
* explicite (et aen englais pliz ;)
* convention de nommage camelCase ou camel_case (que je préfère)
* caractères alphanumériques, sensible à la casse le $ et _ sont acceptés, doit commencer par une lettre 
* pas de noms réservés (obvious)
* le scope d'une variable avec let et const -> purement de type bloc !! (>< à var)

Déclarer (et affecter une variable)
* let nom_variable; //déclaration 
* let nom_variable = valeur; //déclaration et affectation en même temps 
* let variable1 = valeur_1, variable2 = valeur_2; 

Changer la valeur d'une variable 
* opérateurs arithmétiques (+ - * / %)
* quelques raccourcis 
    * x += valeur; //marche avec tous les types et valeurs si compatibles 
    * x++; (idem avec --) note ++x (pré-incrémentation prioritaire % opérateur d'affectation)

Les constantes 
* si un objet (une séquence aussi) on peut une constante -> le pointeur est constant 
* const ma_variable = valeur; 

### Les types de données 
Les types primitifs (qui sont passés par valeurs)
* number (sous-types les int et les floats)
* string 
* boolean 

typeof(variable) // retourne le type de la variable ex 'number', 'boolean'

Pour les booléens -> true ou false //en minuscule 

Pour les chaines de caractères 
* let chaine = 'Bonjour'; 
* let chaine_totale = chaine1 + ' ' + chaine2; //concaténation 

Le typage est dynamique en JS 

### Les objets 
#### Les objets (écriture en JSON = JavaScript Object Notation)
Déclarer un objet littéral 
```
let monLivre = { //convention camelCase dans mon cas 
    title : 'mon titre', 
    author : 'nom prénom', 
    number_of_pages : 300, 
    is_available : true
};
```
Récupérer la valeur (ou la changer)
```
monLivre.title //retourne 'mon titre' 
monLivre.number_of_pages += 30; //on ajoute une préface
```
#### Manipuler les classes

Créer une classe 
```
class MyBook {//convention CamelCase dans mon cas 
    constructor(title, author, pages){ //un constructeur le plus simple du monde 
        this.title = title; 
        this.author = author; 
        this.pages = pages; 
    }
}
```
Créer une instance 
```
const mon_livre = new MyBook('Le seigneur des anneaux', 'son autheur', 259); 
```

### Gérer la comple
Index 
* Les tableaux 
* Les sets 
* Les maps 

#### Les tableaux 
Création d'un tableau 
```
const mon_tableau = [valeur1, valeur2, ....]; //const car pointeur ... on peut avoir des types différents 
```

Accès/modification d'une case 
```
tableau[0] //la première valeur 
tableau[tableau.length-1] //la dernière valeur 
tableau[0] = nouvelle_valeur; 
```

Longueur du tableau 
```
tableau.length; //retourne la taille
```

Ajouter/Supprimer des éléments 
* A la fin du tableau (mieux pour les performances)
```
    tableau.push(x1,x2,....,x_n); //ajout des valeurs à la fin du tableau 
    tableau.pop(); //retire la dernière case du tableau 
```
* Au début du tableau 
```
    tableau.unshift(x1,x2, ...., x_n); 
    tableau.shift(); 
```

#### Les sets 
Je reviens dessus mais le tutoriel est à chier 
#### Les maps 
Equivalent d'un dictionnaire donc un ensemble clef-valeur 

## Partie 2 : Logique d'un programme en javascript 
### La fonction main 
Rien de majeur dans cette partie (on peut utiliser JS pour le front et le back) 
Personnellement je vais commencer par une fonction main (histoire de limiter les variables globales) 

### if ... et switch 
#### Opérateurs de comparaison 
* == et != (vérifie la valeur égalité)
* === et !== (mieux : vérifie la valeur et le type donc pas de conversion implicite)
* <, <= , >, >= 

#### Opérateurs logiques 
* && 
* || 
* ! 

#### if else if else 
```
if(condition){
    //come code 
}else if (condition){
    //some code 
}else{
    //some code 
}
```

#### le switch 
Attention le switch permet de faire uniquement un === sur plusieurs cas de figure 
```
switch(variable){
    case 0: 
        code; 
        break; 
    case 1: 
        code; 
        break; 
    .... 
    default :
        code; 
}
```
### Les boucles 
#### For
```
for(let i = 0, c = tableau.length; i < c; i++)
{
    tableau[i];
}
```

#### For ... of et for ... in 
```
for (let i in tableau){
    tableau[i]; 
}
```

```
for (let element of tableau) {
    element; //idem donc pas besoin de calculer index mais on ne peut pas toucher à l'index dans ce cas de figgure
}
```
#### While 
```
while(condition){
    code; 
    //incrémentation versus break ou continue 
}
```
#### Do while
```
do{
    code; 
    //incrémentation versus break ou continue
}while(condition); //sera forcément exécuté une fois puisque la condition apparait après le bloc 
```
### Erreurs et exceptions
#### Les trois types d'erreur 
Les 3 types d'erreur 
* erreurs de syntaxe (easy ça plante et l'interpréteur le dit)
* erreurs de logique (concentre moi gamin !)
* erreurs d'exécution (exemple exception donne ton age -> bidonjour ?!)

```
try{
    code à essayer
}catch (error) {
    //code si erreur 
}
```

Remarque (va falloir que je cherche) il existe des architectures pour traquer et gérer les erreurs (ex les tests unitaires mais en mieux)



## Partie 3 : Code propre et maintenable 
### Paramètres et valeurs de retour 
Créer une fonction 
* Première syntaxe (ancienne - à éviter donc)
```
function nomFonction(arg1, arg2, ..., arg_n){
    //code 
    //éventuellement un return 
}
```
* Deuxième actuelle cette fois 
```
const nomFonction = (arg1, arg2, ...., arg_n) => {
    //code 
    //éventuellement un return 
}
```
Appel de la fonction 
```
let variable = nomFonction(x1,x2, ...., x_n); //variable seulement si nomFonction a une valeur de retour obvious ! 
```
### Méthodes d'instance et champs 

### Créer ses fonctions 
### Tester une fonction 
### Déboguer sa fonction 
### La récursivité 