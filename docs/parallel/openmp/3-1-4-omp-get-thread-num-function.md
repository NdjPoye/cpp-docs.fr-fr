---
title: 3.1.4 fonction omp_get_thread_num | Documents Microsoft
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
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b7b968d103631dafcdd2132cb749ae8feed30085
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="314-ompgetthreadnum-function"></a>3.1.4 Fonction omp_get_thread_num
Le `omp_get_thread_num` fonction retourne le nombre de threads, au sein de son équipe, du thread d’exécution de la fonction. Le se trouve de thread nombre compris entre 0 et **omp_get_num_threads()**-1, inclus. Le thread principal de l’équipe est 0.  
  
 Le format est le suivant :  
  
```  
#include <omp.h>  
int omp_get_thread_num(void);  
```  
  
 Si elle est appelée à partir d’une région de série, `omp_get_thread_num` retourne 0. Si l’appelé à partir d’une région parallèle imbriquée qui est sérialisée, cette fonction retourne 0.  
  
## <a name="cross-references"></a>Références externes :  
  
-   `omp_get_num_threads`fonction, consultez [Section 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) à la page 37.