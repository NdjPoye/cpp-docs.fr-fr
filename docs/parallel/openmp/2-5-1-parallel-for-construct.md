---
title: "2.5.1 parallèle construction for | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a233e7ed-2462-4f7a-9a5d-556ab9f363d8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7dcd763b68a78e11c3c33bf3d750a26e88ad02ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="251-parallel-for-construct"></a>2.5.1 Construction for parallèle
Le **parallèles pour** la directive est un raccourci pour un **parallèles** région qui contient un seul **pour** la directive. La syntaxe de la **parallèles pour** la directive est la suivante :  
  
```  
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop  
```  
  
 Cette directive permet toutes les clauses de la **parallèles** la directive et le **pour** directive, sauf le `nowait` clause, avec une signification identique et des restrictions. La sémantique est identique à spécifier explicitement un **parallèles** directive immédiatement suivie d’un **pour** la directive.  
  
## <a name="cross-references"></a>Références externes :  
  
-   **parallèle** directive, voir [Section 2.3](../../parallel/openmp/2-3-parallel-construct.md) page 8.  
  
-   **pour** directive, voir [Section 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) à la page 11.  
  
-   Les clauses d’attributs de données, consultez [2.7.2 Clauses d’attributs de partage de données](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) page 25.