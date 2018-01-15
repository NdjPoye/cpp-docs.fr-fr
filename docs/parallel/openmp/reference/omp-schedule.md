---
title: OMP_SCHEDULE | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OMP_SCHEDULE
dev_langs: C++
helpviewer_keywords: OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2295a801-e584-4d2f-826f-7ca4c88846a6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8aa1406b490128657da19f7c48c958d382850d96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ompschedule"></a>OMP_SCHEDULE
Modifie le comportement de la [planification](../../../parallel/openmp/reference/schedule.md) clause lorsque `schedule(runtime)` est spécifié dans un `for` ou `parallel for` la directive.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## <a name="remarks"></a>Notes  
 où,  
  
 `size`(facultatif)  
 Spécifie la taille d’itérations. `size`doit être un entier positif. La valeur par défaut est 1, sauf quand `type` est statique. Non valide lorsque `type` est `runtime`.  
  
 `type`  
 Le type de planification :  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
## <a name="remarks"></a>Notes  
 La valeur par défaut dans l’implémentation Visual C++ de la norme OpenMP est `OMP_SCHEDULE=static,0`.  
  
 Pour plus d’informations, consultez [OMP_SCHEDULE 4.1](../../../parallel/openmp/4-1-omp-schedule.md).  
  
## <a name="example"></a>Exemple  
 La commande suivante définit le **OMP_SCHEDULE** variable d’environnement :  
  
```  
set OMP_SCHEDULE="guided,2"  
```  
  
 La commande suivante affiche le paramètre actuel de la **OMP_SCHEDULE** variable d’environnement :  
  
```  
set OMP_SCHEDULE  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Variables d’environnement](../../../parallel/openmp/reference/openmp-environment-variables.md)