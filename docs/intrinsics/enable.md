---
title: "_enable | Microsoft Docs"
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
  - "_enable"
  - "_enable_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_enable intrinsic"
  - "enable intrinsic"
  - "ssm instruction"
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _enable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Active les interruptions.  
  
## Syntaxe  
  
```  
void _enable(void);  
```  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_enable`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 `_enable` fait en sorte que le processeur définisse l'indicateur d'interruption.  Sur les systèmes x86, cette fonction génère l'instruction de définition de l'indicateur d'interruption \(`sti`\).  
  
 Cette fonction est disponible uniquement en mode noyau.  Si vous l'utilisez en mode utilisateur, une exception Instruction privilégiée est levée.  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)