---
title: "Lvalues et Rvalues | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "valeurs L"
  - "valeurs R"
ms.assetid: a8843344-cccc-40be-b701-b71f7b5cdcaf
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Lvalues et Rvalues
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chaque expression C\+\+ est une lvalue ou une rvalue.  Une lvalue fait référence à un objet qui persiste au\-delà d'une expression unique.  Vous pouvez considérer une lvalue comme un objet qui porte un nom.  Toutes les variables, y compris les variables non modifiables \(`const`\), sont des lvalues.  Une rvalue est une valeur temporaire qui n'est pas persistante au\-delà de l'expression qui l'utilise.  Pour mieux comprendre la différence entre les Ivalues et les rvalues, observez l'exemple suivant :  
  
```  
// lvalues_and_rvalues1.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main()  
{  
   int x = 3 + 4;  
   cout << x << endl;  
}  
```  
  
 Dans cet exemple, `x` est une lvalue car elle persiste au\-delà de l'expression qui la définit.  L'expression `3 + 4` est une rvalue car elle prend une valeur temporaire qui n'est pas persistante au\-delà de l'expression qui le définit.  
  
 L'exemple suivant illustre plusieurs utilisations correctes et incorrectes des valeurs lvalues et des rvalues :  
  
```  
// lvalues_and_rvalues2.cpp  
int main()  
{  
   int i, j, *p;  
  
   // Correct usage: the variable i is an lvalue.  
   i = 7;  
  
   // Incorrect usage: The left operand must be an lvalue (C2106).  
   7 = i; // C2106  
   j * 4 = 7; // C2106  
  
   // Correct usage: the dereferenced pointer is an lvalue.  
   *p = i;   
  
   const int ci = 7;  
   // Incorrect usage: the variable is a non-modifiable lvalue (C3892).  
   ci = 9; // C3892  
  
   // Correct usage: the conditional operator returns an lvalue.  
   ((i < 3) ? i : j) = 7;  
}  
```  
  
> [!NOTE]
>  Les exemples de cette rubrique illustrent une utilisation correcte et incorrecte lorsque les opérateurs ne sont pas surchargés.  En surchargeant les opérateurs, vous pouvez faire d'une expression telle que `j * 4` une lvalue.  
  
 Les termes *Ivalue* et *rvalue* sont souvent utilisés lorsque vous faites référence à des références d'objets.  Pour plus d'informations sur les références, consultez [Déclarateur de référence Lvalue : &](../cpp/lvalue-reference-declarator-amp.md) et [Déclarateur de référence Rvalue : &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## Voir aussi  
 [Concepts de base](../cpp/basic-concepts-cpp.md)   
 [Déclarateur de référence Lvalue : &](../cpp/lvalue-reference-declarator-amp.md)   
 [Déclarateur de référence Rvalue : &&](../cpp/rvalue-reference-declarator-amp-amp.md)