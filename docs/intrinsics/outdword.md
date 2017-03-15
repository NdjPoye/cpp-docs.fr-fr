---
title: "__outdword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__outdword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "out, instruction"
  - "outdword, instruction"
  - "__outdword, intrinsèque"
ms.assetid: ed1e4994-a84b-4759-8bf9-cd48fb073f4d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __outdword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère des instructions d' `out` d'envoyer un mot double `Data` le port `Port`.  
  
## Syntaxe  
  
```  
void __outdword(   
   unsigned short Port,   
   unsigned long Data   
);  
```  
  
#### Paramètres  
 \[in\] `Port`  
 Le port pour renvoyer les données à.  
  
 \[in\] `Data`  
 le mot double à envoyer.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__outdword`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette routine est uniquement disponible sous forme intrinsèque.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)