---
title: "__halt | Microsoft Docs"
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
  - "__halt"
  - "__halt_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__halt, intrinsèque"
  - "HLT, instruction"
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __halt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Interrompt le processeur jusqu'à ce qu'une interruption active, une interruption non \(NMI\) masquable, ou une remise se produise.  
  
## Syntaxe  
  
```  
void __halt( void );  
```  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__halt`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 La fonction d' `__halt` équivaut à l'instruction machine d' `HLT` , et est uniquement disponible en mode noyau.  Pour plus d'informations, recherchez le document, « le manuel du développeur de logiciels d'architecture Intel, le volume 2 : référence de jeu d'instructions, » [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) au site.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)