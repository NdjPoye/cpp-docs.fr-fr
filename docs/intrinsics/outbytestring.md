---
title: "__outbytestring | Microsoft Docs"
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
  - "__outbytestring"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rep outsb, instruction"
  - "__outbytestring, intrinsèque"
  - "outsb, instruction"
ms.assetid: c9150661-9c18-427f-bae8-710bba6ed78c
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __outbytestring
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère des instructions d' `rep outsb` , qui envoie les premiers octets d' `Count` de données pointées par `Buffer` au port spécifié par `Port`.  
  
## Syntaxe  
  
```  
void __outbytestring(   
   unsigned short Port,   
   unsigned char* Buffer,   
   unsigned long Count   
);  
```  
  
#### Paramètres  
 \[in\] `Port`  
 Le port pour renvoyer les données à.  
  
 \[in\] `Buffer`  
 les données à envoyer le port spécifié.  
  
 \[in\] `Count`  
 le nombre d'octets de données à envoyer.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__outbytestring`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette routine est uniquement disponible sous forme intrinsèque.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)