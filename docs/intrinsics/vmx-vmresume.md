---
title: "__vmx_vmresume | Microsoft Docs"
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
  - "__vmx_vmresume"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__vmx_vmresume intrinsèque"
  - "VMRESUME, instruction"
ms.assetid: 233fe1b6-c727-493a-a484-1b2363732281
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmresume
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Reprend l’opération non racine VMX à l’aide de la structure de contrôle de machine virtuelle actuelle \(VMCS, Virtual Machine Control Structure\).  
  
## Syntaxe  
  
```  
unsigned char __vmx_vmresume(  
   void);  
```  
  
## Valeur de retour  
  
|Valeur|Signification|  
|------------|-------------------|  
|0|L’opération a réussi.|  
|1|L’opération a échoué avec l’état étendu disponible dans le `VM-instruction error field` de la VMCS actuelle.|  
|2|L’opération a échoué sans état disponible.|  
  
## Notes  
 Une application peut effectuer une opération VM\-enter à l’aide de la fonction [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) ou `__vmx_vmresume`. La fonction `__vmx_vmlaunch` peut être utilisée seulement avec une VMCS dont l’état de lancement est `Clear`, et la fonction `__vmx_vmresume` peut être utilisée seulement avec une VMCS dont l’état de lancement est `Launched`. Par conséquent, utilisez la fonction [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md) pour définir l’état de lancement d’une VMCS sur `Clear`, puis utilisez la fonction `__vmx_vmlaunch` pour votre première opération VM\-enter et la fonction `__vmx_vmresume` pour les opérations VM\-enter ultérieures.  
  
 La fonction `__vmx_vmresume` est équivalente à l’instruction machine `VMRESUME`. Cette fonction prend en charge l’interaction du moniteur de machines virtuelles d’un hôte avec un système d’exploitation invité et ses applications. Pour plus d’informations, recherchez le document PDF « Intel Virtualization Technical Specification for the IA\-32 Intel Architecture », dont le numéro de document est C97063\-002, sur le site d’[Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127).  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__vmx_vmresume`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d’en\-tête** \<intrin.h\>  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md)