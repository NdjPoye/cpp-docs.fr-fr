---
title: "__addfsbyte, __addfsword, __addfsdword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__addfsbyte_cpp"
  - "__addfsdword"
  - "__addfsword_cpp"
  - "__addfsbyte"
  - "__addfsword"
  - "__addfsdword_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__addfsdword, intrinsèque"
  - "__addfsword, intrinsèque"
  - "__addfsbyte, intrinsèque"
ms.assetid: 706c70df-6b52-4401-9268-2977ed8ad715
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# __addfsbyte, __addfsword, __addfsdword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Ajoutez une valeur à un emplacement mémoire spécifié par un offset relatif au début du segment d' `FS` .  
  
## Syntaxe  
  
```  
void __addfsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __addfsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __addfsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
```  
  
#### Paramètres  
 \[in\] `Offset`  
 L'offset du début d' `FS`.  
  
 \[in\] `Data`  
 La valeur à ajouter à l'emplacement mémoire.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__addfsbyte`|x86|  
|`__addfsword`|x86|  
|`__addfsdword`|x86|  
  
## Notes  
 Ces routines sont disponibles uniquement comme intrinsèques.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [\_\_incfsbyte, \_\_incfsword, \_\_incfsdword](../intrinsics/incfsbyte-incfsword-incfsdword.md)   
 [\_\_readfsbyte, \_\_readfsdword, \_\_readfsqword, \_\_readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)   
 [\_\_writefsbyte, \_\_writefsdword, \_\_writefsqword, \_\_writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)