---
title: "A.5 à l’aide de la Directive critique | Documents Microsoft"
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
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7cf4170fae6792906db29c90f61f067886b00f1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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