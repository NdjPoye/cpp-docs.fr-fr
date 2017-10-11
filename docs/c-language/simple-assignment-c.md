---
title: Assignation simple (C) | Microsoft Docs
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
- type conversion [C++], simple assignment
- data type conversion [C++], simple assignment
- operators [C], simple assignment
- assignment operators [C++], simple
- simple assignment operator
- equal sign
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: c6f81732b4fccdac6ae0912b7617c28318da3e55
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="simple-assignment-c"></a>Assignation simple (C)
L’opérateur d’assignation simple assigne son opérande droit à son opérande gauche. La valeur de l’opérande droit est convertie dans le type de l’expression d’assignation et remplace la valeur stockée dans l’objet désigné par l’opérande gauche. Les règles de conversion relatives à l'assignation sont applicables (consultez [Conversions d'assignation](../c-language/assignment-conversions.md)).  
  
```  
double x;  
int y;  
  
x = y;  
```  
  
 Dans cet exemple, la valeur de `y` est convertie en type **double** et assignée à `x`.  
  
## <a name="see-also"></a>Voir aussi  
 [Opérateurs d’assignation C](../c-language/c-assignment-operators.md)
