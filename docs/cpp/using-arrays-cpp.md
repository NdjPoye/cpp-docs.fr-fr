---
title: Utilisation des tableaux (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arrays [C++]
ms.assetid: 7818a7fe-7e82-4881-a3d1-7d25162b7fc7
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 31402e2f113deb89fce6d2d8b6c3633f06a944be
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="using-arrays-c"></a>Utilisation de tableaux (C++)
Vous pouvez accéder à des éléments individuels d’un tableau à l’aide de l’opérateur d’indice de tableau (`[ ]`). Si un tableau unidimensionnel est utilisé dans une expression qui ne comporte aucun indice, le nom du tableau a la valeur un pointeur vers le premier élément du tableau.  
  
```  
// using_arrays.cpp  
int main() {  
   char chArray[10];  
   char *pch = chArray;   // Evaluates to a pointer to the first element.  
   char   ch = chArray[0];   // Evaluates to the value of the first element.  
   ch = chArray[3];   // Evaluates to the value of the fourth element.  
}  
```  
  
 Lorsque vous utilisez des tableaux multidimensionnels, vous pouvez utiliser différentes combinaisons dans les expressions.  
  
```  
// using_arrays_2.cpp  
// compile with: /EHsc /W1  
#include <iostream>  
using namespace std;  
int main() {  
   double multi[4][4][3];   // Declare the array.  
   double (*p2multi)[3];  
   double (*p1multi);  
  
   cout << multi[3][2][2] << "\n";   // C4700 Use three subscripts.  
   p2multi = multi[3];               // Make p2multi point to  
                                     // fourth "plane" of multi.  
   p1multi = multi[3][2];            // Make p1multi point to  
                                     // fourth plane, third row  
                                     // of multi.  
}  
```  
  
 Dans le code précédent, `multi` est un tableau à trois dimensions de type `double`. Le `p2multi` pointeur pointe vers un tableau de type `double` de taille de trois. Dans cet exemple, le tableau est utilisé avec un, deux et trois indices. Bien qu’il soit plus courant pour spécifier tous les indices, comme dans le `cout` instruction, il est parfois utile de sélectionner un sous-ensemble spécifique d’éléments de tableau, comme indiqué dans les instructions qui suivent `cout`.  
  
## <a name="see-also"></a>Voir aussi  
 [Tableaux](../cpp/arrays-cpp.md)
