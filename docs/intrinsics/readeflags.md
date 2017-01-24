---
title: "__readeflags | Microsoft Docs"
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
  - "__readeflags"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readeflags, intrinsèque"
ms.assetid: f9d2f4d8-c428-491f-b8de-04d0566b2b6b
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __readeflags
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lit le registre d'état et de contrôle du programme \(EFLAGS\).  
  
## Syntaxe  
  
```  
unsigned     int __readeflags(void);  
unsigned __int64 __readeflags(void);  
```  
  
## Valeur de retour  
 la valeur du registre d'EFLAGS.  La valeur de retour est une longueur minimum de 32 bits sur une plateforme 32 bits et 64 bits de temps sur une plateforme 64 bits.  
  
## Notes  
 Ces routines sont disponibles uniquement comme intrinsèques.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__readeflags`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_\_writeeflags](../intrinsics/writeeflags.md)