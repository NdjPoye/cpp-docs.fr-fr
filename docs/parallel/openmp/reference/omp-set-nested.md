---
title: omp_set_nested | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- omp_set_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_set_nested OpenMP function
ms.assetid: fa1cb08c-7b8b-42c9-8654-2c33dcffb5b6
caps.latest.revision: 13
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
ms.openlocfilehash: d120c4eca49a917cb34fc3b8a873c08f5e2815eb
ms.lasthandoff: 02/24/2017

---
# <a name="ompsetnested"></a>omp_set_nested
Active le parallélisme imbriqué.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void omp_set_nested(  
   int val  
);  
```  
  
## <a name="remarks"></a>Notes  
 où,  
  
 `val`  
 Si elle est différente de zéro, Active le parallélisme imbriqué. Si zéro, désactive le parallélisme imbriqué.  
  
## <a name="remarks"></a>Notes  
 OMP imbriqué parallélisme peut être activé avec `omp_set_nested`, ou en définissant le [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md) variable d’environnement.  
  
 Le paramètre de `omp_set_nested` remplacera le paramètre de la `OMP_NESTED` variable d’environnement.  
  
 Lorsque activé, la variable d’environnement peut interrompre un programme opérationnel dans le cas contraire, car le nombre de threads augmente de façon exponentielle lors de l’imbrication de régions parallèles.  Par exemple, une fonction que récursivement 6 fois avec le nombre de threads OMP défini sur 4 requiert 4 096 (4 à la puissance de 6) les threads en général, diminuent les performances de votre application si le nombre de threads dépasse le nombre de processeurs. Une exception à cela serait de qu'applications liées aux e/s.  
  
 Utilisez [omp_get_nested](../../../parallel/openmp/reference/omp-get-nested.md) pour afficher le paramètre actuel de `omp_set_nested`.  
  
 Pour plus d’informations, consultez [3.1.9 fonction omp_set_nested](../../../parallel/openmp/3-1-9-omp-set-nested-function.md).  
  
## <a name="example"></a>Exemple  
  
```  
// omp_set_nested.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    omp_set_nested(1);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_nested( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_nested( ));  
        }  
}  
```  
  
```Output  
1  
1  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../../parallel/openmp/reference/openmp-functions.md)
