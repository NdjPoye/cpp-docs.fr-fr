---
title: "__svm_vmrun | Microsoft Docs"
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
  - "__svm_vmrun"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__svm_vmrun, intrinsèque"
  - "VMRUN, instruction"
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __svm_vmrun
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Commence l'exécution de code d'appelée à l'ordinateur virtuel qui correspond au bloc de contrôle spécifié d'ordinateur \(VMCB\) virtuel.  
  
## Syntaxe  
  
```  
void __svm_vmrun(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|\[in\] `VmcbPhysicalAddress`|l'adresse physique du VMCB.|  
  
## Notes  
 La fonction d' `__svm_vmrun` utilise un minimum d'informations dans le VMCB pour démarrer l'exécution du code d'appelée à l'ordinateur virtuel.  Utilisez la fonction de [\_\_svm\_vmsave](../intrinsics/svm-vmsave.md) ou de [\_\_svm\_vmload](../intrinsics/svm-vmload.md) si vous avez besoin de davantage d'informations pour gérer une interruption complexe ou pour le basculer vers un autre invité.  
  
 La fonction d' `__svm_vmrun` équivaut à l'instruction machine d' `VMRUN` .  cette fonction prend en charge l'interaction du moniteur d'ordinateurs virtuels d'un hôte avec un système d'exploitation invité et ses applications.  Pour plus d'informations, recherchez le document, « le volume manuel 2 du programmeur d'architectures AMD64 : Programmation système, » numéro de document 24593, révision 3,11 ou version ultérieure, [AMD corporation](http://go.microsoft.com/fwlink/?LinkId=23746) au site.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__svm_vmrun`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_vmsave](../intrinsics/svm-vmsave.md)   
 [\_\_svm\_vmload](../intrinsics/svm-vmload.md)