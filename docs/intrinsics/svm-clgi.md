---
title: "__svm_clgi | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_clgi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLGI, instruction"
  - "__svm_clgi, intrinsèque"
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __svm_clgi
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 désactive la balise d'interruption globale.  
  
## Syntaxe  
  
```  
void __svm_clgi( void );  
```  
  
## Notes  
 La fonction d' `__svm_clgi` équivaut à l'instruction machine d' `CLGI` .  La balise d'interruption globale détermine si le processeur ignore, remet à plus tard, ou gère les interruptions en raison de les événements tels qu'une terminaison d'E\/S, une alerte de la température matériel, ou une exception de débogage.  
  
 cette fonction prend en charge l'interaction du moniteur d'ordinateurs virtuels d'un hôte avec un système d'exploitation invité et ses applications.  Pour plus d'informations, recherchez le document, « le volume manuel 2 du programmeur d'architectures AMD64 : programmation système, » numéro de document 24593, révision 3,11, [AMD corporation](http://go.microsoft.com/fwlink/?LinkId=23746) au site.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__svm_clgi`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_stgi](../intrinsics/svm-stgi.md)