---
title: "__indwordstring | Microsoft Docs"
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
  - "__indwordstring"
  - "__indwordstring_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__indwordstring, intrinsèque"
  - "rep insd, instruction"
ms.assetid: 96a1cf33-f691-4916-99e4-fa849b61e3a9
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __indwordstring
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Lit les données du port spécifié à l'aide de l'instruction d' `rep insd` .  
  
## Syntaxe  
  
```  
void __indwordstring(  
   unsigned short Port,  
   unsigned long* Buffer,  
   unsigned long Count  
);  
```  
  
#### Paramètres  
 \[in\] `Port`  
 Le port à lire.  
  
 \[out\] `Buffer`  
 la lecture de données du port est écrite ici.  
  
 \[in\] `Count`  
 Le nombre d'octets de données à lire.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__indwordstring`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette routine est uniquement disponible sous forme intrinsèque.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)