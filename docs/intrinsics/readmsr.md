---
title: "__readmsr | Microsoft Docs"
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
  - "__readmsr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Read Model Specific Register, instruction"
  - "rdmsr, instruction"
  - "__readmsr, intrinsèque"
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __readmsr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère des instructions d' `rdmsr` , qui lit le registre de recherche spécifié par `register` et retourne sa valeur.  
  
## Syntaxe  
  
```  
__int64 __readmsr(   
   int register   
);  
```  
  
#### Paramètres  
 \[in\] `register`  
 Le registre spécifique de modèle à lire.  
  
## Valeur de retour  
 la valeur dans le registre spécifié.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__readmsr`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette fonction est uniquement disponible en mode noyau, et la routine est uniquement disponible sous forme intrinsèque.  
  
 Pour plus d'informations, consultez la documentation d'AMD.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)