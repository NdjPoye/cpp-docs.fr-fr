---
title: "noalias | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "noalias"
  - "noalias_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++), noalias"
  - "noalias __declspec (mot clé)"
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# noalias
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 `noalias` signifie qu'un appel de fonction ne modifie pas ou ne référence pas l'état global visible et modifie uniquement la mémoire pointée `directly` par les paramètres de pointeur \(indirections de premier niveau\).  
  
 Si une fonction est annotée comme `noalias`, l'optimiseur peut supposer que, en plus des paramètres proprement dits, seuls les indirections de premier niveau des paramètres de pointeur sont référencées ou modifiées dans la fonction.  L'état global visible est l'ensemble de toutes les données qui ne sont pas définies ou référencées en dehors de la portée de compilation, et leur adresse n'est pas prise.  La portée de compilation est constituée de tous les fichiers sources \(builds [\/LTCG \(Génération de code durant l'édition de liens\)](../build/reference/ltcg-link-time-code-generation.md)\) ou d'un fichier source unique \(build non\-**\/LTCG**\).  
  
## Exemple  
 L'exemple suivant illustre l'utilisation de `__declspec(restrict)` et `__declspec(noalias)`.  Normalement, la mémoire retournée à partir de `malloc` est `restrict` et `noalias` car les en\-têtes CRT sont décorés correctement.  
  
 Toutefois, dans cet exemple, les pointeurs `mempool` et `memptr`  sont globaux. Le compilateur n'a par conséquent aucune assurance que la mémoire ne fait pas l'objet de l'attribut d'un alias.  Le fait de décorer les fonctions qui retournent des pointeurs avec `__declspec(restrict)` indique au compilateur que la mémoire vers laquelle pointe la valeur de retour n'a pas d'alias.  
  
 Le fait de décorer la fonction dans l'exemple qui accède à la mémoire avec `__declspec(noalias)` indique au compilateur que cette fonction n'interfère pas avec l'état global, hormis par l'intermédiaire des pointeurs dans sa liste de paramètres.  
  
```  
// declspec_noalias.c   
#include <stdio.h>  
#include <stdlib.h>  
  
#define M 800  
#define N 600  
#define P 700  
  
float * mempool, * memptr;  
  
__declspec(restrict) float * ma(int size)  
{  
    float * retval;  
    retval = memptr;  
    memptr += size;  
    return retval;  
}  
  
__declspec(restrict) float * init(int m, int n)  
{  
    float * a;  
    int i, j;  
    int k=1;  
  
    a = ma(m * n);  
    if (!a) exit(1);  
    for (i=0; i<m; i++)  
        for (j=0; j<n; j++)  
            a[i*n+j] = 0.1/k++;  
    return a;  
}  
  
__declspec(noalias) void multiply(float * a, float * b, float * c)  
{  
    int i, j, k;  
  
    for (j=0; j<P; j++)  
        for (i=0; i<M; i++)  
            for (k=0; k<N; k++)  
                c[i * P + j] =   
                          a[i * N + k] *   
                          b[k * P + j];  
}  
  
int main()  
{  
    float * a, * b, * c;  
  
    mempool = (float *) malloc(sizeof(float) * (M*N + N*P + M*P));  
  
    if (!mempool)   
    {  
        puts("ERROR: Malloc returned null");  
        exit(1);  
    }  
  
    memptr = mempool;  
    a = init(M, N);  
    b = init(N, P);  
    c = init(M, P);  
  
    multiply(a, b, c);  
}  
```  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)