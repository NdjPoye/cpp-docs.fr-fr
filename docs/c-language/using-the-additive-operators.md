---
title: "Utilisation des opérateurs additifs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
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
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 9f2bdbc6a22754587dce3cb2a4c9b2baf12a1a1f
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

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
