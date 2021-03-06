---
title: omp_get_nested | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_get_nested OpenMP function
ms.assetid: e9784847-516e-40d3-89f7-b8b6898d8667
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59900f0a1aba1cbc3bacc5cd1d8832e60aebe30b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="ompgetnested"></a>omp_get_nested
Retourne une valeur qui indique si le parallélisme imbriquée est activée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int omp_get_nested( );  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Si elle est différente de zéro, parallélisme imbriquée est activée.  
  
## <a name="remarks"></a>Notes  
 Parallélisme imbriquée est spécifié avec [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) et [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md).  
  
 Pour plus d’informations, consultez [3.1.10 fonction omp_get_nested](../../../parallel/openmp/3-1-10-omp-get-nested-function.md).  
  
## <a name="example"></a>Exemple  
 Consultez [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) pour obtenir un exemple d’utilisation de `omp_get_nested`.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../../parallel/openmp/reference/openmp-functions.md)