---
title: "__vmx_vmread | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__vmx_vmread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VMREAD, instruction"
  - "__vmx_vmread, intrinsèque"
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __vmx_vmread
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Lit un champ spécifié de la structure de contrôle actuelle d'ordinateur \(VMCS\) virtuel et le place à l'emplacement spécifié.  
  
## Syntaxe  
  
```  
unsigned char __vmx_vmread(  
   size_t Field,  
   size_t *FieldValue  
);  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|\[in\] `Field`|Le champ de VMCS à lire.|  
|\[in\] `FieldValue`|Pointeur vers l'emplacement pour stocker la valeur lue dans le champ de VMCS spécifié par le paramètre d' `Field` .|  
  
## Valeur de retour  
  
|Valeur|Signification|  
|------------|-------------------|  
|0|l'opération réussie.|  
|1|L'opération a échoué avec l'état étendu disponible dans `VM-instruction error field` du actuel VMCS.|  
|2|L'opération a échoué sans état disponible.|  
  
## Notes  
 La fonction d' `__vmx_vmread` équivaut à l'instruction machine d' `VMREAD` .  la valeur du paramètre d' `Field` est un index encodé de champ qui est décrit dans la documentation d'Intel.  Pour plus d'informations, recherchez le document, « spécification technique de virtualisation Intel pour l'architecture de IA\-32 Intel, » le numéro de document C97063 \-002, [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) au site, consultent l'annexe C de ce document.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__vmx_vmread`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmwrite](../intrinsics/vmx-vmwrite.md)