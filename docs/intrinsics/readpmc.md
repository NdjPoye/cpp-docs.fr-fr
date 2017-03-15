---
title: "__readpmc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readpmc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Read Performance Monitoring Counters, instruction"
  - "__readpmc, intrinsèque"
  - "rdpmc, instruction"
ms.assetid: 14ed45a6-28b6-4635-8437-a597c04b43d4
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __readpmc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère des instructions d' `rdpmc` , qui lit le compteur de performance spécifié par `counter`.  
  
## Syntaxe  
  
```  
unsigned __int64 __readpmc(   
   unsigned long counter   
);  
```  
  
#### Paramètres  
 \[in\] `counter`  
 La représentation compteur à lire.  
  
## Valeur de retour  
 la valeur du compteur de performance spécifié.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__readpmc`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette intrinsèque est disponible en mode noyau uniquement, et la routine est uniquement disponible sous forme intrinsèque.  
  
## TERMINEZ le détail de Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)