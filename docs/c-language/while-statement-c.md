---
title: Instruction while (C) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- while
dev_langs:
- C++
helpviewer_keywords:
- while keyword [C]
- while keyword [C], syntax
ms.assetid: d0c970b8-12a9-4827-afb2-a051111834b7
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: e383ae0646bdf15c38f6537de0adec9bb9468486
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="while-statement-c"></a>while, instruction (C)
L'instruction `while` vous permet de répéter une instruction jusqu'à ce qu'une expression spécifiée devienne false.  
  
## <a name="syntax"></a>Syntaxe  
 *itération-instruction* :  
 **while (**  *expression*  **)**  *statement*  
  
 L'élément *expression* doit être de type arithmétique ou pointeur. L'exécution se déroule comme suit :  
  
1.  L'élément *expression* est évalué.  
  
2.  Si l'élément *expression* est initialement false, le corps de l'instruction `while` n'est jamais exécuté et le contrôle passe de l'instruction `while` à l'instruction suivante dans le programme.  
  
     Si l'élément *expression* est true (différent de zéro), le corps de l'instruction est exécuté et le processus est répété à partir de l'étape 1.  
  
 L'instruction `while` peut également se terminer lorsqu'une instruction **break**, `goto` ou `return` est exécutée dans le corps de l'instruction. Utilisez l'instruction **continue** pour terminer une itération sans quitter la boucle de `while`. L'instruction **continue** passe le contrôle à l'itération suivante de l'instruction `while`.  
  
 Voici un exemple d'instruction `while` :  
  
```  
while ( i >= 0 )   
{  
    string1[i] = string2[i];  
    i--;  
}  
```  
  
 Cet exemple copie des caractères de `string2` à `string1`. Si `i` est supérieur ou égal à 0, `string2[i]` est assigné à `string1[i]` et `i` est décrémenté. Lorsque `i` atteint 0 ou une valeur inférieure, l'exécution de l'instruction `while` se termine.  
  
## <a name="see-also"></a>Voir aussi  
 [while, instruction (C++)](../cpp/while-statement-cpp.md)
