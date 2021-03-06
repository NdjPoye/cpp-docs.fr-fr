---
title: fonctions omp_unset_lock | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_unset_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_unset_lock OpenMP function
ms.assetid: 68fcb728-040b-4bad-979e-aaecb9097a4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 243ff6d2336d3e293d009f82ba4a39243e076f94
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="ompunsetlock"></a>omp_unset_lock
Libère un verrou.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void omp_unset_lock(  
   omp_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>Notes  
 où,  
  
 `lock`  
 Une variable de type [omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md) qui a été initialisée avec [fonctions omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md), détenu par le thread et en cours d’exécution dans la fonction.  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [3.2.4 fonctions omp_unset_lock and omp_unset_nest_lock fonctions](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).  
  
## <a name="example"></a>Exemple  
 Consultez [fonctions omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md) pour obtenir un exemple d’utilisation de `omp_unset_lock`.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../../parallel/openmp/reference/openmp-functions.md)