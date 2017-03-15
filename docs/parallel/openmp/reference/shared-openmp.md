---
title: "shared (OpenMP) | Microsoft Docs"
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
  - "Shared"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "shared OpenMP clause"
ms.assetid: 7887dc95-67a2-462f-a3a2-8e0632bf5d04
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# shared (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Spécifie qu'une ou plusieurs variables doivent être partagées par tous les threads.  
  
## Syntaxe  
  
```  
shared(var)  
```  
  
## Notes  
 où,  
  
 `var`  
 Un plus plusieurs variables à partager.  Si plusieurs la variable est spécifiée, les noms de variables séparés par une virgule.  
  
## Notes  
 Une autre méthode pour partager des variables entre les threads avec la clause de [copyprivate](../../../parallel/openmp/reference/copyprivate.md) .  
  
 `shared` s'applique aux directives suivantes :  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Pour plus d'informations, consultez [2.7.2.4 shared](../../../parallel/openmp/2-7-2-4-shared.md).  
  
## Exemple  
 Consultez [private](../../../parallel/openmp/reference/private-openmp.md) pour un exemple d'utilisation `shared`.  
  
## Voir aussi  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)