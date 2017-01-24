---
title: "Bas&#233; sur une plage, instruction (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 5750ba1d-ba48-4236-a923-e32de8345c2d
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Bas&#233; sur une plage, instruction (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Exécute le `statement` à plusieurs reprises et séquentiellement pour chaque élément de `expression`.  
  
## Syntaxe  
  
```  
  
      for ( for-range-declaration : expression )  
   statement   
```  
  
## Notes  
 Utilisez l'instruction `for` basée sur une portée pour construire des boucles qui doivent exécuter dans une « portée », qui est définie comme tout ce que vous pouvez itérer à travers \- par exemple, `std::vector`, ou toute autre séquence STL dont la plage est définie par `begin()` et `end()`.  Le nom déclaré dans la partie `for-range-declaration` est locale à l'instruction `for` et ne peut pas être de nouveau déclaré dans `expression` ou `statement`.  Notez que le mot clé [automatique](../cpp/auto-cpp.md) est recommandé dans la partie `for-range-declaration` de l'instruction.  
  
 Ce code montre comment utiliser les boucles étendues d'un `for` pour itérer au sein d'un tableau et un vecteur :  
  
```cpp  
  
// range-based-for.cpp  
// compile by using: cl /EHsc /nologo /W4  
#include <iostream>  
#include <vector>  
using namespace std;  
  
int main()   
{  
    // Basic 10-element integer array.  
    int x[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };  
  
    // Range-based for loop to iterate through the array.  
    for( int y : x ) { // Access by value using a copy declared as a specific type.   
                       // Not preferred.  
        cout << y << " ";  
    }  
    cout << endl;  
  
    // The auto keyword causes type inference to be used. Preferred.  
  
    for( auto y : x ) { // Copy of 'x', almost always undesirable  
        cout << y << " ";  
    }  
    cout << endl;  
  
    for( auto &y : x ) { // Type inference by reference.  
        // Observes and/or modifies in-place. Preferred when modify is needed.  
        cout << y << " ";  
    }  
    cout << endl;  
  
    for( const auto &y : x ) { // Type inference by reference.  
        // Observes in-place. Preferred when no modify is needed.  
        cout << y << " ";  
    }  
    cout << endl;  
    cout << "end of integer array test" << endl;  
    cout << endl;  
  
    // Create a vector object that contains 10 elements.  
    vector<double> v;  
    for (int i = 0; i < 10; ++i) {  
        v.push_back(i + 0.14159);  
    }  
  
    // Range-based for loop to iterate through the vector, observing in-place.  
    for( const auto &j : v ) {  
        cout << j << " ";  
    }  
    cout << endl;  
    cout << "end of vector test" << endl;  
}  
  
```  
  
 Le balisage se présente comme suit :  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `end of integer array test`  
  
 `0.14159 1.14159 2.14159 3.14159 4.14159 5.14159 6.14159 7.14159 8.14159 9.14159`  
  
 `end of vector test`  
  
 Une boucle basée sur une portée `for` se termine lorsque l'un des `statement` suivant est exécuté : [saut](../cpp/break-statement-cpp.md), [retour](../cpp/return-statement-cpp.md), ou [goto](../cpp/goto-statement-cpp.md) à une instruction étiquetée hors de la boucle basée sur une portée **for**.  Une instruction [Continuer](../cpp/continue-statement-cpp.md) dans une boucle basée sur une portée `for` termine uniquement l'itération actuelle.  
  
 Gardez à l'esprit ces faits sur les `for`basés sur une portée :  
  
-   Identifie automatiquement vos tableaux.  
  
-   Reconnaît vos conteneurs qui ont `.begin()` et `.end()`.  
  
-   Utilise les recherches dépendant d'arguments `begin()` et `end()` pour tout le reste.  
  
## Voir aussi  
 [auto](../cpp/auto-cpp.md)   
 [Instructions d'itération](../cpp/iteration-statements-cpp.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [while, instruction \(C\+\+\)](../cpp/while-statement-cpp.md)   
 [do\-while, instruction \(C\+\+\)](../cpp/do-while-statement-cpp.md)   
 [for, instruction \(C\+\+\)](../cpp/for-statement-cpp.md)