---
title: "__stosd | Microsoft Docs"
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
  - "__stosd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "stosd, instruction"
  - "rep stosd, instruction"
  - "__stosd, intrinsèque"
ms.assetid: 03104247-1cea-49f6-b6f8-287917bf5680
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __stosd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère une instruction de chaîne du magasin \(`rep stosd`\).  
  
## Syntaxe  
  
```  
void __stosd(   
   unsigned long* Dest,   
   unsigned long Data,   
   size_t Count   
);  
```  
  
#### Paramètres  
 \[out\] `Dest`  
 la destination de l'opération.  
  
 \[in\] `Data`  
 Données à stocker.  
  
 \[in\] `Count`  
 la longueur du bloc de mots doubles à écrire.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__stosd`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Le résultat est que le mot double `Data` est entré dans un bloc de mots doubles d' `Count` à l'emplacement mémoire désigné par `Dest`.  
  
 Cette routine est uniquement disponible sous forme intrinsèque.  
  
## Exemple  
  
```  
// stosd.c  
// processor: x86, x64  
  
#include <stdio.h>  
#include <memory.h>  
#include <intrin.h>  
  
#pragma intrinsic(__stosd)  
  
int main()  
{  
    unsigned long val = 99999;  
    unsigned long a[10];  
  
    memset(a, 0, sizeof(a));  
    __stosd(a+1, val, 2);  
  
printf_s( "%u %u %u %u",  
              a[0], a[1], a[2], a[3]);   
}  
```  
  
  **0 99999 99999 0**   
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)