# Exercices Javascript

Pur Vanilla Javascript, aucune lib ou framework


Portée des variables
======

Scope
----

Voici des exemples de variables qui s'entrecroise. On appelle un "scope" le lieu ou des variables peuvent être appelées.


        function doStuff(){
            var i = "can you get me ?";
        }
        
        // Estce que la variable i est dans le scope courant ?
        var j = i;
        console.log(j);

* 1) Est-ce que i et j sont dans le même scope ?
* 2) Est-ce que la fonction `doStuff` est dans le scope de j ?




Scope croisé
---


        var i = 10; // déclaration et affectation à 10 de la variable.
        
        var name; // Déclaration de la variable, elle est crée mais vaux toujours undefined. 
        name = "John"; // j vaux maintenant "John";
        
        i = 12; // la variable i précédente vaux 12
        
        
        /*
        La fonction doStuff est crée. Il existe une variable doStuff;
        L'astuce est que le compilateur fait en sorte que cette fonction soit accessible depuis tout le scope du programme.
        */
        
        funtion doStuff(someName){
        
            // On donne name en paramètre. 
            // La variable name est également accessible
            return someName + name;
        
        }
        
        doStuff("Jim"); // Quel est le résultat ?
        

* 3) Quel est le résultat de `doStuff("Jim");`
* 4) Est ce qu'une fonction a accès au scope exterieur ?



Scope dans des blocs
----

Javascript est un peu laxiste dans la gestion des blocs. Le fonctionnement n'est pas toujours très logique, surtout en comparaison avec les autres langages.


        var x = 10;
        
        for (var i = 0 ; i < 5 ; i ++){
            
            var y = i + x;
            
        }
        
        var z = y; // y a été déclaré dans un autre bloc. On s'attend à ce que cette variable ne soit pas accessible.

* 5) Quelle est la valeur de z ?
* 6) A votre avis pourquoi ?


        var x = 10;
        
        function doStuff(i){
           
           var y = i + x;
        
        }
        
        var z = y;

* 7) Quelle est la valeur de z ?
* 8) A votre avis pourquoi ?



Redéfinition 
----


        var i = 10;
        
        for (var i = 0 ; i < 5 ; i ++){
            
            var y = i+1;
            
        }
        
        var z = i; 
        

* 9) Quelle est la valeur de z ?
* 10) A votre avis pourquoi ?   



Ecriture de chaines
=====


`"John" + " Doe"` concatène deux chaines et donne `"John Doe"`


        var i =0;
        var name = "Joe";
        
        console.log(i +" : " + name);

* 1) Quel est le résultat ?

John a le numéro 1, mais l'index est i=0; on veut présenter `John : 0`. On a donc tenter plusieurs possibilités :

        i = i+1; // mais i change de valeur
        console.log(name + " : " + i);
        
        ----
        
        i++; // pile poil pareil en plus court
        console.log(name + " : " + i);
        
        --- 
        
        var j = i+1; // plus safe, l'index est inchangé
        console.log(name + " : " + j);
        
        --- 
        
        console.log(name + " : " + (i+1) );
        // Plus compliqué. 
        
        ----
        
        console.log(name + " : " + i+1 );
        // ?
        
        
* 2) Quel est le résultat avec `console.log(name + " : " + i + 1 );`
* 3) Expliquez la différence avec console.log(name + " : " + (i+1) );


On a maintenant deux tableaux. Un avec les prénomes, l'autre avec les noms. Et on veut les réunir.


                var firstNames = ["Joe", "Jamel", "Nicolas", "Henri"];
                var lastNames = ["Lemon", "Ankholic", "Jhen", "Khan"];

Avec un petit programme et une boucle for, affichez les noms en commençant par le numéro 1;

                1 : Joe Lemon
                ...



