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
ms.openlocfilehash: c29ec07f9a912fb66adc391465885da8030cc466
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="ompschedule"></a>OMP_SCHEDULE
Modifie le comportement de la [planification](../../../parallel/openmp/reference/schedule.md) clause lorsque `schedule(runtime)` est spécifié dans un `for` ou `parallel for` la directive.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## <a name="remarks"></a>Remarques  
 où,  
  
 `size`(facultatif)  
 Spécifie la taille d’itérations. `size`doit être un entier positif. La valeur par défaut est 1, sauf quand `type` est statique. Non valide lorsque `type` est `runtime`.  
  
 `type`  
 Le type de planification :  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
## <a name="remarks"></a>Remarques  
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