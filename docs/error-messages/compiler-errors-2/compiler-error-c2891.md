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
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6c35294472fe4142e7e6689adfc5f5f71c27b664
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

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
