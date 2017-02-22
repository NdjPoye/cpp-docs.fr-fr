---
title: "__svm_skinit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_skinit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SKINIT, instruction"
  - "__svm_skinit, intrinsèque"
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __svm_skinit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Initialise le chargement vérifié du logiciel sécurisé, tel qu'un écran d'ordinateurs virtuels.  
  
## Syntaxe  
  
```  
void __svm_skinit(  
   int SLB  
);  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`SLB`|L'adresse physique 32 bits à un octet de sécuriser le bloc de chargeur \(SLB\).|  
  
## Notes  
 La fonction d' `__svm_skinit` équivaut à l'instruction machine d' `SKINIT` .  Cette fonction fait partie d'un système de sécurité qui utilise le processeur et un module approuvé de \(TPM\) plateforme pour rechercher et charger le logiciel approuvé appelé cœur de sécurité \(SK\).  Le moniteur d'ordinateurs virtuels est un exemple d'un noyau de sécurité.  Le système de sécurité vérifie les composants de programme chargés pendant le processus d'initialisation, et protège les composants de la falsification par les interruptions, l'accès de périphérique, ou un autre programme si l'ordinateur est un multiprocesseur.  
  
 Le paramètre d' `SLB` spécifie l'adresse physique d'un bloc de mémoire limitée appelé *le bloc de chargeur sécurisé \(SLB\)* .  Le SLB contient un programme appelé le chargeur sécurisé qui génère l'environnement d'exploitation de l'ordinateur, et charge par la suite le noyau de sécurité.  
  
 cette fonction prend en charge l'interaction du moniteur d'ordinateurs virtuels d'un hôte avec un système d'exploitation invité et ses applications.  Pour plus d'informations, recherchez le document, « le volume manuel 2 du programmeur d'architectures AMD64 : programmation système, » numéro de document 24593, révision 3,11, [AMD corporation](http://go.microsoft.com/fwlink/?LinkId=23746) au site.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__svm_skinit`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)