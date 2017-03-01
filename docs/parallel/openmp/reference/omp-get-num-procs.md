---
title: omp_get_num_procs | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- omp_get_num_procs
dev_langs:
- C++
helpviewer_keywords:
- omp_get_num_procs OpenMP function
ms.assetid: 14a10b8f-e59b-4211-a292-687648c9f760
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 5968fcaa13fb8e0deaca7da49f2db93e7cca10fb
ms.lasthandoff: 02/24/2017

---
# <a name="ompgetnumprocs"></a>omp_get_num_procs
Retourne le nombre de processeurs qui sont disponibles lorsque la fonction est appelée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int omp_get_num_procs();  
```  
  
## <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [3.1.5 fonction omp_get_num_procs](../../../parallel/openmp/3-1-5-omp-get-num-procs-function.md).  
  
## <a name="example"></a>Exemple  
  
```  
// omp_get_num_procs.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    printf_s("%d\n", omp_get_num_procs( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_num_procs( ));  
        }  
}  
```  
  
```Output  
// Expect the following output when the example is run on a two-processor machine:  
2  
2  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../../parallel/openmp/reference/openmp-functions.md)
