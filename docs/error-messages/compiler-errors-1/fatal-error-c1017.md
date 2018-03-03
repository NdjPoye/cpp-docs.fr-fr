---
title: "Erreur irrécupérable C1017 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1017
dev_langs:
- C++
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e28a4b09ef4d62edd97d734e4a3ad64b8a0c2f86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1017"></a>Erreur irrécupérable C1017
expression constante entière non valide  
  
 L’expression dans une `#if` directive n’existe pas ou ne correspond pas à une constante.  
  
 Constantes définies à l’aide de `#define` doivent avoir des valeurs qui correspondent à une constante entière si elles sont utilisées dans un `#if`, `#elif`, ou `#else` la directive.  
  
 L’exemple suivant génère l’erreur C1017 :  
  
```  
// C1017.cpp  
#define CONSTANT_NAME "YES"  
#if CONSTANT_NAME   // C1017  
#endif  
```  
  
 Solution possible :  
  
```  
// C1017b.cpp  
// compile with: /c  
#define CONSTANT_NAME 1  
#if CONSTANT_NAME  
#endif  
```  
  
 Étant donné que `CONSTANT_NAME` prend la valeur en une chaîne et non pas un entier, la `#if` directive génère l’erreur irrécupérable C1017.  
  
 Dans d’autres cas, le préprocesseur évalue une constante non définie en tant que zéro. Cela peut entraîner des résultats inattendus, comme indiqué dans l’exemple suivant. `YES`n’est pas défini, il correspond à zéro. L’expression `#if` `CONSTANT_NAME` prend la valeur false et le code à utiliser sur `YES` est supprimé par le préprocesseur. `NO`est également non définie (zéro), par conséquent, `#elif` `CONSTANT_NAME==NO` a la valeur true (`0 == 0`), et le préprocesseur laisse le code dans la `#elif` partie de l’instruction — exactement le contraire du comportement prévu.  
  
```  
// C1017c.cpp  
// compile with: /c  
#define CONSTANT_NAME YES  
#if CONSTANT_NAME  
   // Code to use on YES...  
#elif CONSTANT_NAME==NO  
   // Code to use on NO...  
#endif  
```  
  
 Pour voir exactement comment le compilateur gère les directives de préprocesseur, utilisez [/P](../../build/reference/p-preprocess-to-a-file.md), [/E](../../build/reference/e-preprocess-to-stdout.md), ou [/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md).