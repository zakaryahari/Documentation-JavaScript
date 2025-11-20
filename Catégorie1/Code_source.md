//Catégorie 1 : Concepts JavaScript de Base

//Variables : var, let, const

    //### Définition :

    For the definition, they are all used to create a variable to store data.

    //### Syntaxe :

    var exemple1 = 12;
    let exemple2 = 12;
    const exemple3 = 12;

    //Cas d'Utilisation :

    --var: is the old way of declaration, it uses function scope and can be redeclared.
    --let: is used to create a variable that we can rechange the value of everytime.
    --const: is used when we want to create a var that will not have the ability to change later.

//Fonctions:

    //### Définition :

    The function is used to simplify the way of using code. Instead of rewriting the code every time, we put it inside a function to call it later, and it accepts to pass arguments.

    //### Syntaxe :

    function functionname(argument) {
        // innercode
    };

    //Cas d'Utilisation :

    --you can return a value to use in other parts of the code.
    --you can use the arrow function, that can be used inside a block like a listener, without declaring it.

    //Exemple :

    function addtwonum(a,b){
        return a+b;
    }

//Types de Données:

    //### Définition :

    There are two types of data: 'Primitive Types' and 'Reference Types'. They are the types used by variables declared by the user.

    //### Cas d'Utilisation :

    --The Primitive is all of this: 'String', 'number', 'boolean', etc.
    --The Reference Types is all of this: 'Object', 'Array', 'Functions'.
    --typeof() is used to identify the type of the passed argument, to determine for us which type it is.

    //Exemple :

    typeof(exemple1); // it will return that it's a "number".
    typeof(addtwonum); // it will return that it's a "function".
