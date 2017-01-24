---
title: "__writecr4 | Microsoft Docs"
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
  - "_writecr4"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_writecr4, intrinsèque"
ms.assetid: ab7651d7-b86b-4be7-a0a0-7263099c70fc
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __writecr4
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 écrit la valeur `Data` au registre de CR4.  
  
## Syntaxe  
  
```  
void writecr4(   
   unsigned __int64 Data   
);  
```  
  
#### Paramètres  
 \[in\] `Data`  
 La valeur pour écrire dans CR4 le registre.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__writecr4`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette intrinsèque est uniquement disponible en mode noyau, et la routine est uniquement disponible sous forme intrinsèque.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)