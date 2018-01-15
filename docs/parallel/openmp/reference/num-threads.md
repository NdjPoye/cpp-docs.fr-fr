---
title: num_threads | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: num_threads
dev_langs: C++
helpviewer_keywords: num_threads OpenMP clause
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7289a843c33fbc9ba23d6006997dea8e09ba7c79
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="numthreads"></a>num_threads
Définit le nombre de threads dans une équipe de thread.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
num_threads(num)  
```  
  
## <a name="remarks"></a>Notes  
 où,  
  
 `num`  
 Le nombre de threads  
  
## <a name="remarks"></a>Notes  
 Le `num_threads` clause a les mêmes fonctionnalités que le [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) (fonction).  
  
 `num_threads`s’applique aux directives suivantes :  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Pour plus d’informations, consultez [2.3 construction parallèle](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## <a name="example"></a>Exemple  
 Consultez [parallèles](../../../parallel/openmp/reference/parallel.md) pour obtenir un exemple d’utilisation de `num_threads` clause.  
  
## <a name="see-also"></a>Voir aussi  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)