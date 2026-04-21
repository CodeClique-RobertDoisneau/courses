# TP — La suite de Fibonacci

La suite de Fibonacci est l'une des suites les plus célèbres en mathématiques. Chaque terme est la somme des deux précédents :

$$F_0 = 0, \quad F_1 = 1, \quad F_{n+2} = F_{n+1} + F_n$$

Les premiers termes sont donc : 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, …

## 🐰 D'où vient cette suite ?

Fibonacci a découvert cette suite en 1202 en étudiant la reproduction des lapins. La règle : chaque paire adulte donne naissance à une nouvelle paire chaque mois, mais les nouveaux-nés mettent un mois à grandir avant de pouvoir se reproduire.

| Mois | Évolution des lapins | Nombre de paires |
|------|----------------------|------------------|
| 1 | 🐰🐰 | 1 |
| 2 | 🐰🐰 | 1 |
| 3 | 🐰🐰 🐰🐰 | 2 |
| 4 | 🐰🐰 🐰🐰 🐰🐰 | 3 |
| 5 | 🐰🐰 🐰🐰 🐰🐰 🐰🐰 🐰🐰 | 5 |
| 6 | 🐰🐰 🐰🐰 🐰🐰 🐰🐰 🐰🐰 🐰🐰 🐰🐰 🐰🐰 | 8 |

On retrouve bien la suite : **1, 1, 2, 3, 5, 8, …**

## Vidéo d'introduction

::video{link="https://www.youtube-nocookie.com/embed/lqMf1HtW9Ys?rel=0&modestbranding=1&iv_load_policy=3"}

## Objectifs du TP

- Calculer les termes de la suite de Fibonacci en Python
- Réutiliser la méthode du **calcul de seuil** vue dans la Partie 3
- Observer la croissance rapide de cette suite

## Exercice 1 — Calculer un terme donné

Écrire une fonction `fibonacci(n)` qui renvoie le terme $F_n$ de la suite.

**Méthode :**
- Initialiser deux variables : `a = 0` (pour $F_0$) et `b = 1` (pour $F_1$)
- Faire une boucle `for` qui tourne `n` fois
- À chaque tour, calculer le terme suivant et décaler les variables

```python
def fibonacci(n):
    a = 0
    b = 1
    for i in range(n):
        a, b = b, a + b
    return a
```

**À tester :** `fibonacci(10)` doit renvoyer `55`.

## Exercice 2 — Calcul de seuil

En réutilisant la méthode de la Partie 3, écrire une fonction `seuil_fibonacci(S)` qui renvoie le plus petit rang $n$ tel que $F_n \geq S$.

**Méthode :**
- Initialiser `a = 0`, `b = 1`, `n = 0`
- Tant que `a < S`, calculer le terme suivant et incrémenter `n`
- Renvoyer `n`

```python
def seuil_fibonacci(S):
    a = 0
    b = 1
    n = 0
    while a < S:
        a, b = b, a + b
        n = n + 1
    return n
```

**À tester :** À partir de quel rang $F_n$ dépasse-t-il 1 000 ? 1 000 000 ?

## Exercice 3 — Afficher les premiers termes

Écrire un programme qui affiche les 20 premiers termes de la suite de Fibonacci.

## Pour aller plus loin

Le rapport $\frac{F_{n+1}}{F_n}$ tend vers le **nombre d'or** $\varphi \approx 1{,}618$ quand $n$ devient grand. Vérifie-le en calculant ce rapport pour $n = 10, 20, 30$.
