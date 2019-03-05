
# Manipuler des chaînes de caractères en programmation

**Qu'est-ce qu'une chaine de caractère ?**

Cela peut être votre nom, prénom, un code postal etc...
C'est une information sous forme alphabéthique ou numérique.

Lorsqu'on utilise une chaine de caractère, il faut toujours la mettre entre guillemets (simple ou double). 

```
var nom = "Truel"; // OK
var prénom = 'Jean'; // OK
var message = "Bonjour'; // PAS OK
```

Si vous avez utiliser les simples guillemets et que votre chaine de caractère contient un apostrophe, cela va provoquer une erreur.

```
var phrase = 'C'est une apostrophe dans des apostrophes.'; // PAS OK
var phrase = "C'est une apostrophe dans des apostrophes."; // OK
var phrase = "Une citation "entre guillemets" ne passe pas."; // PAS OK
```

Si vous devez vraiment utiliser une chaine de caractère avec du texte qui possède déjà des guillemets, la solution est d'utiliser les **backslash**.

```
var phrase = "Une citation \"entre guillemets\" ne passe pas."; // OK 
```


## Utiliser la concaténation

Un concaténation n'est pas une addition!

L'addition concerne du numérique

```
var a = 5;
var b = 5;
var c = a + b; // Ici c vaut 10
```

La concaténation concerne des chaines caractères

```
var a = "5";
var b = "5";
var c = a + b; // Ici c vaut 55
```

Avec la concaténation, les informations se mettent bout à bout.

Qu'est qui ce passe si j'utilise une chaine de caractère avec du numérique ?

```
var a = 5;
var b = "5";
var c = a + b; // Ici c vaut 55
```


```
var a = 5;
var b = "b";
var c = a * b; // Une erreur se produit et affiche NaN
```

Le signe pour la concaténation peut varier en fonction du langage...

- Javascript c'est un +
- Visual basic c'est un &


## Lire une chaine comme une valeur

Il est possible de covertir une chaine en numérique afin d'y appliquer des calculs.

```
var a = "55"; // guillements donc chaine
var convertir = Number(a); // devient un nombre
```

Dans tous les type de langage, une variable de type chaine de caractère qui contient du numérique peut être convertie.

:exclamation: Une chaine de caractère est en langage de programmation un objet de type string donc une chaine de caractère possède des propriétés et des méthodes.

Plus d'informaton sur les objets : [Les objets](objet.md)

## Obtenir la taille d'une chaine de caractère

Étant donner que la chaine est un string, nous pouvons utiliser la propriété length.

```
var phrase = "C'est une simple phrase.";
alert(phrase.length); // Affiche la nombre de caractère dans phrase
```

## Transformer le contenu d'une chaine avec une méthode

Si je souhaite transformer ma phrase en majuscule, je peux utiliser la methode toUpperCase.

```
var phrase = "C'est une simple phrase.";
alert(phrase.toUpperCase());
```

Si vous souhaitez connaitre plus de méthodes pour les chaine de caractère, allez sur ce lien : [String](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/String)


## Comparer des chaines

```
var uneChaine = "Bonjour";
var uneAutreChaine = "bonjour";

if(uneChaine != uneAutreChaine){
    alert("C'est différent");
}
```

Ci-dessus, les chaines sont différentes car la première a une majuscule.

La solution pour les comparer, c'est d'utiliser la méthode toLowerCase. Celle-ci va transformer notre chaine en minuscule.

```
if(uneChaine.toLowerCase() == uneAutreChaine.toLowerCase()){
    alert("C'est pareil");
}
```

:exclamation: Peut importe le langage, lorsque vous comparer deux chaine, la case est important car une majuscule n'a pas le même poids qu'une minuscule.

## Recherche une chaine dans une chaine

Régulièrement, vous aurez besoin de savoir si une chaine de caractère contient tel ou tel mot.

```
var phrase = "Les formations informatiques.";
var position = phrase.indexOf("informatiques"); // 4
```

Si le mot n'existe pas dans la chaine de caractère, indexOf renvoie -1

```
if(phrase.indexOf("test") == -1){
    alert("Ce mot n'est pas présent.");
}
```

## Manipuler un chaine de caractère

```
var phrase = "Je veux être developpeur";

var segemnt = phrase.slice(3,7) // segment est égal à veux
```

Avec la méthode slice, vous pouvez isoler une partie de la chaine.

Les paramètre ne calcule pas la position de la même manière.

Le première paramètre est le départ et il commence de 0 à ...

Le deuxième paramètre est la fin et il commence de 1 à ...


Il y d'autre méthodes comme substing ou substr...


## Expressions régulières

L'utisation des exprissions régulière est difficile mais elles sont dans de nombreux langages.

Utilités :

- Vérifier une adresse email, un code postal ou ...
- Permet de controller
- Permet de formater


Étapes d'utilisation :

- Définir l'expression
- Appliquer l'expression


Exemple :

```
var expression = new RegExp("bonjour"); // On peut écrire aussi var expression = /bonjour/;
 
var uneChaine =  "Est-ce que cette phrase contient le mot bonjour ?";

if(expression.test(uneChaine)){
    alert("Oui");
}
```

Le symbole / indique le début et la fin.

Test est une méthode qui appartient à l'objet RegExp et elle return true ou false

Autres exemples :

```
var expression = /^bonjour/;
```

Le symbole ^ indique commence par

```
var expression = /bonjour$/;
```

Le symbole $ indique fini par


```
var expression = /bonj+o/;
```

Le symbole + indique que le caractère précédent peut se trouver une à plusieur fois dans la phrase ("bonjour", "bonjjour" ou "bonjjjjjjjjour")


```
var expression = /bonj*o/;
```

Le symbole * indique que le caractère précédent peut se trouver 0 à plusieur fois dans la phrase ("bonour", "bonjour" ou "bonjjjjour")


```
var expression = /bonj?o/;
```

Le symbole ? indique que le caractère précédent peut se trouver 0 à 1 fois dans la phrase ("bonour", "bonjour")


**Autres symboles :**

Symbole | veut dire ou

```
/bonjour|aurevoir/;
```

Symbole \W veut dire caravtère aplphabétique (majuscule ou minuscule), chiffres et le souligné mais pas d'accent.

```
/\wonjour/;
```

Symbole \b veut dire qu'il y a espace ou ponctuation au le début ou la fin d'un mot.

```
/\bbonjour/; // Ici la lettre b n'est précédée par rien donc c'est OK
```

```
/bonjour\b/; // Ici la lettre r n'est suivie par rien donc c'est OK
```

symbole [...] Certains caractères.

```
/bo[nj]our/; // bonour est OK ou bojour est OK
```

symbole . un unique caractère.

```
/bo..our/;
```

[plus d'infos](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/RegExp)
[Explication EN sur les expressions regulières](https://flaviocopes.com/javascript-regular-expressions/?fbclid=IwAR2S6dI2gw79LnQ2apCYpOFctm1CC6oYqTX4D-jy5hXcZOwbtcXPvVURIH4)
[Explication EN sur les expressions regulières](http://exploringjs.com/impatient-js/ch_regular-expressions.html?fbclid=IwAR2CDhzeVXNrTAKZfTjCNF960L807ctiQMoMU90i_bNchhgiwGrAKT_oSAA)
[Exercices EN sur les expressions regulières](https://regexone.com/?fbclid=IwAR0W654H83MShx1t2zvmpZ_WHfNb4ZydIsPgj-nidt8s_HWmO0gPGx78TdA)





