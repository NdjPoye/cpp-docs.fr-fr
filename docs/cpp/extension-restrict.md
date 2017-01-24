---
title: "__restrict | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__restrict"
  - "__restrict_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__restrict (mot clé) (C++)"
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __restrict
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comme le modificateur **\_\_declspec \([restrict](../cpp/restrict.md)\)**, le mot clé `__restrict` indique qu'un symbole n'a pas d'alias dans la portée actuelle.  Le mot clé `__restrict` diffère du modificateur `__declspec ( restrict )` sur les points suivants :  
  
-   Le mot clé `__restrict` est valide uniquement sur des variables, alors que `__declspec ( restrict )` est valide seulement sur des déclarations et des définitions de fonction.  
  
-   `__restrict` est similaire à `restrict` issu de la norme C99, mais `__restrict` peut être utilisé dans les programmes C et C\+\+.  
  
-   Lorsque `__restrict` est utilisé, le compilateur ne propage pas la propriété anti\-alias d'une variable.  Autrement dit, si vous assignez une variable `__restrict` à une variable non\-`__restrict`, le compilateur permet toujours à la variable non\-\_\_restrict d'avoir un alias.  Cela diffère du comportement du mot clé `restrict` défini dans la norme C99.  
  
 En général, si vous influez sur le comportement d'une fonction entière, il est préférable d'utiliser `__declspec ( restrict )` plutôt que le mot clé.  
  
 Dans Visual Studio 2015 et versions ultérieures, `__restrict` peut être utilisé sur les références C\+\+.  
  
> [!NOTE]
>  Lorsqu'il est utilisé sur une variable qui possède également le mot clé [volatile](../cpp/volatile-cpp.md), `volatile` est prioritaire.  
  
## Exemple  
  
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
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)