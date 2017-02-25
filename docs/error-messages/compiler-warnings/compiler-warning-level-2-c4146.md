---
title: "Avertissement du compilateur (niveau 2) C4146 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4146"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4146"
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Avertissement du compilateur (niveau 2) C4146
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

opérateur moins unaire appliqué à un type non signé, le résultat sera non signé  
  
 Les types non signés ne peuvent contenir que des valeurs positives ou nulles, donc le moins unaire \(opposé\) n'a d'habitude aucune signification s'il s'applique à un type non signé.  L'opérande et le résultat sont tous deux positifs ou nuls.  
  
 En pratique, cela se produit lorsque le programmeur tente d'exprimer la valeur entière minimale, qui correspond à \-2147483648.  Cette valeur ne peut pas être écrite sous la forme \-2147483648 car l'expression est traitée en deux étapes :  
  
1.  Le nombre 2147483648 est évalué.  Comme il est supérieur à la valeur entière maximale 2147483647, le type de 2147483648 n'est pas [int](../../c-language/integer-types.md), mais `unsigned int`.  
  
2.  Le moins unaire est appliqué à la valeur, avec un résultat non signé, qui se trouve être 2147483648.  
  
 Le type non signé du résultat peut générer un comportement inattendu.  Si le résultat est utilisé dans une comparaison, c'est peut\-être une comparaison non signée qui sera effectuée, alors que l'autre opérande est un `int`.  Ceci explique pourquoi le programme ci\-dessous n'imprime qu'une ligne.  
  
 La deuxième ligne attendue, `1 is greater than the most negative int`, n'est pas imprimée parce que l'expression `((unsigned int)1) > 2147483648`  est false.  
  
 Vous pouvez éviter C4146 en utilisant INT\_MIN défini dans limits.h, qui a le type **signed int**.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4146 :  
  
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