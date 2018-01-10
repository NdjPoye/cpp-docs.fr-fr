---
title: omp_destroy_nest_lock | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_destroy_nest_lock
dev_langs: C++
helpviewer_keywords: omp_destroy_nest_lock OpenMP function
ms.assetid: 0ab1352b-668f-43dd-b441-31ec4cc53e68
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8949f9fe49efab6b9a5fc2dd5a54b53ba58d9e60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ompdestroynestlock"></a>omp_destroy_nest_lock
N’initialise pas un verrou pouvant.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void omp_destroy_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>Notes  
 où,  
  
 `lock`  
 Une variable de type [omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) qui a été initialisée avec [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md).  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [3.2.2 fonctions omp_destroy_lock et omp_destroy_nest_lock fonctions](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).  
  
## <a name="example"></a>Exemple  
 Consultez [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) pour obtenir un exemple d’utilisation de `omp_destroy_nest_lock`.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../../parallel/openmp/reference/openmp-functions.md)