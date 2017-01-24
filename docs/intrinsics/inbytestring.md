---
title: "__inbytestring | Microsoft Docs"
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
  - "__inbytestring"
  - "__inbytestring_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rep insb, instruction"
  - "__inbytestring, intrinsèque"
ms.assetid: fe549556-e7a3-4af3-8ebf-8a7dc3cb233b
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __inbytestring
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Lit les données du port spécifié à l'aide de l'instruction d' `rep insb` .  
  
## Syntaxe  
  
```  
void __inbytestring(  
   unsigned short Port,  
   unsigned char* Buffer,  
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
|`__inbytestring`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette routine est uniquement disponible sous forme intrinsèque.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)