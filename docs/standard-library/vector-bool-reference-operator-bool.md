---
title: "vector&lt;bool&gt;::reference::operator bool | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "operatorbool"
  - "vector<bool>::reference::operatorbool"
  - "bool"
  - "std::vector<bool>::reference::operatorbool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BOOL (opérateur)"
  - "reference::operator bool"
ms.assetid: b0e57869-18cc-4296-9061-da502f30120d
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# vector&lt;bool&gt;::reference::operator bool
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fournit une conversion implicite de `vector<bool>::reference` en `bool`.  
  
## Syntaxe  
  
```  
operator bool( ) const;  
```  
  
## Valeur de retour  
 La valeur booléenne de l'élément de l'objet [vector\<bool\>](../standard-library/vector-bool-class.md).  
  
## Notes  
 L'objet `vector<bool>` ne peut pas être modifié par cet opérateur.  
  
## Configuration requise  
 **En\-tête :** \<vector\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [vector\<bool\>::reference, classe](../standard-library/vector-bool-reference-class.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)