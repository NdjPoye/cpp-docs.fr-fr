---
title: "Utilisation d&#39;op&#233;rateurs dans les blocs __asm | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm (mot clé) (C++), opérateurs"
  - "crochets [ ]"
  - "crochets [ ], __asm (blocs)"
  - "opérateurs (C++), utiliser dans les blocs in __asm"
  - "crochets [ ]"
  - "crochets [ ], __asm (blocs)"
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Utilisation d&#39;op&#233;rateurs dans les blocs __asm
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Un bloc `__asm` ne peut pas utiliser d'opérateurs C ou C\+\+ spécifiques, tels que l'opérateur **\<\<**.  Toutefois, les opérateurs partagés par C et MASM, notamment l'opérateur \*, sont interprétés comme opérateurs de langage assembleur.  Par exemple, en dehors d'un bloc `__asm`, les crochets \(**\[ \]**\) sont interprétés comme indices de tableau englobants, que C ajuste automatiquement à la taille d'un élément du tableau.  Au sein d'un bloc `__asm`, ils s'affichent en tant qu'opérateur index MASM, qui produit un offset d'octet non mis à l'échelle à partir d'un objet de données ou d'une étiquette \(pas uniquement d'un tableau\).  Le code suivant illustre l'utilisation la différence :  
  
```  
int array[10];  
  
__asm mov array[6], bx ;  Store BX at array+6 (not scaled)  
  
array[6] = 0;         /* Store 0 at array+24 (scaled) */  
```  
  
 La première référence à `array` n'est pas mise à l'échelle, la seconde oui.  Notez que vous pouvez utiliser l'opérateur **TYPE** pour effectuer une mise à l'échelle basée sur une constante.  Par exemple, les instructions suivantes sont équivalentes :  
  
```  
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24  
  
array[6] = 0;                   /* Store 0 at array + 24 */  
```  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Utilisation de C ou C\+\+ dans les blocs \_\_asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)