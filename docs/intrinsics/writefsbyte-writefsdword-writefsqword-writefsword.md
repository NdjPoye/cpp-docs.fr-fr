---
title: "__writefsbyte, __writefsdword, __writefsqword, __writefsword | Microsoft Docs"
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
  - "__writefsword"
  - "__writefsbyte"
  - "__writefsqword"
  - "__writefsdword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "writefsbyte, intrinsèque"
  - "__writefsword, intrinsèque"
  - "writefsqword, intrinsèque"
  - "writefsdword, intrinsèque"
  - "__writefsdword, intrinsèque"
  - "__writefsqword, intrinsèque"
  - "__writefsbyte, intrinsèque"
  - "writefsword, intrinsèque"
ms.assetid: 23ac6e8e-bc91-4e90-a4c6-da02993637ad
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __writefsbyte, __writefsdword, __writefsqword, __writefsword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Entrez la mémoire à un emplacement spécifié par un offset relatif au début du segment de FS.  
  
## Syntaxe  
  
```  
void __writefsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __writefsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __writefsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
void __writefsqword(   
   unsigned long Offset,   
   unsigned __int64 Data   
);  
```  
  
#### Paramètres  
 \[in\] `Offset`  
 L'offset du début du FS à écrire la valeur.  
  
 \[in\] `Data`  
 Valeur à écrire.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__writefsbyte`|x86|  
|`__writefsword`|x86|  
|`__writefsdword`|x86|  
|`__writefsqword`|x86|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Ces routines sont disponibles uniquement comme intrinsèques.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [\_\_readfsbyte, \_\_readfsdword, \_\_readfsqword, \_\_readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)