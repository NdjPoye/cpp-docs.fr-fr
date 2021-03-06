---
title: la valeur True (C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- true_cpp
dev_langs:
- C++
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44df8d3e9429c272d83025b600fc8d43cc8f8b73
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="true-c"></a>true (C++)
## <a name="syntax"></a>Syntaxe  
  
```  
  
      bool-identifier = true ;  
bool-expression logical-operator true ;  
```  
  
## <a name="remarks"></a>Notes  
 Ce mot clé est une des deux valeurs d’une variable de type [bool](../cpp/bool-cpp.md) ou une expression conditionnelle (une expression conditionnelle est maintenant une véritable expression booléenne). Si `i` est de type `bool`, puis l’instruction `i = true;` assigne **true** à `i`.  
  
## <a name="example"></a>Exemple  
  
```  
// bool_true.cpp  
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