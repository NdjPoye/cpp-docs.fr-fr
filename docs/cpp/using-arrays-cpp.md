---
title: "Utilisation de tableaux (C++) | Microsoft Docs"
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
helpviewer_keywords: 
  - "tableaux (C++)"
ms.assetid: 7818a7fe-7e82-4881-a3d1-7d25162b7fc7
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de tableaux (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez accéder à des éléments d'un tableau en utilisant l'opérateur d'indice de tableau \(`[ ]`\).  Si un tableau unidimensionnel est utilisé dans une expression sans indice, le nom de tableau correspond à un pointeur au premier élément du tableau.  
  
```  
// using_arrays.cpp  
int main() {  
   char chArray[10];  
   char *pch = chArray;   // Evaluates to a pointer to the first element.  
   char   ch = chArray[0];   // Evaluates to the value of the first element.  
   ch = chArray[3];   // Evaluates to the value of the fourth element.  
}  
```  
  
 Lorsque vous utilisez des tableaux multidimensionnels, vous pouvez utiliser différentes combinaisons dans des expressions.  
  
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
  
 Dans le code précédent, `multi` est un tableau à trois dimensions de type `double`.  Le pointeur `p2multi` pointe vers un tableau de type `double` de taille trois.  Dans cet exemple, le tableau est utilisé avec un, deux, et trois indices.  Bien qu'il soit plus courant de spécifier tous les indices, comme dans l'instruction `cout`, il est parfois utile de sélectionner un sous\-ensemble spécifique d'éléments de tableau, comme indiqué dans les instructions qui suivent `cout`.  
  
## Voir aussi  
 [Tableaux](../cpp/arrays-cpp.md)