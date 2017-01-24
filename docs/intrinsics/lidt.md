---
title: "__lidt | Microsoft Docs"
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
  - "__lidt"
  - "__lidt_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LIDT, instruction"
  - "__lidt, intrinsèque"
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __lidt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Charge le marquage des tables de descripteur d'interruption \(IDTR\) à la valeur dans l'emplacement mémoire spécifié.  
  
## Syntaxe  
  
```  
void __lidt(  
     void *Source);  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|\[in\] `Source`|Pointeur vers la valeur à copier à l'IDTR.|  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__lidt`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 La fonction d' `__lidt` équivaut à l'instruction machine d' `LIDT` , et est uniquement disponible en mode noyau.  Pour plus d'informations, recherchez le document, « le manuel du développeur de logiciels d'architecture Intel, le volume 2 : référence de jeu d'instructions, » [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) au site.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_\_sidt](../intrinsics/sidt.md)