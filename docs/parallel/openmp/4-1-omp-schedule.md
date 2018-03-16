---
title: 4.1 OMP_SCHEDULE | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 330e5ea576e3cd779a7c17c21d00b6459f5e7043
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="41-ompschedule"></a>4.1 OMP_SCHEDULE
**OMP_SCHEDULE** s’applique uniquement aux **pour** et **parallèles pour** directives qui ont le type de planification **runtime**. La taille de segment et de type de planification pour toutes les boucles de ce type peut être définie au moment de l’exécution en définissant cette variable d’environnement pour les types de planification reconnue et facultative *chunk_size*.  
  
 Pour **pour** et **parallèles pour** directives qui ont un type de planification autres que **runtime**, **OMP_SCHEDULE** est ignoré. La valeur par défaut pour cette variable d’environnement est défini par l’implémentation. Si le paramètre facultatif *chunk_size* est définie, la valeur doit être positive. Si *chunk_size* n’est pas définie, la valeur 1 est donnée, sauf dans le cas d’un **statique** planification. Pour un **statique** calendrier, la taille de segment par défaut est définie à l’espace d’itération de boucle divisé par le nombre de threads appliqué à la boucle.  
  
 Exemple :  
  
```  
setenv OMP_SCHEDULE "guided,4"  
setenv OMP_SCHEDULE "dynamic"  
```  
  
## <a name="cross-references"></a>Références externes :  
  
-   **pour** directive, voir [Section 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) à la page 11.  
  
-   **parallèle pour** directive, voir [Section 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) page 16.