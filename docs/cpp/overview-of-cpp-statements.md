---
title: "Vue d’ensemble des instructions C++ | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements, C++
ms.assetid: e56996b2-b846-4b99-ac94-ac72fffc5ec7
caps.latest.revision: 6
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 4977d508beeedd7a2fa9f20e9822e6fa6cd61e47
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="overview-of-c-statements"></a>Vue d'ensemble des instructions C++
Les instructions C++ sont exécutées séquentiellement, sauf lorsqu'une instruction d'expression, une instruction de sélection, une instruction d'itération ou une instruction de saut modifie spécifiquement cette séquence.  
  
 Les instructions peuvent être des types suivants :  
  
```  
  
labeled-statement  
expression-statement  
compound-statement  
selection-statement  
iteration-statement  
jump-statement  
declaration-statement  
try-throw-catch  
  
```  
  
 Dans la plupart des cas, la syntaxe d’instruction C++ est identique à celle d’ANSI C. La principale différence entre les deux est qui dans C, les déclarations sont autorisées uniquement au début d’un bloc ; C++ ajoute le *instruction de déclaration*, ce qui élimine cette restriction. Cela vous permet d'entrer des variables à un point du programme où une valeur d'initialisation précalculée peut être calculée.  
  
 La déclaration de variables à l'intérieur de blocs vous permet également d'exercer un contrôle précis sur la portée et la durée de vie de ces variables.  
  
 Les rubriques sur les instructions décrivent les mots clés C++ suivants :  
  
|||||  
|-|-|-|-|  
|[break](../cpp/break-statement-cpp.md)|[else](../cpp/if-else-statement-cpp.md)|[__if_exists](../cpp/if-exists-statement.md)|[__try](../cpp/structured-exception-handling-c-cpp.md)|  
|[case](../cpp/switch-statement-cpp.md)|[__except](../cpp/structured-exception-handling-c-cpp.md)|[__if_not_exists](../cpp/if-not-exists-statement.md)|[try](../cpp/try-throw-and-catch-statements-cpp.md)|  
|[catch](../cpp/try-throw-and-catch-statements-cpp.md)|[for](../cpp/for-statement-cpp.md)|[__leave](../c-language/try-finally-statement-c.md)|[while](../cpp/while-statement-cpp.md)|  
|[continue](../cpp/continue-statement-cpp.md)|[goto](../cpp/goto-statement-cpp.md)|[return](../cpp/return-statement-cpp.md)||  
|[default](../cpp/switch-statement-cpp.md)|[__finally](../cpp/structured-exception-handling-c-cpp.md)|[switch](../cpp/switch-statement-cpp.md)||  
|[do](../cpp/do-while-statement-cpp.md)|[if](../cpp/if-else-statement-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)||  
  
## <a name="see-also"></a>Voir aussi  
 [Instructions](../cpp/statements-cpp.md)
