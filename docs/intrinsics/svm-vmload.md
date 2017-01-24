---
title: "__svm_vmload | Microsoft Docs"
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
  - "__svm_vmload"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__svm_vmload, intrinsèque"
  - "VMLOAD, instruction"
ms.assetid: b46a5592-db76-4ffc-8694-2f3494e28bed
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __svm_vmload
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 charge un sous\-ensemble d'état du processeur du bloc de contrôle spécifié d'ordinateur virtuel \(VMCB\).  
  
## Syntaxe  
  
```  
void __svm_vmload(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|\[in\] `VmcbPhysicalAddress`|l'adresse physique du VMCB.|  
  
## Notes  
 La fonction d' `__svm_vmload` équivaut à l'instruction machine d' `VMLOAD` .  cette fonction prend en charge l'interaction du moniteur d'ordinateurs virtuels d'un hôte avec un système d'exploitation invité et ses applications.  Pour plus d'informations, recherchez le document, « le volume manuel 2 du programmeur d'architectures AMD64 : programmation système, » numéro de document 24593, révision 3,11, [AMD corporation](http://go.microsoft.com/fwlink/?LinkId=23746) au site.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__svm_vmload`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## TERMINEZ le détail de Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_vmrun](../intrinsics/svm-vmrun.md)   
 [\_\_svm\_vmsave](../intrinsics/svm-vmsave.md)