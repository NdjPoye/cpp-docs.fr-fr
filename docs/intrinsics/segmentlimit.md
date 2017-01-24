---
title: "__segmentlimit | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__segmentlimit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__segmentlimit, intrinsèque"
  - "lsl, instruction"
ms.assetid: d0bc3630-90cb-4185-8667-686fd41e23d4
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __segmentlimit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère des instructions d' `lsl` \(limite de segment de charge\).  
  
## Syntaxe  
  
```  
unsigned long __segmentlimit(   
   unsigned long a   
);  
```  
  
#### Paramètres  
 \[in\] `a`  
 une constante qui spécifie le sélecteur de segment.  
  
## Valeur de retour  
 la limite de segment du sélecteur de segment spécifié par `a,`à condition que le sélecteur soit valide et visible au niveau d'autorisation actuel.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__segmentlimit`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Si la limite de segment ne peut pas être récupérée, de échec de cette instruction.  En cas de échec, cette instruction désactive la balise de ZF et la valeur de retour est pas définie.  
  
 Cette routine est uniquement disponible sous forme intrinsèque.  
  
## Exemple  
  
```  
#include <stdio.h>  
  
#ifdef _M_IX86  
typedef unsigned int READETYPE;  
#else  
typedef unsigned __int64 READETYPE;  
#endif  
  
#define EFLAGS_ZF      0x00000040  
#define KGDT_R3_DATA    0x0020  
#define RPL_MASK        0x3  
  
extern "C"  
{  
unsigned long __segmentlimit (unsigned long);  
READETYPE __readeflags();  
}  
  
#pragma intrinsic(__readeflags)  
#pragma intrinsic(__segmentlimit)  
  
int main(void)  
{  
   const unsigned long initsl = 0xbaadbabe;  
   READETYPE eflags = 0;  
   unsigned long sl = initsl;  
  
   printf("Before: segment limit =0x%x eflags =0x%x\n", sl, eflags);  
   sl = __segmentlimit(KGDT_R3_DATA + RPL_MASK);  
  
   eflags = __readeflags();  
  
   printf("After: segment limit =0x%x eflags =0x%x eflags.zf = %s\n", sl, eflags, (eflags & EFLAGS_ZF) ? "set" : "clear");  
  
   // If ZF is set, the call to lsl succeeded; if ZF is clear, the call failed.  
   printf("%s\n", eflags & EFLAGS_ZF ? "Success!": "Fail!");  
  
   // You can verify the value of sl to make sure that the instruction wrote to it  
   printf("sl was %s\n", (sl == initsl) ? "unchanged" : "changed");  
  
   return 0;  
}  
```  
  
  **avant : eflags \=0x0 de la limite \=0xbaadbabe de segment**  
**Après : sur un des segments les eflags \=0x256 de la limite \=0xffffffff eflags.zf \= défini**  
**Succès.  le SL a été modifié**    
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)