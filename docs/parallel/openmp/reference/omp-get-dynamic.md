---
title: omp_get_dynamic | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_get_dynamic
dev_langs:
- C++
helpviewer_keywords:
- omp_get_dynamic OpenMP function
ms.assetid: efa843c5-7266-4a75-8db3-22992663d9db
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 865104055fc98946c09152f328f4812af0120e64
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="ompgetdynamic"></a>omp_get_dynamic
Retourne une valeur qui indique si le nombre de threads disponibles dans une région parallèle suivante peut être ajusté par le temps d’exécution.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int omp_get_dynamic();  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Si elle est différente de zéro, l’ajustement dynamique de threads est activée.  
  
## <a name="remarks"></a>Notes  
 L’ajustement dynamique de threads est spécifié avec [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) et [OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md).  
  
 Pour plus d’informations, consultez [3.1.7 fonction omp_set_dynamic](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).  
  
## <a name="example"></a>Exemple  
 Consultez [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) pour obtenir un exemple d’utilisation de `omp_get_dynamic`.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../../parallel/openmp/reference/openmp-functions.md)