---
title: "__svm_invlpga | Microsoft Docs"
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
  - "__svm_invlpga"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__svm_invlpga, intrinsèque"
  - "INVLPGA, instruction"
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __svm_invlpga
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Invalide l'entrée de reproduction d'adresses dans la mémoire tampon de échecs côté de l'interprétation par ordinateur.  Les paramètres spécifient l'identificateur d'adresse virtuelle et l'espace d'adressage de la page pour invalider.  
  
## Syntaxe  
  
```  
void __svm_invlpga(  
     void *Va,  
     int ASID);  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|\[in\] `Va`|Adresse virtuelle de la page à invalider.|  
|\[in\] `ASID`|L'identificateur de l'espace d' \(ASID\)adressage de la page à invalider.|  
  
## Notes  
 La fonction d' `__svm_invlpga` équivaut à l'instruction machine d' `INVLPGA` .  cette fonction prend en charge l'interaction du moniteur d'ordinateurs virtuels d'un hôte avec un système d'exploitation invité et ses applications.  Pour plus d'informations, recherchez le document, « le volume manuel 2 du programmeur d'architectures AMD64 : programmation système, » numéro de document 24593, révision 3,11, [AMD corporation](http://go.microsoft.com/fwlink/?LinkId=23746) au site.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__svm_invlpga`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)