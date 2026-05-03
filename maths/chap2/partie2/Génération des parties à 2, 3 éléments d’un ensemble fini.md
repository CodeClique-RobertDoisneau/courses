\# Chapitre 2 \- Partie 2 : Génération des parties à 2 et 3 éléments d’un ensemble fini

\#\# INTRODUCTION

Après avoir étudié les \*\*permutations\*\* (où l'ordre des éléments compte), nous nous intéressons maintenant aux \*\*parties\*\* (ou sous-ensembles). Dans une partie, l'ordre n'a aucune importance : l'ensemble $\\{A, B\\}$ est le même que $\\{B, A\\}$.

\#\#\# Définitions  
\* \*\*Combinaison :\*\* Une combinaison de $k$ éléments parmi $n$ est un sous-ensemble de $k$ éléments distincts choisis dans un ensemble $E$ de cardinal $n$.  
\* \*\*Coefficient binomial :\*\* Le nombre de ces parties est noté $\\binom{n}{k}$ (se lit "$k$ parmi $n$"). Il se calcule par :  
    $$\\binom{n}{k} \= \\frac{n\!}{k\!(n-k)\!}$$  
\* \*\*Propriété de génération :\*\* Pour générer des parties sans doublons (ex: ne pas lister $\\{1, 2\\}$ puis $\\{2, 1\\}$), on impose généralement un \*\*ordre strict\*\* sur les indices : $i \< j \< l \\dots$

\---

\#\# Algorithme \- Cas 1 : Génération des parties à 2 éléments (paires)

\#\#\# Idée générale  
⇒ Pour générer toutes les paires $\\{x\_i, x\_j\\}$ d'un ensemble de taille $n$, on utilise deux boucles imbriquées. La clé pour éviter les répétitions est que la deuxième boucle commence toujours après l'indice de la première.

\#\#\# Méthode générale  
Pour un ensemble $E$ d'indices allant de $0$ à $n-1$ :  
1\. Pour $i$ allant de $0$ à $n-2$ :  
2\. Pour $j$ allant de $i \+ 1$ à $n-1$ :  
3\. Afficher la paire $\\{E\[i\], E\[j\]\\}$.

\#\#\# Exemples pour visualiser  
Soit $E \= \\{1, 2, 3, 4\\}$. Ici $n=4$. On attend $\\binom{4}{2} \= 6$ paires.  
\* \*\*$i \= 0$ (élément '1') :\*\* $j$ varie de $1$ à $3$.  
    \* Paires : $\\{1, 2\\}$, $\\{1, 3\\}$, $\\{1, 4\\}$.  
\* \*\*$i \= 1$ (élément '2') :\*\* $j$ varie de $2$ à $3$.  
    \* Paires : $\\{2, 3\\}$, $\\{2, 4\\}$. (On ne reprend pas '1' car $j \> i$).  
\* \*\*$i \= 2$ (élément '3') :\*\* $j$ varie de $3$ à $3$.  
    \* Paire : $\\{3, 4\\}$.  
\* \*\*$i \= 3$ :\*\* La boucle $j$ ne peut pas démarrer ($j$ doit être $\> 3$). Fin.

\#\#\# → EXERCICES d’application directs  
1\. \*\*Calcul :\*\* Combien de paires peut-on former avec un ensemble de 10 personnes ?  
2\. \*\*Algorithme :\*\* Énumérez toutes les parties à 2 éléments de l'ensemble $\\{A, B, C, D, E\\}$.

\*\* CORRECTIONS :\*\*  
1\. \*\*Calcul :\*\* $\\binom{10}{2} \= \\frac{10 \\times 9}{2 \\times 1} \= 45$. On peut former 45 paires.  
2\. \*\*Algorithme :\*\* $\\{A,B\\}, \\{A,C\\}, \\{A,D\\}, \\{A,E\\}, \\{B,C\\}, \\{B,D\\}, \\{B,E\\}, \\{C,D\\}, \\{C,E\\}, \\{D,E\\}$.

\---

\#\# Algorithme \- Cas 2 : Génération des parties à 3 éléments (triplets)

\#\#\# Idée générale  
⇒ C'est une extension du cas précédent. Pour un triplet $\\{x\_i, x\_j, x\_l\\}$, on utilise trois boucles imbriquées avec la condition $i \< j \< l$.

\#\#\# Méthode générale  
1\. Pour $i$ allant de $0$ à $n-3$ :  
2\. Pour $j$ allant de $i \+ 1$ à $n-2$ :  
3\. Pour $l$ allant de $j \+ 1$ à $n-1$ :  
4\. Afficher le triplet $\\{E\[i\], E\[j\], E\[l\]\\}$.

\#\#\# Exemples pour visualiser  
Soit $E \= \\{A, B, C, D, E\\}$. $n=5$, on attend $\\binom{5}{3} \= 10$ triplets.  
\* \*\*$i=0 (A)$ :\*\*  
    \* $j=1 (B) \\rightarrow l \\in \\{2, 3, 4\\}$ : $\\{A,B,C\\}, \\{A,B,D\\}, \\{A,B,E\\}$  
    \* $j=2 (C) \\rightarrow l \\in \\{3, 4\\}$ : $\\{A,C,D\\}, \\{A,C,E\\}$  
    \* $j=3 (D) \\rightarrow l \\in \\{4\\}$ : $\\{A,D,E\\}$  
\* \*\*$i=1 (B)$ :\*\*  
    \* $j=2 (C) \\rightarrow l \\in \\{3, 4\\}$ : $\\{B,C,D\\}, \\{B,C,E\\}$  
    \* $j=3 (D) \\rightarrow l \\in \\{4\\}$ : $\\{B,D,E\\}$  
\* \*\*$i=2 (C)$ :\*\*  
    \* $j=3 (D) \\rightarrow l \\in \\{4\\}$ : $\\{C,D,E\\}$

\#\#\# → EXERCICES d’application directs  
1\. \*\*Logique :\*\* Dans l'algorithme ci-dessus pour $n=5$, pourquoi la première boucle $i$ s'arrête-t-elle à $n-3$ (indice 2\) ?  
2\. \*\*Programmation :\*\* Complétez ce code Python pour générer les triplets d'une liste \`L\` :  
\`\`\`python  
for i in range(len(L)-2):  
    for j in range(i+1, len(L)-1):  
        for k in range(j+1, len(L)):  
            print(..........)  
\`\`\`

\*\* CORRECTIONS :\*\*  
1\. \*\*Logique :\*\* Pour former un triplet, si $i$ est le premier élément, il doit rester au moins deux éléments après lui (pour $j$ et $l$). L'indice maximum pour $i$ est donc $n-3$.  
2\. \*\*Programmation :\*\* \`print(L\[i\], L\[j\], L\[k\])\`

\---

\#\# Résumé global \+ Conseils

\* \*\*Différence clé :\*\* Permutations \= l'ordre compte ($A,B \\neq B,A$). Parties \= l'ordre ne compte pas ($\\left\\{A,B\\right\\} \= \\left\\{B,A\\right\\}$).  
\* \*\*Structure algorithmique :\*\* Pour générer des parties de taille $k$, on utilise $k$ boucles imbriquées.  
\* \*\*Complexité :\*\* Le nombre de parties augmente très vite avec $n$. $\\binom{n}{k}$ est maximal quand $k \\approx n/2$.  
