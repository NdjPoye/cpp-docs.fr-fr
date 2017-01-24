---
title: "inner_product (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::inner_product"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "inner_product (fonction) (STL/CLR)"
ms.assetid: 97d7a507-7494-4216-aedf-0546ed0edb3f
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# inner_product (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Calcule la somme du produit selon l'élément de plusieurs plages et l'ajoute à une valeur initiale spécifiée ou calcule le résultat d'une procédure généralisée où les opérations de somme et de produit binaire sont remplacées par d'autres opérations binaire spécifiées.  
  
## Syntaxe  
  
```  
template<class _InIt1, class _InIt2, class _Ty> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val);  
template<class _InIt1, class _InIt2, class _Ty, class _Fn21,  
       class _Fn22> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val, _Fn21 _Func1, _Fn22 _Func2);  
```  
  
## Notes  
 Cette fonction se comporte comme la fonction numérique STL de `inner_product` Pour plus d'informations, consultez [inner\_product](../Topic/inner_product.md).  
  
## Configuration requise  
 **En\-tête:** \<cliext\/numericc&gt;  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [numériques](../dotnet/numeric-stl-clr.md)