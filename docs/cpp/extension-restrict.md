---
title: __restrict | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __restrict_cpp
dev_langs:
- C++
helpviewer_keywords:
- __restrict keyword [C++]
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d96abd70990f1c01229004e9be000ec4e35a8595
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="restrict"></a>__restrict
Comme le **__declspec ( [restreindre](../cpp/restrict.md) )** modificateur, le `__restrict` mot clé indique qu’un symbole n’est pas un alias dans la portée actuelle. Le mot clé `__restrict` diffère du modificateur `__declspec ( restrict )` sur les points suivants :  
  
-   Le mot clé `__restrict` est valide uniquement sur des variables, alors que `__declspec ( restrict )` est valide seulement sur des déclarations et des définitions de fonction.  
  
-   `__restrict` est similaire à `restrict` issu de la norme C99, mais `__restrict` peut être utilisé dans les programmes C et C++.  
  
-   Lorsque `__restrict` est utilisé, le compilateur ne propage pas la propriété anti-alias d'une variable. Autrement dit, si vous assignez une variable `__restrict` à une variable non-`__restrict`, le compilateur permet toujours à la variable non-__restrict d'avoir un alias. Cela diffère du comportement du mot clé `restrict` défini dans la norme C99.  
  
 En général, si vous influez sur le comportement d'une fonction entière, il est préférable d'utiliser `__declspec ( restrict )` plutôt que le mot clé.  
  
 Dans Visual Studio 2015 et versions ultérieures, `__restrict` peut être utilisé sur les références C++.  
  
> [!NOTE]
>  Lorsqu’il est utilisé sur une variable qui a également la [volatile](../cpp/volatile-cpp.md) (mot clé), `volatile` est prioritaire.  
  
## <a name="example"></a>Exemple  
  
```  
// __restrict_keyword.c  
// compile with: /LD  
// In the following function, declare a and b as disjoint arrays  
// but do not have same assurance for c and d.  
void sum2(int n, int * __restrict a, int * __restrict b,   
          int * c, int * d) {  
   int i;  
   for (i = 0; i < n; i++) {  
      a[i] = b[i] + c[i];  
      c[i] = b[i] + d[i];  
    }  
}  
  
// By marking union members as __restrict, tell compiler that  
// only z.x or z.y will be accessed in any given scope.  
union z {  
   int * __restrict x;  
   double * __restrict y;  
};  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)