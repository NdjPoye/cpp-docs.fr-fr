---
title: A.5 à l’aide de la Directive critique | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1a41e9664faaca24b6708c737a044828eb460bd
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="a5---using-the-critical-directive"></a>A.5   Utilisation de la directive critical
L’exemple suivant inclut plusieurs `critical` directives ([Section 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) page 18). L’exemple illustre un modèle de file d’attente dans laquelle une tâche est dépilée et d’exécution. Pour vous protéger contre plusieurs threads de retrait de la même tâche, l’opération de retrait doit être dans un `critical` section. Étant donné que les deux files d’attente dans cet exemple sont indépendants, ils sont protégés par `critical` directives avec des noms différents, *xaxis* et *yaxis*.  
  
```  
#pragma omp parallel shared(x, y) private(x_next, y_next)  
{  
    #pragma omp critical ( xaxis )  
        x_next = dequeue(x);  
    work(x_next);  
    #pragma omp critical ( yaxis )  
        y_next = dequeue(y);  
    work(y_next);  
}  
```