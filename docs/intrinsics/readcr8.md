---
title: "__readcr8 | Microsoft Docs"
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
  - "__readcr8"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readcr8, intrinsèque"
ms.assetid: fce16953-87ff-4fbe-8081-7962b97ae46c
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __readcr8
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Lit le registre de CR8 et retourne sa valeur.  
  
## Syntaxe  
  
```  
unsigned __int64 __readcr8(void);  
```  
  
## Valeur de retour  
 la valeur dans le registre de CR8.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__readcr8`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette intrinsèque est uniquement disponible en mode noyau, et la routine est uniquement disponible sous forme intrinsèque.  
  
## TERMINEZ le détail de Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)