---
title: "vector&lt;bool&gt;::reference::flip | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vector<bool>::reference::flip"
  - "std::vector<bool>::reference::flip"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reference::flip (méthode)"
ms.assetid: ef940365-cbe4-4a87-a3e2-1f3cfa357e29
caps.latest.revision: 21
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# vector&lt;bool&gt;::reference::flip
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Inverse la valeur booléenne d'un élément [vector\<bool\>](../standard-library/vector-bool-class.md) référencé.  
  
## Syntaxe  
  
```  
void flip();  
```  
  
## Exemple  
  
```cpp  
// vector_bool_ref_flip.cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    cout << boolalpha;  
  
    vector<bool> vb = { true, false, false, true, true };  
  
    cout << "The vector is: " << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
  
    vector<bool>::reference vbref = vb.front();  
    vbref.flip();  
  
    cout << "The vector with first element flipped is: " << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
}  
  
```  
  
## Sortie  
  
```  
The vector is:  
    true false false true true  
The vector with first element flipped is:  
    false false false true true  
```  
  
## Configuration requise  
 **En\-tête :** \<vector\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [vector\<bool\>::reference, classe](../standard-library/vector-bool-reference-class.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)