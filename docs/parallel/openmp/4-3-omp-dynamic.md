---
title: 4.3 OMP_DYNAMIC | Documents Microsoft
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
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 103067b28990854fb6522c19f4349a9607d65bab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="43-ompdynamic"></a>4.3 OMP_DYNAMIC
Le **OMP_DYNAMIC** variable d’environnement Active ou désactive l’ajustement dynamique du nombre de threads disponibles pour l’exécution des régions parallèles, sauf si l’ajustement dynamique est explicitement activée ou désactivée en appelant le **omp_set_dynamic** routine de bibliothèque. Sa valeur doit être **TRUE** ou **FALSE**.  
  
 Si la valeur **TRUE**, le nombre de threads utilisés pour exécuter les régions parallèles peut-être être modifié par l’environnement d’exécution pour optimiser l’utilisation de ressources système.  Si la valeur **FALSE**, ajustement dynamique est désactivée. La condition par défaut est défini par l’implémentation.  
  
 Exemple :  
  
```  
setenv OMP_DYNAMIC TRUE  
```  
  
## <a name="cross-references"></a>Références externes :  
  
-   Pour plus d’informations sur les régions parallèles, consultez [Section 2.3](../../parallel/openmp/2-3-parallel-construct.md) page 8.  
  
-   **omp_set_dynamic** , consultez [Section 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sur la page 39.