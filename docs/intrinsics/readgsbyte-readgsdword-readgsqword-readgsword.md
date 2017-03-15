---
title: "__readgsbyte, __readgsdword, __readgsqword, __readgsword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readgsbyte"
  - "__readgsdword"
  - "__readgsqword"
  - "__readgsword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readgsword, intrinsèque"
  - "__readgsdword, intrinsèque"
  - "__readgsqword, intrinsèque"
  - "__readgsbyte, intrinsèque"
ms.assetid: f822632d-854c-4558-a71b-cdfc3eea2236
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# __readgsbyte, __readgsdword, __readgsqword, __readgsword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Lisez la mémoire d'un emplacement spécifié par un offset relatif au début du segment de GS.  
  
## Syntaxe  
  
```  
unsigned char __readgsbyte(   
   unsigned long Offset   
);  
unsigned short __readgsword(   
   unsigned long Offset   
);  
unsigned long __readgsdword(   
   unsigned long Offset  
);  
unsigned __int64 __readgsqword(   
   unsigned long Offset   
);  
```  
  
#### Paramètres  
 \[in\] `Offset`  
 L'offset du début d' `GS` pour lire.  
  
## Valeur de retour  
 Les contenu en mémoire de l'octet, le mot, du double mot, ou le mot quadruple \(comme indiqué par le nom de la fonction appelée\) à l'emplacement `GS:[``Offset``]`.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__readgsbyte`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__readgsdword`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__readgsqword`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__readgsword`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Ces éléments intrinsèques sont uniquement disponibles en mode noyau, et les routines sont uniquement disponibles comme intrinsèques.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [\_\_writegsbyte, \_\_writegsdword, \_\_writegsqword, \_\_writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)