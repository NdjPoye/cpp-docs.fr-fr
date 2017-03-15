---
title: "2.5.2 parallel sections Construct | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.5.2 parallel sections Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La directive de **mettez en parallèle les sections** fournit un formulaire de raccourci pour spécifier une zone de **parallèle** contenant une seule directive unique de **sections** .  La sémantique est identique à spécifier explicitement une directive de **parallèle** immédiatement suivie d'une directive de **sections** .  La syntaxe de la directive de **sections parallèles** est la suivante :  
  
```  
#pragma omp parallel sections  [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-line  
      structured-block  ]  
   ...  
}  
```  
  
 *La clause* peut avoir l'une des clauses reçues par les directives de **parallèle** et de **sections** , à l'exception de la clause de **nowait** .  
  
## Références croisées :  
  
-   la directive de**parallèle** , consultez [section 2,3](../../parallel/openmp/2-3-parallel-construct.md) à la page 8.  
  
-   la directive de**sections** , consultez [section 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) à la page 14.