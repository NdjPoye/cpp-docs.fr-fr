---
title: "__readfsbyte, __readfsdword, __readfsqword, __readfsword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readfsword"
  - "__readfsdword"
  - "__readfsbyte"
  - "__readfsqword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readfsword, intrinsèque"
  - "readfsword, intrinsèque"
  - "__readfsdword, intrinsèque"
  - "readfsbyte, intrinsèque"
  - "__readfsbyte, intrinsèque"
  - "readfsdword, intrinsèque"
  - "readfsqword, intrinsèque"
  - "__readfsqword, intrinsèque"
ms.assetid: f6ee7203-4179-402c-a464-0746c84ce6ac
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __readfsbyte, __readfsdword, __readfsqword, __readfsword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Lisez la mémoire d'un emplacement spécifié par un offset relatif au début du segment de FS.  
  
## Syntaxe  
  
```  
unsigned char __readfsbyte(   
   unsigned long Offset   
);  
unsigned short __readfsword(   
   unsigned long Offset   
);  
unsigned long __readfsdword(   
   unsigned long Offset  
);  
unsigned __int64 __readfsqword(   
   unsigned long Offset   
);  
```  
  
#### Paramètres  
 \[in\] `Offset`  
 L'offset du début d' `FS` pour lire.  
  
## Valeur de retour  
 Les contenu en mémoire de l'octet, le mot, le mot double, ou le mot quadruple \(comme indiqué par le nom de la fonction appelée\) à l'emplacement `FS:[``Offset``]`.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__readfsbyte`|x86|  
|`__readfsdword`|x86|  
|`__readfsqword`|x86|  
|`__readfsword`|x86|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Ces routines sont disponibles uniquement comme intrinsèques.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [\_\_writefsbyte, \_\_writefsdword, \_\_writefsqword, \_\_writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)