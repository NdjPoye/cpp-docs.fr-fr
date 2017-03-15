---
title: "Cibles dans des blocs de description multiples | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "blocs, (multiples) description"
  - "blocs de description"
  - "blocs de description multiples"
ms.assetid: 8618dcd9-c11d-4562-91a7-0c904ed438a8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Cibles dans des blocs de description multiples
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour mettre à jour une cible dans plusieurs blocs de description à l'aide de commandes différentes, spécifiez deux signes deux\-points consécutifs \(::\) entre les cibles et les dépendants.  
  
```  
target.lib :: one.asm two.asm three.asm  
    ml one.asm two.asm three.asm  
    lib target one.obj two.obj three.obj  
target.lib :: four.c five.c  
    cl /c four.c five.c  
    lib target four.obj five.obj  
```  
  
## Voir aussi  
 [Cibles](../build/targets.md)