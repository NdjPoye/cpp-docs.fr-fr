---
title: "__vmx_vmclear | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__vmx_vmclear"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VMCLEAR, instruction"
  - "__vmx_vmclear, intrinsèque"
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __vmx_vmclear
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Initialise la structure de contrôle spécifiée d' \(VMCS\)ordinateur virtuel et définit son état de lancement pour `Clear`.  
  
## Syntaxe  
  
```  
unsigned char __vmx_vmclear(  
   unsigned __int64 *VmcsPhysicalAddress  
);  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|\[in\] `VmcsPhysicalAddress`|Un pointeur vers un emplacement mémoire 64 bits qui contient l'adresse physique du VMCS pour désactiver.|  
  
## Valeur de retour  
  
|Valeur|Signification|  
|------------|-------------------|  
|0|l'opération réussie.|  
|1|L'opération a échoué avec l'état étendu disponible dans `VM-instruction error field` du actuel VMCS.|  
|2|L'opération a échoué sans état disponible.|  
  
## Notes  
 une application peut exécuter une opération de VM\-entrer à l'aide de [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) ou de la fonction de [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) .  La fonction de [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) peut être utilisée qu'avec un VMCS dont l'état de lancement est `Clear`, et la fonction de [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) peut être utilisée qu'avec un VMCS dont l'état de lancement est `Launched`.  Par conséquent, utilisez la fonction de [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md) pour définir la condition de lancement d'un VMCS à `Clear`.  Utilisez la fonction de [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) de votre première VM\-entrent l'opération et la fonction de [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) pour suivant VM\-entrent des opérations.  
  
 La fonction d' `__vmx_vmclear` équivaut à l'instruction machine d' `VMCLEAR` .  cette fonction prend en charge l'interaction du moniteur d'ordinateurs virtuels d'un hôte avec un système d'exploitation invité et ses applications.  Pour plus d'informations, recherchez le document, « spécification technique de virtualisation Intel pour l'architecture de IA\-32 Intel, » numéro de document C97063 \-002, [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) au site.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__vmx_vmclear`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md)