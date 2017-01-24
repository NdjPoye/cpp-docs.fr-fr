---
title: "__addgsbyte, __addgsword, __addgsdword, __addgsqword | Microsoft Docs"
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
  - "__addgsdword"
  - "__addgsqword"
  - "__addgsword_cpp"
  - "__addgsword"
  - "__addgsbyte_cpp"
  - "__addgsqword_cpp"
  - "__addgsbyte"
  - "__addgsdword_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__addgsword, intrinsèque"
  - "__addgsqword, intrinsèque"
  - "__addgsdword, intrinsèque"
  - "__addgsbyte, intrinsèque"
ms.assetid: 4fa03e69-d849-49ed-ba37-1d3aa23c2a21
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __addgsbyte, __addgsword, __addgsdword, __addgsqword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Ajoutez une valeur à un emplacement mémoire spécifié par un offset relatif au début du segment d' `GS` .  
  
## Syntaxe  
  
```  
void __addgsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __addgsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __addgsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
void __addgsqword(   
   unsigned long Offset,   
   unsigned __int64 Data   
);  
```  
  
#### Paramètres  
 \[in\] `Offset`  
 L'offset du début d' `GS`.  
  
 \[in\] `Data`  
 La valeur à ajouter à l'emplacement mémoire.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__addgsbyte`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__addgsword`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__addgsdword`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__addgsqword`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
## Notes  
 Ces éléments intrinsèques sont disponibles en mode noyau uniquement, et ces routines sont uniquement disponibles comme intrinsèques.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [\_\_incgsbyte, \_\_incgsword, \_\_incgsdword, \_\_incgsqword](../intrinsics/incgsbyte-incgsword-incgsdword-incgsqword.md)   
 [\_\_readgsbyte, \_\_readgsdword, \_\_readgsqword, \_\_readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)   
 [\_\_writegsbyte, \_\_writegsdword, \_\_writegsqword, \_\_writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)