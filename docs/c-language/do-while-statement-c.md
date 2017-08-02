---
title: Instruction do-while (C) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- do
- while
dev_langs:
- C++
helpviewer_keywords:
- do-while keyword [C]
ms.assetid: f2ac20a6-10c7-4a08-b5e3-c3b3639dbeaf
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
ms.openlocfilehash: 9ea9e9c4cfdf57709cd125f8269657d37393cc61
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="do-while-statement-c"></a>do-while, instruction (C)
L'instruction `do-while` vous permet de répéter une instruction ou une instruction composée jusqu'à ce qu'une expression spécifiée devienne false.  
  
## <a name="syntax"></a>Syntaxe  
 *itération-instruction* :  
 **do**  *statement*  **while (**  *expression*  **) ;**  
  
 L'élément *expression* dans une instruction `do-while` est évalué après l'exécution du corps de la boucle. Par conséquent, le corps de la boucle est toujours exécuté au moins une fois.  
  
 L'élément *expression* doit être de type arithmétique ou pointeur. L'exécution se déroule comme suit :  
  
1.  Le corps de l'instruction est exécuté.  
  
2.  Ensuite, l'élément *expression* est évalué. Si l'élément *expression* est false, l'instruction `do-while` se termine et le contrôle passe à l'instruction suivante du programme. Si l'élément *expression* est true (différent de zéro), le processus se répète, en commençant à l'étape 1.  
  
 L'instruction `do-while` peut également se terminer lorsqu'une instruction **break**, `goto` ou `return` est exécutée dans le corps de l'instruction.  
  
 Voici un exemple d'instruction `do-while` :  
  
```  
do   
{  
    y = f( x );  
    x--;  
} while ( x > 0 );  
```  
  
 Dans cette instruction `do-while`, les deux instructions `y = f( x );` et `x--;` sont exécutées, quelle que soit la valeur initiale de `x`. Ensuite, `x > 0` est évalué. Si `x` est supérieur à 0, le corps de l'instruction est réexécuté et `x > 0` est réévalué. Le corps de l'instruction est exécuté à plusieurs reprises tant que `x` reste supérieur à 0. L'exécution de l'instruction `do-while` se termine lorsque `x` devient 0 ou négatif. Le corps de la boucle est exécuté au moins une fois.  
  
## <a name="see-also"></a>Voir aussi  
 [do-while, instruction (C++)](../cpp/do-while-statement-cpp.md)
