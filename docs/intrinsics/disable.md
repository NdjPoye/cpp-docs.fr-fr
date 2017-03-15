---
title: "_disable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_disable_cpp"
  - "_disable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_disable intrinsic"
  - "disable intrinsic"
  - "rsm instruction"
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _disable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Désactive les interruptions.  
  
## Syntaxe  
  
```  
void _disable(void);  
```  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_disable`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 `_disable` fait en sorte que le processeur efface l'indicateur d'interruption.  Sur les systèmes x86, cette fonction génère l'instruction d'effacement de l'indicateur d'interruption \(`cli`\).  
  
 Cette fonction est disponible uniquement en mode noyau.  Si vous l'utilisez en mode utilisateur, une exception Instruction privilégiée est levée au moment de l'exécution.  
  
 Sur les plateformes ARM, cette routine est disponible uniquement en tant qu'intrinsèque.  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)