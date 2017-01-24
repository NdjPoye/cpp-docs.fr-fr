---
title: "__vmx_vmptrst | Microsoft Docs"
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
  - "__vmx_vmptrst"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__vmx_vmptrst intrinsèque"
  - "VMPTRST, instruction"
ms.assetid: 8dc66e47-03a0-41b0-8e25-c1485f42817a
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmptrst
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Stocke le pointeur à la structure de contrôle actuelle d'ordinateur \(VMCS\) virtuel à l'adresse spécifiée.  
  
## Syntaxe  
  
```  
void __vmx_vmptrst(   
   unsigned __int64 *VmcsPhysicalAddress   
);  
```  
  
#### Paramètres  
 \[in\]  \*`VmcsPhysicalAddress`  
 L'adresse où le pointeur du actuel VMCS est enregistré.  
  
## Notes  
 le pointeur de VMCS est une adresse physique 64 bits.  
  
 La fonction d' `__vmx_vmptrst` équivaut à l'instruction machine d' `VMPTRST` .  cette fonction prend en charge l'interaction du moniteur d'ordinateurs virtuels d'un hôte avec un système d'exploitation invité et ses applications.  Pour plus d'informations, recherchez le document, « spécification technique de virtualisation Intel pour l'architecture de IA\-32 Intel, » numéro de document C97063 \-002, [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) au site.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__vmx_vmptrst`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmptrld](../intrinsics/vmx-vmptrld.md)