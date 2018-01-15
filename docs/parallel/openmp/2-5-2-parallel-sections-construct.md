---
title: "2.5.2 construction de sections parallèles | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e3a76a950d547effccf0b50fa04799814597bc5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="252-parallel-sections-construct"></a>2.5.2 Construction de sections parallèles
Le **de sections parallèles** directive fournit un formulaire contextuel pour spécifier un **parallèles** région contenant un seul **sections** directive. La sémantique est identique à spécifier explicitement un **parallèles** directive immédiatement suivie d’un **sections** directive. La syntaxe de la **de sections parallèles** la directive est la suivante :  
  
```  
#pragma omp parallel sections  [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-linestructured-block  ]  
   ...  
}  
```  
  
 Le *clause* peut prendre l’une clauses de l’acceptation par la **parallèles** et **sections** directives, sauf le **nowait** clause.  
  
## <a name="cross-references"></a>Références externes :  
  
-   **parallèle** directive, voir [Section 2.3](../../parallel/openmp/2-3-parallel-construct.md) page 8.  
  
-   **sections** directive, voir [Section 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) page 14.