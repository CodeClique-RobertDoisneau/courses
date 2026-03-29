### ⭐⭐ **EPM341 - Exercice 1 : Calcul de la factorielle**

*Notions : factorielle*  

Imaginer être le proffesseur d'EPS. Vous avez une après-midi conscré aux sports et vous devez choisir l'ordre des sports pour cette evenement. Vous avez le choix entre 4 sports. Un eleve vient vous voir et vous demande combien de choix differents vous avez. Vous lui repondez, a raison, que pour le sport de 13h vous avez 4 choix, puis 3 pour celui de 15h et ensuite plus que 2, et enfin le dernier non encore choisis. Ainsi au total vous avez $4 \cdot 3 \cdot 2 \cdot 1 =24$ choix. Le nombre de facon d'arange les element d'un ensemble à $n$ elements s'apelle la factoriel de $n$. Et ce note $n!$, de maniere suffixe avec un point d'exclamation pour montrer que ce nombre est tres grand !


## I/ Exercice

1. Etablisser la relation de récurence definissant la facotorielle.


2. Definisser une fonction Python, factorielle(n) calculant la factorielle de n.


3. (Approfondissmeent) La relation de recurence definssant la factoirelle etant recurente il serait appreciable de coder de maniere recursive comme la defintion mathamtiques. Pour ce faire on peut commencer à ecrire un code sous cette forme.

```python
def factorielle(n): 
    return n * factorielle(n-1)
```

On remarquera que la fonction se definit en utilisant sa propre defintion ! Ce qui est tout a fait suprenat et pourtant remaruqebla c'est uqe cette definition est totu a fait valable ! La raison depasse malheuresement de loins l'objectif de ce cours.

Toutefois en l'etat l'exemple ne marche pas ... en effet en l'etat on a les reusltats suivant : factorielle(2) = 2 * factorielle(1) = 2 * 1 * factorielle(0) = 2 * 1 * 0 * factorielle(-1) = ... ce qui ne s'arrete jamais... et cela est problematiques. Corriger le probleme en rajoutant ce que l'on apelle un cas de base traitant la valeur de factorielle pour n = 1. 