---
title: "__vmx_on | Microsoft Docs"
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
  - "__vmx_on"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VMXON, instruction"
  - "__vmx_on, intrinsèque"
ms.assetid: 16804991-6a75-4adf-8ec2-bc95acfa4801
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_on
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 active l'opération d'extensions d'ordinateur virtuel \(VMX\) dans le processeur.  
  
## Syntaxe  
  
```  
unsigned char __vmx_on(  
   unsigned __int64 *VmsSupportPhysicalAddress  
);  
```  
  
#### Paramètres  
 \[in\] `VmsSupportPhysicalAddress`  
 Un pointeur vers une adresse physique 64 bits qui pointe vers une structure de contrôle d'ordinateur \(VMCS\) virtuel.  
  
## Valeur de retour  
  
|Valeur|Signification|  
|------------|-------------------|  
|0|l'opération réussie.|  
|1|L'opération a échoué avec l'état étendu disponible dans `VM-instruction error field` du actuel VMCS.|  
|2|L'opération a échoué sans état disponible.|  
  
## Notes  
 la fonction d' `__vmx_on` correspond à l'instruction machine d' `VMXON` .  cette fonction prend en charge l'interaction du moniteur d'ordinateurs virtuels d'un hôte avec un système d'exploitation invité et ses applications.  Pour plus d'informations, recherchez le document, « spécification technique de virtualisation Intel pour l'architecture de IA\-32 Intel, » numéro de document C97063 \-002, [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) au site.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__vmx_on`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)