---
title: omp_set_dynamic | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_set_dynamic
dev_langs:
- C++
helpviewer_keywords:
- omp_set_dynamic OpenMP function
ms.assetid: 3845faf2-a0ca-45a5-ae70-2a7a6164f1e8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 00ee1ad4c42e0d2f1303854cbd050e5601d0c3cd
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="ompsetdynamic"></a>omp_set_dynamic
Indique que le nombre de threads disponibles dans une région parallèle suivante peut être ajusté par le temps d’exécution.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void omp_set_dynamic(  
   int val  
);  
```  
  
## <a name="remarks"></a>Notes  
 où,  
  
 `val`  
 Une valeur qui indique si le nombre de threads disponibles dans une région parallèle suivante peut être ajustée par le runtime.  Si elle est différente de zéro, que le runtime peut ajuster le nombre de threads, si zéro, le runtime s’ajustent pas dynamiquement le nombre de threads.  
  
## <a name="remarks"></a>Notes  
 Le nombre de threads ne dépassera jamais la valeur définie par [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) ou par [OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md).  
  
 Utilisez [omp_get_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md) pour afficher le paramètre actuel de `omp_set_dynamic`.  
  
 Le paramètre de `omp_set_dynamic` remplace le paramètre de la [OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md) variable d’environnement.  
  
 Pour plus d’informations, consultez [3.1.7 fonction omp_set_dynamic](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).  
  
## <a name="example"></a>Exemple  
  
```  
// omp_set_dynamic.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main()   
{  
    omp_set_dynamic(9);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_dynamic( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_dynamic( ));  
        }  
}  
```  
  
```Output  
1  
1  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../../parallel/openmp/reference/openmp-functions.md)