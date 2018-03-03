---
title: Compilateur avertissement (niveau 2) C4146 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4146
dev_langs:
- C++
helpviewer_keywords:
- C4146
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d7a9a67beb4dc122c25318c1796e22a4c35dbe38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4146"></a>Compilateur avertissement (niveau 2) C4146
opérateur moins unaire appliqué à un type non signé, le résultat sera non signé  
  
 Types non signés peuvent contenir des valeurs de négatif uniquement, donc unaire (négation) n’est pas généralement pertinent quand il est appliqué à un type non signé. L’opérande et le résultat ne sont pas négatifs.  
  
 En pratique, cela se produit lorsque le programmeur tente d’exprimer la valeur entière minimale, qui est -2147483648. Cette valeur ne peut pas être écrite comme -2147483648 car l’expression est traitée en deux étapes :  
  
1.  Le nombre 2147483648 est évalué. Comme il est supérieur à la valeur entière maximale 2147483647, le type de 2147483648 n’est pas [int](../../c-language/integer-types.md), mais `unsigned int`.  
  
2.  Moins unaire est appliqué à la valeur, avec un résultat non signé, ce qui se trouve être 2147483648.  
  
 Le type non signé du résultat peut provoquer un comportement inattendu. Si le résultat est utilisé dans une comparaison, une comparaison non signée peut être utilisée, par exemple, lorsque l’autre opérande est un `int`. Cela explique pourquoi l’exemple de programme ci-dessous imprime qu’une ligne.  
  
 La deuxième ligne attendue, `1 is greater than the most negative int`, n’est pas imprimé car `((unsigned int)1) > 2147483648` a la valeur false.  
  
 Vous pouvez éviter C4146 en utilisant INT_MIN défini dans limits.h, qui a le type **type signed int**.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C4146 :  
  
```  
// C4146.cpp  
// compile with: /W2  
#include <stdio.h>  
  
void check(int i)   
{  
    if (i > -2147483648)   // C4146  
        printf_s("%d is greater than the most negative int\n", i);  
}  
  
int main()   
{  
    check(-100);  
    check(1);  
}  
```