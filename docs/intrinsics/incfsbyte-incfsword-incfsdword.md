---
title: "__incfsbyte, __incfsword, __incfsdword | Microsoft Docs"
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
  - "__incfsword"
  - "__incfsbyte_cpp"
  - "__incfsbyte"
  - "__incfsdword"
  - "__incfsword_cpp"
  - "__incfsdword_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__incfsword, intrinsèque"
  - "__incfsdword, intrinsèque"
  - "__incfsbyte, intrinsèque"
ms.assetid: 820457fb-e35e-42d3-bcb6-725da3281c64
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __incfsbyte, __incfsword, __incfsdword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Ajoutez \-en une à la valeur dans un emplacement mémoire spécifié par un offset relatif au début du segment d' `FS` .  
  
## Syntaxe  
  
```  
void __incfsbyte(   
   unsigned long Offset   
);  
void __incfsword(   
   unsigned long Offset   
);  
void __incfsdword(   
   unsigned long Offset  
);  
```  
  
#### Paramètres  
 \[in\] `Offset`  
 L'offset du début d' `FS`.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__incfsbyte`|x86|  
|`__incfsword`|x86|  
|`__incfsdword`|x86|  
  
## Notes  
 Ces éléments intrinsèques sont uniquement disponibles en mode noyau, et les routines sont uniquement disponibles comme intrinsèques.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [\_\_addfsbyte, \_\_addfsword, \_\_addfsdword](../intrinsics/addfsbyte-addfsword-addfsdword.md)   
 [\_\_readfsbyte, \_\_readfsdword, \_\_readfsqword, \_\_readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)   
 [\_\_writefsbyte, \_\_writefsdword, \_\_writefsqword, \_\_writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)