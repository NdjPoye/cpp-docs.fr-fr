---
title: "__vmx_vmptrld | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__vmx_vmptrld"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__vmx_vmptrld, intrinsèque"
  - "VMPTRLD, instruction"
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __vmx_vmptrld
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 charge le pointeur à la structure de contrôle actuelle d'ordinateur virtuel \(VMCS\) de l'adresse spécifiée.  
  
## Syntaxe  
  
```  
int __vmx_vmptrld(   
   unsigned __int64 *VmcsPhysicalAddress   
);  
```  
  
#### Paramètres  
 \[in\]  \*`VmcsPhysicalAddress`  
 l'adresse où le pointeur de VMCS est enregistré.  
  
## Valeur de retour  
 0  
 l'opération réussie.  
  
 1  
 L'opération a échoué avec l'état étendu disponible dans `VM-instruction error field` du actuel VMCS.  
  
 2  
 L'opération a échoué sans état disponible.  
  
## Notes  
 le pointeur de VMCS est une adresse physique 64 bits.  
  
 La fonction d' `__vmx_vmptrld` équivaut à l'instruction machine d' `VMPTRLD` .  cette fonction prend en charge l'interaction du moniteur d'ordinateurs virtuels d'un hôte avec un système d'exploitation invité et ses applications.  Pour plus d'informations, recherchez le document, « spécification technique de virtualisation Intel pour l'architecture de IA\-32 Intel, » numéro de document C97063 \-002, [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) au site.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__vmx_vmptrld`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmptrst](../intrinsics/vmx-vmptrst.md)