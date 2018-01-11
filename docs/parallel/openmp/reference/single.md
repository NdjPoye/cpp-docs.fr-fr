---
title: seul | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Single
dev_langs: C++
helpviewer_keywords: single OpenMP directive
ms.assetid: 85cf94fb-cb9c-4d82-8609-adffa9f552e1
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8eabac06acc78aec46c86cf8a7dcbb2d5854c941
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="single"></a>unique
Permet de spécifier qu’une section de code doit être exécutée sur un seul thread, pas nécessairement le thread principal.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#pragma omp single [clauses]   
{  
   code_block   
}  
```  
  
#### <a name="parameters"></a>Paramètres  
 `clause`(facultatif)  
 Zéro ou plusieurs clauses. Consultez la section Notes pour obtenir la liste des clauses prises en charge par **unique**.  
  
## <a name="remarks"></a>Notes  
 Le **unique** directive prend en charge les clauses OpenMP suivantes :  
  
-   [copyprivate](../../../parallel/openmp/reference/copyprivate.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
 Le [master](../../../parallel/openmp/reference/master.md) directive vous permet de spécifier qu’une section de code doit être exécutée uniquement sur le thread principal.  
  
 Pour plus d’informations, consultez [2.4.3 unique construire](../../../parallel/openmp/2-4-3-single-construct.md).  
  
## <a name="example"></a>Exemple  
  
```  
// omp_single.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(2)  
   {  
      #pragma omp single  
      // Only a single thread can read the input.  
      printf_s("read input\n");  
  
      // Multiple threads in the team compute the results.  
      printf_s("compute results\n");  
  
      #pragma omp single  
      // Only a single thread can write the output.  
      printf_s("write output\n");  
    }  
}  
```  
  
```Output  
read input  
compute results  
compute results  
write output  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)