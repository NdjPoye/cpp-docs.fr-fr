---
title: "__nop | Microsoft Docs"
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
  - "__nop"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nop, instruction"
  - "__nop, intrinsèque"
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __nop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère le code machine spécifique à la plateforme qui n'effectue aucune opération.  
  
## Syntaxe  
  
```  
void __nop();  
```  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__nop`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## détail de FIN Microsoft  
  
## Notes  
 La fonction d' `__nop` équivaut à l'instruction machine d' `NOP` .  Pour plus d'informations, recherchez le document, « le manuel du développeur de logiciels d'architecture Intel, le volume 2 : référence de jeu d'instructions, » [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) au site.  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_\_noop](../intrinsics/noop.md)