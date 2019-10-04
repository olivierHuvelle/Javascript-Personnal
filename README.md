# Javascript-Personnal
## SDZ First Part 
Index 
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
Les types primitifs
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

