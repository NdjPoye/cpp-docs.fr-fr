---
title: la valeur est False (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: false_cpp
dev_langs: C++
helpviewer_keywords: false keyword [C++]
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 47052993f9bfc003310da8c0ead47f62dddcc298
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="false-c"></a>false (C++)
Le mot clé est une des deux valeurs d’une variable de type [bool](../cpp/bool-cpp.md) ou une expression conditionnelle (une expression conditionnelle est maintenant un **true** expression booléenne). Par exemple, si `i` est une variable de type `bool`, le `i = false;` instruction assigne **false** à `i`.  
  
## <a name="example"></a>Exemple  
  
```  
// bool_false.cpp  
#include <stdio.h>  
  
int main()  
{  
    bool bb = true;  
    printf_s("%d\n", bb);  
    bb = false;  
    printf_s("%d\n", bb);  
}  
```  
  
```Output  
1  
0  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)