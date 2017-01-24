---
title: "__stosq | Microsoft Docs"
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
  - "__stosq"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rep stosq, instruction"
  - "stosq, instruction"
  - "__stosq, intrinsèque"
ms.assetid: 3ea28297-4369-4c2d-bf0c-91fa539ce209
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __stosq
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère une instruction de chaîne du magasin \(`rep stosq`\).  
  
## Syntaxe  
  
```  
void __stosb(   
   unsigned __int64* Dest,   
   unsigned __int64 Data,   
   size_t Count   
);  
```  
  
#### Paramètres  
 \[out\] `Dest`  
 la destination de l'opération.  
  
 \[in\] `Data`  
 Données à stocker.  
  
 \[in\] `Count`  
 la longueur du bloc de mots quadruples à écrire.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__stosq`|AMD64|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Le résultat est que le mot quadruple `Data` est entré dans un bloc de mots quadruples d' `Count` dans la chaîne d' `Dest` .  
  
 Cette routine est uniquement disponible sous forme intrinsèque.  
  
## Exemple  
  
```  
// stosq.c  
// processor: x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__stosq)  
  
int main()  
{  
   unsigned __int64 val = 0xFFFFFFFFFFFFI64;  
   unsigned __int64 a[10];  
   memset(a, 0, sizeof(a));  
   __stosq(a+1, val, 2);  
   printf("%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);   
}  
```  
  
## Sortie  
  
```  
0 ffffffffffff ffffffffffff 0  
```  
  
### détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)