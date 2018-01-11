---
title: Instruction return dans la terminaison du programme (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9a9e97c0ee52094cd3f0ccbb36c0da8b3b04c630
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="return-statement-in-program-termination-c"></a>Instruction return dans la terminaison du programme (C++)
Émettre un `return` instruction à partir de **principal** est fonctionnellement équivalente à l’appel le **quitter** (fonction). Prenons l'exemple suivant :  
  
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