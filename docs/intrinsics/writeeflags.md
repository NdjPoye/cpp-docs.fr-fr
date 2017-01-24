---
title: "__writeeflags | Microsoft Docs"
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
  - "__writeeflags"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__writeeflags, intrinsèques"
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __writeeflags
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Écrit la valeur spécifiée dans le registre d'état et de contrôle du programme \(EFLAGS\).  
  
## Syntaxe  
  
```  
void __writeeflags(unsigned Value);  
void __writeeflags(unsigned __int64 Value);  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|\[in\] `Value`|La valeur à écrire dans le registre d'EFLAGS.  Le paramètre d' `Value` est 32 bits longue pour une plateforme 32 bits et 64 bits longue pour une plateforme 64 bits.|  
  
## Notes  
 Ces routines sont disponibles uniquement comme intrinsèques.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__writeeflags`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_\_readeflags](../intrinsics/readeflags.md)