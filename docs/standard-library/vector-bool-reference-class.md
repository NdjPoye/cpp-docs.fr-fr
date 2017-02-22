---
title: "vector&lt;bool&gt;::reference, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vector<bool>::reference"
  - "std::vector<bool>::reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vector<bool> (classe de référence)"
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# vector&lt;bool&gt;::reference, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe `vector<bool>::reference` est une classe proxy fournie par la [classe vector\<bool\>](../standard-library/vector-bool-class.md)pour simuler `bool&`.  
  
## Notes  
 Une référence simulée est requise car C\+\+ n'autorise pas en mode natif les références directes aux bits.  `vector<bool>` utilise un seul bit par élément, lequel peut être référencé à l'aide de cette classe proxy.  Toutefois, la simulation de référence n'est pas terminée car certaines attributions ne sont pas valides.  Par exemple, comme l'adresse de l'objet `vector<bool>::reference` ne peut pas être prise, le code suivant qui utilise [vector\<bool\>::operator&#91;&#93;](../Topic/vector%3Cbool%3E::operator.md) n'est pas correct :  
  
```cpp  
    vector<bool> vb;  
...  
    bool* pb = &vb[1]; // conversion error - do not use  
    bool& refb = vb[1];   // conversion error - do not use  
  
```  
  
### Fonctions membres  
  
|||  
|-|-|  
|[flip](../standard-library/vector-bool-reference-flip.md)|Inverse la valeur booléenne d'un élément de vecteur.|  
|[operator bool](../standard-library/vector-bool-reference-operator-bool.md)|Fournit une conversion implicite de `vector<bool>::reference` en `bool`.|  
|[operator\=](../standard-library/vector-bool-reference-operator-assign.md)|Assigne une valeur booléenne à un bit, ou la valeur détenue par un élément référencé à un bit.|  
  
## Conditions requises  
 **En\-tête :** \<vector\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<vector\>](../standard-library/vector.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)