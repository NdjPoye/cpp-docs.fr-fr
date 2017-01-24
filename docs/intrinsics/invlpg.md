---
title: "__invlpg | Microsoft Docs"
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
  - "__invlpg"
  - "__invlpg_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invlpg, instruction"
  - "__invlpg, intrinsèque"
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __invlpg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère des instructions d' `invlpg` x86, qui invalide la mémoire tampon lookaside de \(TLB\) traduction de la page associée à la mémoire désignée par `Address`.  
  
## Syntaxe  
  
```  
void __invlpg(  
   void* Address  
);  
```  
  
#### Paramètres  
 \[in\]    `Address`  
 une adresse 64 bits.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__invlpg`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 `__invlpg` intrinsèque émet une instruction privilégiée et est uniquement disponible en mode noyau avec un niveau de privilège \(COMPLET\) de 0.  
  
 Cette routine est uniquement disponible sous forme intrinsèque.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)