---
title: "2.5.1 parallel for Construct | Microsoft Docs"
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
ms.assetid: a233e7ed-2462-4f7a-9a5d-556ab9f363d8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.5.1 parallel for Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La directive de **parallèle pour** est un raccourci pour une zone de **parallèle** qui contient uniquement une directive unique de **pour** .  La syntaxe de la directive de **parallèle pour** est la suivante :  
  
```  
#pragma omp parallel for [clause[[,] clause] ...] new-line  
   for-loop  
```  
  
 Cette directive toutes les clauses de la directive de **parallèle** et de la directive de **pour** , à l'exception de la clause d' `nowait` , avec des significations et restrictions identiques.  La sémantique est identique à spécifier explicitement une directive de **parallèle** immédiatement suivie d'une directive de **pour** .  
  
## Références croisées :  
  
-   la directive de**parallèle** , consultez [section 2,3](../../parallel/openmp/2-3-parallel-construct.md) à la page 8.  
  
-   la directive de**pour** , consultez [section 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) à la page 11.  
  
-   Les clauses d'attribut de données, consultez [2.7.2 Data\-Sharing Attribute Clauses](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) à la page 25.