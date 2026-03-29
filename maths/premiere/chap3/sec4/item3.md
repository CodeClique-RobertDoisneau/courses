### ⭐ **EPM343 - Exercice 3 : Fréquence des lettres**

*Notions : fréquences*  

On se donne un texte il est composée de mot mais nous allons le regarder sous un autre angle. Pour nous ce texte sera une suite de lettre de l'alphabet, sous-entendu ici qu'on ne comptabilisera pas la ponctuation. 

On cherche une structure permettant de stcoker nos fréquence d'apparations. Listons nos pre-requis. Cette strcutrue doit pouvoir contenir plusieur valuer puisqu'on nous avons plusieur lettres, de plus nous allons regulierement acceder aux element de cette structurer il faut donc un acce rapide, nous allons utiliser une liste. 

Construison la liste qui vas acceuillir nos lettres. Dans un premeir temps nous allons recuperer le nombre d'occurence de chauqe lettres dans le texte. 

On notera que c.lower() transforme c en le meme caractere en minuscule. Car sur un ordinateur une majuscule et une miniscule sont a priori different (sinon votre ordinateur ne pourrait savoir si B est ecrit comme b ou B)

Voici une ebauche de code :

Pour trouver l'index il faut faire en sorte de trasnformer a en 0 et b en 1 etc ...
Pour ce faire utiliser, ord('a') qui retourne la valeur entiere de 'a' qui malheuresement n'est pas 0... a vous de trouver comment s'en sortir.

```python
def occurence(texte):
    liste = [0 for _ in range(26)] #HP
    for c in texte :
        c = c.lower()
        if ... :
            index = ...
            liste[c] = liste[c] + 1
    return ...
```