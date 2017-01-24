---
title: "__vmx_vmlaunch | Microsoft Docs"
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
  - "__vmx_vmlaunch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VMLAUNCH, instruction"
  - "__vmx_vmlaunch, intrinsèque"
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmlaunch
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Place l'application appelante dans VMX l'état de l'opération de non\-racine \(l'ordinateur virtuel entrée\) à l'aide de la structure de contrôle actuelle de l'ordinateur \(VMCS\) virtuel.  
  
## Syntaxe  
  
```  
unsigned char __vmx_vmlaunch(  
   void);  
```  
  
## Valeur de retour  
  
|Valeur|Signification|  
|------------|-------------------|  
|0|l'opération réussie.|  
|1|L'opération a échoué avec l'état étendu disponible dans `VM-instruction error field` du actuel VMCS.|  
|2|L'opération a échoué sans état disponible.|  
  
## Notes  
 une application peut exécuter une opération de VM\-entrer à l'aide de [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) ou de la fonction de [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) .  La fonction de [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) peut être utilisée qu'avec un VMCS dont l'état de lancement est `Clear`, et la fonction de [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) peut être utilisée qu'avec un VMCS dont l'état de lancement est `Launched`.  Par conséquent, utilisez la fonction de [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md) pour définir la condition de lancement d'un VMCS à `Clear`, puis utilisez la fonction de [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) de votre première VM\-entrent l'opération et la fonction de [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) pour suivant VM\-entrent des opérations.  
  
 La fonction d' `__vmx_vmlaunch` équivaut à l'instruction machine d' `VMLAUNCH` .  cette fonction prend en charge l'interaction du moniteur d'ordinateurs virtuels d'un hôte avec un système d'exploitation invité et ses applications.  Pour plus d'informations, recherchez le document, « spécification technique de virtualisation Intel pour l'architecture de IA\-32 Intel, » numéro de document C97063 \-002, [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) au site.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__vmx_vmlaunch`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md)   
 [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md)