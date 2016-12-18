---
title: "__vmx_vmwrite | Microsoft Docs"
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
  - "__vmx_vmwrite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__vmx_vmwrite intrinsèque"
  - "VMWRITE, instruction"
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmwrite
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Écrit la valeur spécifiée au champ spécifié dans la structure de contrôle actuelle de l'ordinateur \(VMCS\) virtuel.  
  
## Syntaxe  
  
```  
unsigned char __vmx_vmwrite(   
   size_t Field,  
   size_t FieldValue  
);  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|\[in\] `Field`|le champ de VMCS à écrire.|  
|\[in\] `FieldValue`|La valeur à écrire dans le champ de VMCS.|  
  
## Valeur de retour  
 0  
 l'opération réussie.  
  
 1  
 L'opération a échoué avec l'état étendu disponible dans `VM-instruction error field` du actuel VMCS.  
  
 2  
 L'opération a échoué sans état disponible.  
  
## Notes  
 La fonction d' `__vmx_vmwrite` équivaut à l'instruction machine d' `VMWRITE` .  la valeur du paramètre d' `Field` est un index encodé de champ qui est décrit dans la documentation d'Intel.  Pour plus d'informations, recherchez le document, « la spécification technique de virtualisation Intel pour l'architecture de IA\-32 Intel, » le numéro de document C97063 \-002, [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) du site, et font référence ensuite l'annexe C de ce document.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__vmx_vmwrite`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmread](../intrinsics/vmx-vmread.md)