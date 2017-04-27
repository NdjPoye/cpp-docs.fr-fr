---
title: "Utilisation des opérateurs additifs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], addition
- additive operators
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 04e23f9694193a05d48b7fcdff717d06e448e877
ms.lasthandoff: 04/01/2017

---
# <a name="using-the-additive-operators"></a>Utilisation des opérateurs additifs
Les exemples suivants, qui illustrent les opérateurs d'addition et de soustraction, utilisent ces déclarations :  
  
```  
int i = 4, j;  
float x[10];  
float *px;  
```  
  
 Ces instructions sont équivalentes :  
  
```  
px = &x[4 + i];  
px = &x[4] + i;    
```  
  
 La valeur de `i` est multipliée par la longueur d’un **float** et ajoutée à `&x[4]`. La valeur de pointeur résultante est l'adresse de `x[8]`.  
  
```  
j = &x[i] - &x[i-2];  
```  
  
 Dans cet exemple, l'adresse du troisième élément de `x` (donné par `x[i-2]`) est ensuite soustraite dans l'adresse du cinquième élément de `x` (donné par `x[i]`). La différence est divisée par la longueur d’un **float** ; le résultat est la valeur entière 2.  
  
## <a name="see-also"></a>Voir aussi  
 [Opérateurs additifs C](../c-language/c-additive-operators.md)
