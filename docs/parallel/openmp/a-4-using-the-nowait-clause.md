---
title: A.4 à l’aide de la Clause nowait | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d3de2111-05ea-4ee3-a66c-57bd988712af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d1de6b5e86d600ee1b3c2fa2c29fe014f9cb768
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="a4---using-the-nowait-clause"></a>A.4   Utilisation de la clause nowait
S’il existe plusieurs boucles indépendantes dans une région parallèle, vous pouvez utiliser la `nowait` clause ([Section 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) à la page 11) afin d’éviter la barrière implicite à la fin de la `for` directive, comme suit :  
  
```  
#pragma omp parallel  
{  
    #pragma omp for nowait  
        for (i=1; i<n; i++)  
             b[i] = (a[i] + a[i-1]) / 2.0;  
    #pragma omp for nowait  
        for (i=0; i<m; i++)  
            y[i] = sqrt(z[i]);  
}  
```