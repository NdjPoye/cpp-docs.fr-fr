---
title: "firstprivate | Microsoft Docs"
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
  - "firstprivate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "firstprivate OpenMP clause"
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# firstprivate
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Spécifie que chaque thread doit avoir sa propre instance d'une variable, et que la variable doit être initialisée avec la valeur de la variable, car elle existe avant que l'élément parallèle.  
  
## Syntaxe  
  
```  
firstprivate(var)  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`var`|La variable d'avoir des instances dans chaque thread et qui sera initialisée avec la valeur de la variable, car elle existe avant que l'élément parallèle.  Si plusieurs la variable est spécifiée, les noms de variables séparés par une virgule.|  
  
## Notes  
  
## Notes  
 `firstprivate` s'applique aux directives suivantes :  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [single](../../../parallel/openmp/reference/single.md)  
  
 Pour plus d'informations, consultez [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md).  
  
## Exemple  
 Pour obtenir un exemple d'utilisation `firstprivate`, consultez l'exemple de [private](../../../parallel/openmp/reference/private-openmp.md).  
  
## Voir aussi  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)