---
title: omp_set_num_threads | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_set_num_threads
dev_langs: C++
helpviewer_keywords: omp_set_num_threads OpenMP function
ms.assetid: dae0bf3f-cd7a-4413-89de-6149ac1f4fa7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 66fc3984342b75b2fed35ed9a5c58d0848d41b2c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="ompsetnumthreads"></a>omp_set_num_threads
Définit le nombre de threads dans les régions parallèles suivantes, sauf si un [num_threads](../../../parallel/openmp/reference/num-threads.md) clause.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void omp_set_num_threads(  
   int num_threads  
);  
```  
  
## <a name="remarks"></a>Remarques  
 où,  
  
 `num_threads`  
 Le nombre de threads dans la région parallèle.  
  
## <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [3.1.1 fonction omp_set_num_threads](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md).  
  
## <a name="example"></a>Exemple  
 Consultez [omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md) pour obtenir un exemple d’utilisation de `omp_set_num_threads`.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../../parallel/openmp/reference/openmp-functions.md)