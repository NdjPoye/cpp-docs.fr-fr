---
title: "A.6 à l’aide de la Clause lastprivate | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1744787e1dfb90fa9af93db5dba4eecd600b4334
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="a6---using-the-lastprivate-clause"></a>A.6   Utilisation de la clause lastprivate
Exécution correcte parfois dépend de la valeur de la dernière itération d’une boucle assigne à une variable. Ces programmes doivent répertorier toutes les variables de ce type en tant qu’arguments à une `lastprivate` clause ([Section 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) page 27) afin que les valeurs des variables sont les mêmes que lorsque la boucle est exécutée de manière séquentielle.  
  
```  
#pragma omp parallel  
{  
   #pragma omp for lastprivate(i)  
      for (i=0; i<n-1; i++)  
         a[i] = b[i] + b[i+1];  
}  
a[i]=b[i];  
```  
  
 Dans l’exemple précédent, la valeur de `i` à la fin de la région parallèle est égale à `n-1`, comme dans le cas séquentiel.