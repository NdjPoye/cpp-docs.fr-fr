---
title: "__outbyte | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__outbyte"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "out, instruction"
  - "__outbyte, intrinsèque"
ms.assetid: c4cd1a34-8a02-4e37-993d-3201bc17901a
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __outbyte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère des instructions d' `out` , qui envoie 1 octet spécifié par `Data` le port d'E\/S spécifié par `Port`.  
  
## Syntaxe  
  
```  
void __outbyte(   
   unsigned short Port,   
   unsigned char Data   
);  
```  
  
#### Paramètres  
 \[in\] `Port`  
 Le port pour renvoyer les données à.  
  
 \[in\] `Data`  
 l'octet à envoyer le port spécifié.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__outbyte`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette routine est uniquement disponible sous forme intrinsèque.  
  
## TERMINEZ le détail de Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)