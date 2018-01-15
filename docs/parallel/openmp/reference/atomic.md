---
title: atomique | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: atomic
dev_langs: C++
helpviewer_keywords: atomic OpenMP directive
ms.assetid: 275e0338-cf2f-4525-97b5-696250000df7
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1e3d190504a0e4caab864c637d7053836b01f88f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="atomic"></a>atomique
Spécifie qu’un emplacement de mémoire qui sera mise à jour atomiquement.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#pragma omp atomic  
   expression  
```  
  
#### <a name="parameters"></a>Paramètres  
 `expression`  
 L’instruction contenant la valeur lvalue dont l’emplacement de mémoire que vous souhaitez protéger contre plusieurs écritures. Pour plus d’informations sur les formes expression juridique, consultez la spécification OpenMP.  
  
## <a name="remarks"></a>Notes  
 Le `atomic` directive prend en charge aucune clauses OpenMP.  
  
 Pour plus d’informations, consultez [2.6.4 atomique construire](../../../parallel/openmp/2-6-4-atomic-construct.md).  
  
## <a name="example"></a>Exemple  
  
```  
// omp_atomic.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
#define MAX 10  
  
int main() {  
   int count = 0;  
   #pragma omp parallel num_threads(MAX)  
   {  
      #pragma omp atomic  
      count++;  
   }  
   printf_s("Number of threads: %d\n", count);  
}  
```  
  
```Output  
Number of threads: 10  
```  
  
## <a name="see-also"></a>Voir aussi  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)