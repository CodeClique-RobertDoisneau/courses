\# Chapitre 2 \- Partie 1 : Génération des permutations d’un ensemble fini

\#\# INTRODUCTION  
Dans ce chapitre, nous étudions comment manipuler l'ordre des éléments d'un ensemble fini. Cette notion est fondamentale en combinatoire (dénombrement) et en informatique, que ce soit pour tester toutes les possibilités d'un problème ou pour simuler des phénomènes aléatoires (jeux de cartes, échantillonnage).

\#\#\# Définitions  
\* \*\*Permutation :\*\* Soit E un ensemble fini de n éléments. Une permutation de E est une liste ordonnée contenant tous les éléments de E une et une seule fois.   
\* \*\*Dénombrement :\*\* Le nombre de permutations d'un ensemble à n éléments est donné par la factorielle de n, notée n\! :

$$n\! \= n \\times (n-1) \\times (n-2) \\times \\dots \\times 2 \\times 1$$

Par convention, $0\! \= 1$.

\---

\#\# Algorithme \- Cas 1 : Génération systématique (exhaustive)

\#\#\# Idée générale  
⇒ L'objectif est de lister toutes les permutations possibles sans en oublier aucune. On utilise une approche récursive basée sur un arbre de choix : on fixe un premier élément, puis on recommence le processus avec les éléments restants.

\#\#\# Méthode générale  
\* \*\*Cas de base :\*\* Si l'ensemble ne contient qu'un élément, la seule permutation est l'élément lui-même.  
\* \*\*Hérédité (Récursion) :\*\* Pour générer les permutations d'un ensemble E :  
    \* Pour chaque élément x de E :  
        1\. Placer x en première position.  
        2\. Générer toutes les permutations de l'ensemble E∖{x}.  
        3\. Associer x à chacune de ces permutations.

\#\#\# Exemples pour visualiser  
Pour E={A,B,C}, on a $3\! \= 6$ permutations :  
\* On fixe A : il reste {B,C}. On peut avoir (B,C) ou (C,B).  
    \* Résultats : (A,B,C) et (A,C,B).  
\* On fixe B : il reste {A,C}. On peut avoir (A,C) ou (C,A).  
    \* Résultats : (B,A,C) et (B,C,A).  
\* On fixe C : il reste {A,B}. On peut avoir (A,B) ou (B,A).  
    \* Résultats : (C,A,B) et (C,B,A).

\#\#\# → EXERCICES d’application directs  
\* \*\*Calcul :\*\* Calculez 5\! et déduisez-en le nombre de façons d'ordonner 5 livres sur une étagère.  
\* \*\*Logique :\*\* Si on génère les permutations de {1,2,3,4,5}, combien de permutations commencent par le chiffre 3 ?  
\* \*\*Représentation :\*\* Dessinez l'arbre complet des permutations pour l'ensemble {1,2,3}.

\*\* CORRECTIONS :\*\*  
\* \*\*Calcul :\*\* $5\! \= 5 \\times 4 \\times 3 \\times 2 \\times 1 \= 120$. Il y a donc 120 façons différentes d'ordonner ces 5 livres sur l'étagère.  
\* \*\*Logique :\*\* Si le chiffre 3 est fixé en première position, il reste 4 éléments $\\{1, 2, 4, 5\\}$ à ordonner. Le nombre de permutations pour ces 4 éléments restants est de $4\! \= 24$. Il y a donc 24 permutations qui commencent par le chiffre 3\.  
\* \*\*Représentation :\*\*  
    \* \*\*Choix 1 :\*\* On fixe 1 $\\rightarrow$ Reste $\\{2, 3\\} \\rightarrow$ Branches finales : (1, 2, 3\) et (1, 3, 2\)  
    \* \*\*Choix 2 :\*\* On fixe 2 $\\rightarrow$ Reste $\\{1, 3\\} \\rightarrow$ Branches finales : (2, 1, 3\) et (2, 3, 1\)  
    \* \*\*Choix 3 :\*\* On fixe 3 $\\rightarrow$ Reste $\\{1, 2\\} \\rightarrow$ Branches finales : (3, 1, 2\) et (3, 2, 1\)

\---

\#\# Algorithme \- Cas 2 : Tirage aléatoire (Mélange de Fisher-Yates)

\#\#\# Idée générale  
⇒ Lorsque n est grand, il est impossible de lister toutes les permutations (ex: 52\! pour un jeu de cartes). On cherche alors à obtenir une seule permutation au hasard, de manière "équiprobable" (chaque permutation doit avoir la même chance de sortir).

\#\#\# Méthode générale (Algorithme de Knuth / Fisher-Yates)  
On parcourt la liste de la fin vers le début et on procède à des échanges :  
1\.  Soit une liste L de n éléments (indices de 0 à n−1).  
2\.  Pour i allant de n−1 à 1 (par pas de \-1) :  
    \* Choisir un entier aléatoire j tel que $0 \\le j \\le i$.  
    \* Échanger les éléments situés aux indices i et j.

\#\#\# Exemples pour visualiser  
Mélangeons \[X,Y,Z\] (indices 0, 1, 2\) :  
\* Étape 1 (i=2) : On choisit j entre 0 et 2\. Supposons j=0. On échange L\[2\] et L\[0\].  
    \* La liste devient \[Z,Y,X\]. L'élément X est "fixé" à sa place finale.  
\* Étape 2 (i=1) : On choisit j entre 0 et 1\. Supposons j=1. On échange L\[1\] et L\[1\] (pas de changement).  
    \* La liste reste \[Z,Y,X\].  
\* Résultat : La permutation aléatoire obtenue est (Z,Y,X).

\#\#\# → EXERCICES d’application directs  
\* \*\*Simulation :\*\* Appliquez l'algorithme à la main sur la liste \[1,2,3,4\] avec les tirages successifs suivants : j=1 (pour i=3), puis j=0 (pour i=2), puis j=0 (pour i=1). Quel est le résultat final ?  
\* \*\*Analyse :\*\* Pourquoi ne tire-t-on pas j entre 0 et n−1 à chaque étape ? (Question de réflexion sur l'uniformité du mélange).

\*\* CORRECTIONS :\*\*  
\* \*\*Simulation :\*\*  
    \* État initial : \`\[1, 2, 3, 4\]\`  
    \* Étape 1 ($i=3$, $j=1$) : On échange l'indice 3 (valeur 4\) avec l'indice 1 (valeur 2). La liste devient \`\[1, 4, 3, 2\]\`.  
    \* Étape 2 ($i=2$, $j=0$) : On échange l'indice 2 (valeur 3\) avec l'indice 0 (valeur 1). La liste devient \`\[3, 4, 1, 2\]\`.  
    \* Étape 3 ($i=1$, $j=0$) : On échange l'indice 1 (valeur 4\) avec l'indice 0 (valeur 3). La liste devient \`\[4, 3, 1, 2\]\`.  
    \* \*\*Résultat final :\*\* \`\[4, 3, 1, 2\]\`  
\* \*\*Analyse :\*\* C'est pour garantir un mélange équiprobable. Si l'on tirait $j$ de $0$ à $n-1$ à chaque étape, l'algorithme effectuerait $n^n$ chemins possibles. Or, $n^n$ n'est pas un multiple de $n\!$ (le nombre total de permutations). En conséquence, le hasard serait biaisé. L'algorithme de Fisher-Yates, avec sa borne glissante $j \\le i$, offre exactement $n\!$ chemins possibles, garantissant une parfaite uniformité.

\---

\#\# Algorithme \- Cas 3 : Permutations avec éléments identiques (Anagrammes)

\#\#\# Idée générale  
⇒ Jusqu'à présent, nous avons permuté des éléments tous distincts. Mais que se passe-t-il si notre ensemble de départ contient des doublons ? L'idée est de générer (ou dénombrer) les permutations, puis d'éliminer les "doublons" créés par le fait que changer de place deux éléments identiques ne modifie pas le résultat final.

\#\#\# Méthode générale  
Pour calculer le nombre de permutations distinctes d'un ensemble de n éléments où un élément se répète $n\_1$ fois, un autre $n\_2$ fois, etc., on utilise la formule :  
$$\\frac{n\!}{n\_1\! \\times n\_2\! \\times \\dots \\times n\_k\!}$$

\#\#\# Exemples pour visualiser  
Cherchons toutes les anagrammes du mot \*\*"ELLE"\*\*.  
\* Nombre total de lettres : $n \= 4$. Donc $4\! \= 24$ permutations au total.  
\* Répétitions : La lettre 'E' apparait 2 fois ($2\! \= 2$). La lettre 'L' apparait 2 fois ($2\! \= 2$).  
\* Nombre de permutations distinctes : $\\frac{4\!}{2\! \\times 2\!} \= \\frac{24}{2 \\times 2} \= \\frac{24}{4} \= 6$.  
\* \*Vérification visuelle :\* ELLE, ELEL, EELL, LELE, LEEL, LLEE. On retrouve bien exactement 6 combinaisons.

\#\#\# → EXERCICES d’application directs  
1\. \*\*Dénombrement simple :\*\* Combien d'anagrammes distinctes peut-on former avec le mot "MATHS" ?  
2\. \*\*Dénombrement avec répétitions :\*\* Calculez le nombre d'anagrammes distinctes du mot "ANANAS".

\*\* CORRECTIONS :\*\*  
\* \*\*Dénombrement simple :\*\* Les 5 lettres de "MATHS" sont toutes distinctes. Il s'agit d'une permutation classique du Cas 1\. Le calcul est donc $5\! \= 120$.  
\* \*\*Dénombrement avec répétitions :\*\* Le mot "ANANAS" contient 6 lettres ($n=6$). Il y a des répétitions : 'A' apparait 3 fois, 'N' apparait 2 fois, et 'S' apparait 1 fois.  
Le calcul est : $\\frac{6\!}{3\! \\times 2\! \\times 1\!} \= \\frac{720}{6 \\times 2 \\times 1} \= \\frac{720}{12} \= 60$. Il y a 60 anagrammes distinctes.

\---

\#\# Résumé global \+ Conseils  
\* \*\*Complexité :\*\* La génération exhaustive (Cas 1\) a une complexité en O(n\!), ce qui devient inutilisable très vite. Le mélange aléatoire (Cas 2\) est en O(n), il est extrêmement efficace.  
\* \*\*Utilisation :\*\*  
    \* Toutes les permutations → Problèmes d'optimisation (ex: voyageur de commerce sur très peu de villes).  
    \* Une permutation aléatoire → Simulations de Monte-Carlo, jeux, cryptographie.  
    \* Permutations avec doublons → Problèmes d'anagrammes, chemins sur quadrillage.  
\* \*\*Conseils :\*\*  
    \* Attention aux indices lors de l'implémentation du mélange (la borne $j \\le i$ est cruciale).  
  