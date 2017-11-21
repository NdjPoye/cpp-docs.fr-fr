---
title: 3.2.3 fonctions omp_set_lock and omp_set_nest_lock | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5f78307023091b2e9d17ca3ff8fa2d3214c458cf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="323-ompsetlock-and-ompsetnestlock-functions"></a>3.2.3 Fonctions omp_set_lock and omp_set_nest_lock
Chacune de ces fonctions bloque le thread d’exécution de la fonction jusqu'à ce que le verrou spécifié n’est disponible et qu’il définit ensuite le verrou. Un verrou simple n’est disponible que si elle est déverrouillée. Un verrou pouvant est disponible s’il est déverrouillé, ou si elle est déjà détenu par le thread d’exécution de la fonction. Le format est le suivant :  
  
```  
#include <omp.h>  
void omp_set_lock(omp_lock_t *lock);  
void omp_set_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Pour un verrou simple, l’argument de la `omp_set_lock` fonction doit pointer vers une variable initialisée de verrou. La propriété du verrou est accordée au thread d’exécution de la fonction.  
  
 Pour un verrou pouvant, l’argument de la `omp_set_nest_lock` fonction doit pointer vers une variable initialisée de verrou. Le nombre d’imbrication est incrémenté et le thread est accordé ou conserve, la propriété du verrou.