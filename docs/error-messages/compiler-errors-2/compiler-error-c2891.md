---
title: Erreur du compilateur C2891 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2891
dev_langs:
- C++
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 979d77ad5b5bd0b68dd539695d6cb1b60b099c55
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2891"></a>Erreur du compilateur C2891
'paramètre' : ne peut pas prendre l’adresse d’un paramètre de modèle  
  
 Vous ne pouvez pas prendre l’adresse d’un paramètre de modèle, sauf si elle est une lvalue. Paramètres de type ne sont pas lvalues, car ils n’ont aucun adresse. Également, les valeurs non-type dans les listes de paramètres de modèle qui ne sont pas des valeurs lvalues n’ont pas d’une adresse. Il s’agit d’un exemple de code qui provoque l’erreur du compilateur C2891, car la valeur passée comme paramètre de modèle est une copie généré par le compilateur de l’argument de modèle.  
  
```  
template <int i> int* f() { return &i; }  
```  
  
 Les paramètres de modèle sont des lvalues, tels que des types référence, permettre avoir leur adresse effectuées.  
  
```  
template <int& r> int* f() { return &r; }  
```  
  
 Pour corriger cette erreur, ne prennent pas l’adresse d’un paramètre de modèle, sauf si elle est une lvalue.