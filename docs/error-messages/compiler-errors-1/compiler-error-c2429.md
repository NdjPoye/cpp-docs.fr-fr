---
title: "C2429 d’erreur du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2429
dev_langs:
- C++
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 18fd64199ff043b660bb205199b982ee2843cdcd
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2429"></a>C2429 d’erreur du compilateur
'*fonctionnalité de langage*'requiert l’indicateur de compilateur'*option du compilateur*'  
  
La fonctionnalité de langage requiert une option du compilateur spécifique pour la prise en charge.  
  
L’erreur C2429 : fonctionnalité de langage 'nested-namespace-definition' nécessite l’indicateur de compilateur ' / std:c ++ dernières » est générée si vous essayez de définir un *espace de noms composé*, un espace de noms qui contient un ou plusieurs noms d’espace de noms imbriqué à portée , à partir de Visual Studio 2015 Update 3. Compound, espace de noms définitions ne sont pas autorisées en C++ avant C ++ 17. Le compilateur prend en charge les définitions de l’espace de noms composé lorsque le [/std : c ++ dernière](../../build/reference/std-specify-language-standard-version.md) option du compilateur est spécifiée :  
```cpp  
// C2429a.cpp  
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.  
                          // Use /std:c++latest to fix, or do this:  
// namespace a { namespace b { int i; }}  
  
int main() {  
   a::b::i = 2;  
}  
```  
