# Chapitre 1 - Partie 2 : les types

Comme tous les objets, les variables ont un type.
Si on compare les variables à des fruits : il existe plusieurs espèces de fruits, c’est la même chose pour les variables.

De la même manière qu’on ne peut pas forcément mélanger ou faire les mêmes choses avec des pommes et des oranges, chaque type de variable a un usage particulier.

## I/ Les types primitifs

Sans plus tarder, les types les plus simples, appelés les **types primitifs**, sont :

**Int - entier** : c'est le type des entiers (comme en Maths !)
:::outline{outlineType="EXEMPLE"}
Exemple : 5, 67, 9554447
:::

**Float - flottants**: c'est le type des nombres décimaux
:::outline{outlineType="EXEMPLE"}
Exemple : 56.0, 67.373894
:::
:::outline{outlineType="ATTENTION"}
Attention ! Les virgules dans les nombres sont des points !!!!!!!
:::

**Str (string) - chaîne de caractères** : tout ce qui est mots ou utilisation de caractères sont des chaînes de caractères et doivent être entre guillemets ! 
:::outline{outlineType="EXEMPLE"}
Exemple : "bonjour" est une chaîne de caractères mais attention, bonjour ne l'est pas !!!
On peut mettre des majuscules, des minuscules, des caractères spéciaux et des espaces mais tout doit être entre guillemets. 
:::
:::outline{outlineType="EXEMPLE"}
Exemple : 'Salut tout le monde' est une chaîne de caractères, de même que " Salut :), j'adore python et toi ?"
:::

**Bool - booléens** : ce sont les variables *True* et *False*, qui signifient respectivement vrai et faux.
Ce type est un peu spécial parce qu'en plus des valeurs True et False, *un 1 est associé à True et un 0 est associé à False*. Vous vous dites peut-être que ce type n'a pas l'air très utile mais c'est tout le contraire !! On verra plus tard l'utilité de ce type très important !!

## II/ Pour aller plus loin

***POUR ALLER PLUS LOIN*** : 

**List - liste** : ce type aura un chapitre entier tellement il est utile et intéressant ! Une liste est comme on peut le comprendre, une liste d'éléments de n'importe quel type. Elle est représentée entre crochet et les éléments sont séparés par des virgules.
:::outline{outlineType="EXEMPLE"}
Ex : [3,5], ["Adidas ou Nike ?"], [True, 45, ["perso Adidas"]] sont des listes
Pour le moment, nous ne vous en dirons pas plus ! 
:::

**Dict - dictionnaires** : vous verrez également ce type en détail un peu plus tard. Pour résumer rapidement, un dictionnaire permet de ranger des objets (entiers, flottants…) de sorte à ce qu’on puisse les retrouver rapidement. Comme dans un dictionnaire ( le gros livre avec plein de mots et pas le type), lorsqu'on cherche un mot appelé clé, on reçoit une définition qui est la valeur associée.
Ce type se présente dans des accolades comme suit : {clé1 : valeur1 , clé2 : valeur2}
:::outline{outlineType="EXEMPLE"}
Ex : {"écurie 1" : [], "écurie 2":[]}
:::

Il existe davantage de types comme les tuples ou les tableaux mais nous verrons cela dans la section pour aller plus loin ou dans le futur ...

### EXERCICES : 

Exercice 1 : Quel type ?
1. 56.68
2. False
3. 0
4. "Vous avez aimé le cours ?"
5.  {"Thaïs" : "n'oubliez pas le pouce bleu :)" }
6.  [1,2,5]
7.  Piège
8.  18

 ## III/ Quel rapport avec les variables ?

Dans le chapitre précédent, nous avons vu comment définir et initialiser une variable. Maintenant, nous savons qu'une variable peut être de types variés. 

### EXERCICE : 
1. Initialisez dans une variable nommée *record_de_but*, l'entier 34. Quel est le nom "officiel" du type de la variable *record_de_but* ?
2. À présent, associez à la variable *record_de_but*, la valeur "non défini". Quel est à présent le type de la variable *record_de_but* ?

Dans cet exercice, on a pu remarquer que les variables ne sont pas limitées par le type. La boîte que représente la variable n'est pas faite pour un type en particulier. Elle peut être initialisée par un entier, puis devenir une chaîne de caractères. Plus simplement, si on considère une variable x initialisée avec l’entier 4, on peut écrire l’instruction *x = “changement de type”* et à présent x est une chaîne de caractères. Le type d’une variable peut varier en fonction de ce qu’elle contient.


