---
title: __int8, __int16, __int32, __int64 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __int8_cpp
- __int16_cpp
- __int32_cpp
- __int64_cpp
dev_langs:
- C++
helpviewer_keywords:
- __int16 keyword [C++]
- integer data type [C++], integer types in C++
- __int32 keyword [C++]
- integer types [C++]
- __int8 keyword [C++]
- __int64 keyword [C++]
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 957e2483d61855c442780440ccf87441f00cb1c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="int8-int16-int32-int64"></a>__int8, __int16, __int32, __int64
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 Prise en charge des fonctionnalités Microsoft C/C++ pour les types d’entiers dimensionnés. Vous pouvez déclarer des 8, 16, 32 ou variables de type entier de 64 bits à l’aide de la **__int**  *n*  spécificateur, de type où  *n*  est 8, 16, 32 ou 64.  
  
 L'exemple suivant déclare une variable pour chacun de ces types d'entiers dimensionnés :  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 Les types `__int8`, `__int16` et `__int32` sont des synonymes des types ANSI de la même taille, et permettent d'écrire du code portable qui se comporte de façon identique sur plusieurs plateformes. Le `__int8` type de données est synonyme du type `char`, `__int16` est synonyme du type **court**, et `__int32` est synonyme du type `int`. Le `__int64` type est synonyme du type `long long`.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre qu’une __int*xx* paramètre sera promu à `int`:  
  
```  
// sized_int_types.cpp  
  
#include <stdio.h>  
  
void func(int i) {  
    printf_s("%s\n", __FUNCTION__);  
}  
  
int main()  
{  
    __int8 i8 = 100;  
    func(i8);   // no void func(__int8 i8) function  
                // __int8 will be promoted to int  
}  
```  
  
```Output  
func  
```  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)   
 [Types fondamentaux](../cpp/fundamental-types-cpp.md)   
 [Plages de types de données](../cpp/data-type-ranges.md)