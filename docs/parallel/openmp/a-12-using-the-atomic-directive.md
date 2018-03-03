---
title: "A.12 à l’aide de la Directive atomique | Documents Microsoft"
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
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9aa619d9bbe635a41d15a39d6c05780a4416520e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="a12---using-the-atomic-directive"></a>A.12   Utilisation de la directive atomic
L’exemple suivant permet d’éviter des conditions de concurrence (mises à jour simultanées d’un élément de *x* par plusieurs threads) à l’aide de la `atomic` directive ([Section 2.6.4](../../parallel/openmp/2-6-4-atomic-construct.md) à la page 19) :  
  
```  
#pragma omp parallel for shared(x, y, index, n)  
    for (i=0; i<n; i++)   
    {  
        #pragma omp atomic  
            x[index[i]] += work1(i);  
        y[i] += work2(i);  
    }  
```  
  
 L’avantage d’utiliser le `atomic` directive dans cet exemple est qu’il permet des mises à jour de deux éléments de x pour être exécutées en parallèle. Si un `critical` directive ([Section 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) page 18) ont été utilisés à la place, puis toutes les mises à jour à des éléments de *x* sont exécutées en série (mais pas dans les garanties ordre).  
  
 Notez que la `atomic` directive s’applique uniquement à l’instruction C ou C++ qui la suit immédiatement.  Par conséquent, les éléments de *y* ne sont pas mises à jour de manière atomique dans cet exemple.