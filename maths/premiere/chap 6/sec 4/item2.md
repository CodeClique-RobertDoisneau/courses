### ☠️ **EPM641 - Exercice 1 : Amélioration de l'algorithme**

*Notions : méthode de Newton*  

On vient de voire que la méthode de Newton permettait de trouver un zéros d'une fonction. Pour ce faire nous calculons des itérations d'une suite récurrente. Dans notre exemple le nombre d'itération était de 1000, mais rien ne nous assure que 1000 étapes nous serons assez proche du zéros chervhée. 

```python
# Fonction f

def f(x):
	return x ** 5 - 4 * x + 5


# Fonction Df, la dérivée de f

def Df(x):
	h = 0.0001
	return (f(x+h) - f(x)) / h


# Methode de Newton

x_n = 10	
seuil = 10	      
n = 0	                                               
while n < seuil :  
	x_n = x_n - f(x_n) / Df(x_n)
	n = n + 1	

print("Valeur du zéros", x_n, " et valeur de la fonction", f(x_n))
```

1. Essayer l'algorithme de la méthode de Newton pour un seuil de 10. Et observer le problème.


2. Corriger ce problème en changeant la structure du code. Indication : on pourrait changer la condition dans le while par $f(x_{n} < \epsilon)$ (où $\epsilon$ est une lettre greque appelle epsilon qu'il faudra définir).
