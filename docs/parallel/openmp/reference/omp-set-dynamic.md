---
title: omp_set_dynamic | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- omp_set_dynamic
dev_langs:
- C++
helpviewer_keywords:
- omp_set_dynamic OpenMP function
ms.assetid: 3845faf2-a0ca-45a5-ae70-2a7a6164f1e8
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: b4313bee47101b91186da999f6f04430da5bca23
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="ompsetdynamic"></a>omp_set_dynamic
Indique que le nombre de threads disponibles dans la région parallèle suivante peut être ajusté par la durée d’exécution.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void omp_set_dynamic(  
   int val  
);  
```  
  
## <a name="remarks"></a>Remarques  
 où,  
  
 `val`  
 Une valeur qui indique si le nombre de threads disponibles dans la région parallèle suivante peut être ajusté par le runtime.  Si elle est différente de zéro, que le runtime peut régler le nombre de threads, si zéro, le runtime s’ajustent pas dynamiquement le nombre de threads.  
  
## <a name="remarks"></a>Remarques  
 Le nombre de threads ne dépassera jamais la valeur définie par [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) ou par [OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md).  
  
 Utilisez [omp_get_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md) pour afficher le paramètre actuel de `omp_set_dynamic`.  
  
 Le paramètre de `omp_set_dynamic` remplacera le paramètre de la [OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md) variable d’environnement.  
  
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
