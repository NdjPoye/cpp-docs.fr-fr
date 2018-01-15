---
title: "A 3 à l’aide de régions parallèles | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 575216a1-960a-47f7-9c82-7f660291fcfe
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: be3489e924dab7faa50d26c7cb89af67b4034ca5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="a3---using-parallel-regions"></a>A.3   Utilisation des régions parallèles
Le `parallel` directive ([Section 2.3](../../parallel/openmp/2-3-parallel-construct.md) page 8) peut être utilisé dans les programmes parallèles de granularité grossière. Dans l’exemple suivant, chaque thread dans la région parallèle décide quelle partie du tableau global `x` travailler, en fonction du nombre de threads :  
  
```  
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)  
{  
    iam = omp_get_thread_num();  
    np =  omp_get_num_threads();  
    ipoints = npoints / np;  
    subdomain(x, iam, ipoints);  
}  
```