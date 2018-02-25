---
title: "parallèle | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- parallel
dev_langs:
- C++
helpviewer_keywords:
- parallel OpenMP directive
ms.assetid: b8e90073-e85b-4d39-8ed8-0364441794fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9293a70ce0615adf1e40bcb19b1706d9e39d4cca
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="parallel"></a>parallel
Définit une région parallèle, ce qui est le code qui sera exécuté par plusieurs threads en parallèle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#pragma omp parallel [clauses]  
{  
   code_block  
}  
```  
  
## <a name="remarks"></a>Notes  
 où,  
  
 `clause`(facultatif)  
 Zéro ou plusieurs clauses.  Consultez la section Notes pour obtenir la liste des clauses prises en charge par **parallèles**.  
  
## <a name="remarks"></a>Notes  
 Le **parallèles** directive prend en charge les clauses OpenMP suivantes :  
  
-   [copyin](../../../parallel/openmp/reference/copyin.md)  
  
-   [default](../../../parallel/openmp/reference/default-openmp.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [if](../../../parallel/openmp/reference/if-openmp.md)  
  
-   [num_threads](../../../parallel/openmp/reference/num-threads.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
-   [shared](../../../parallel/openmp/reference/shared-openmp.md)  
  
 **parallèle** peut également être utilisé avec le [sections](../../../parallel/openmp/reference/sections-openmp.md) et [pour](../../../parallel/openmp/reference/for-openmp.md) directives.  
  
 Pour plus d’informations, consultez [2.3 construction parallèle](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment définir le nombre de threads et de définir une région parallèle. Par défaut, le nombre de threads est égal au nombre de processeurs logiques sur l’ordinateur. Par exemple, si vous avez un ordinateur avec un processeur physique qui a l’hyperthreading activé, il aura deux processeurs logiques et, par conséquent, deux threads.  
  
```  
// omp_parallel.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(4)  
   {  
      int i = omp_get_thread_num();  
      printf_s("Hello from thread %d\n", i);  
   }  
}  
```  
  
```Output  
Hello from thread 0  
Hello from thread 1  
Hello from thread 2  
Hello from thread 3  
```  
  
## <a name="comment"></a>Commentaire  
 Notez que l’ordre de sortie peut varier sur des ordinateurs différents.  
  
## <a name="see-also"></a>Voir aussi  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)