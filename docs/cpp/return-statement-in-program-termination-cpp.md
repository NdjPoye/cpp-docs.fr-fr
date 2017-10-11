---
title: Instruction return dans la terminaison du programme (C++) | Documents Microsoft
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
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: f5ba078ef364a046a9e635d8b2632558e426f4b8
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="return-statement-in-program-termination-c"></a>Instruction return dans la terminaison du programme (C++)
Émettre un `return` instruction à partir de **principal** est fonctionnellement équivalente à l’appel le **quitter** (fonction). Prenons l'exemple suivant :  
  
```  
// return_statement.cpp  
#include <stdlib.h>  
int main()  
{  
    exit( 3 );  
    return 3;  
}  
```  
  
 Le **quitter** et `return` dans l’exemple précédent, les instructions sont fonctionnellement identiques. Toutefois, C++ exige que les fonctions dont les types de retour sont différents de `void` retournent une valeur. Le `return` instruction vous permet de retourner une valeur à partir de **principal**.  
  
## <a name="see-also"></a>Voir aussi  
 [Terminaison du programme](../cpp/program-termination.md)
