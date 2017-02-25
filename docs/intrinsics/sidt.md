---
title: "__sidt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__sidt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sidt, instruction"
  - "__sidt, intrinsèque"
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __sidt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Stocke la valeur du registre de tableau de descripteur d'interruption \(IDTR\) dans l'emplacement mémoire spécifié.  
  
## Syntaxe  
  
```  
void __sidt(  
     void *Destination);  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|\[in\] `Destination`|Un pointeur vers l'emplacement mémoire où l'IDTR est enregistré.|  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__sidt`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 La fonction d' `__sidt` équivaut à l'instruction machine d' `SIDT` .  Pour plus d'informations, recherchez le document, « le manuel du développeur de logiciels d'architecture Intel, le volume 2 : référence de jeu d'instructions, » [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) au site.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_\_lidt](../intrinsics/lidt.md)