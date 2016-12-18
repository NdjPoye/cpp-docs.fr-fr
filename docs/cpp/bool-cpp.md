---
title: "bool (C++) | Microsoft Docs"
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
  - "bool_cpp"
  - "bool"
  - "__BOOL_DEFINED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__BOOL_DEFINED (macro)"
  - "bool (mot clé) (C++)"
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# bool (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ce mot clé est un type intégré.  Une variable de ce type peut avoir les valeurs [true](../cpp/true-cpp.md) et [false](../cpp/false-cpp.md).  Les expressions conditionnelles sont de type `bool` et ont ainsi des valeurs de type `bool`.  Par exemple, `i!=0` a maintenant la valeur **true** ou **false** selon la valeur de `i`.  
  
 Les valeurs **true** et **false** ont la relation suivante :  
  
```  
!false == true  
!true == false  
```  
  
 Dans l'instruction suivante :  
  
```  
if (condexpr1) statement1;   
```  
  
 Si `condexpr1` est **true**, `statement1` est toujours exécuté ; si `condexpr1` est **false**, `statement1` n'est jamais exécuté.  
  
 Lorsqu'un opérateur `++` de préfixe ou de suffixe est appliqué à une variable de type `bool`, la variable a la valeur **true**.  L'opérateur `--` de préfixe ou de suffixe ne peut pas s'appliquer à une variable de ce type.  
  
 Le type `bool` participe aux promotions intégrales.  Une r\-value de type `bool` peut être convertie en une r\-value de type `int`, avec **false** devenant zéro et **true** devenant un.  En tant que type distinct, `bool` participe à la résolution de la surcharge.  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Types fondamentaux](../cpp/fundamental-types-cpp.md)