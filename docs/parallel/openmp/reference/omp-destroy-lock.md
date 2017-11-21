---
title: fonctions omp_destroy_lock | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_destroy_lock
dev_langs: C++
helpviewer_keywords: omp_destroy_lock OpenMP function
ms.assetid: b73ab036-b76f-4e42-82ff-c89db2edf7c0
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2d15a860ecb897d107b0ae27665e659404a32969
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="ompdestroylock"></a>omp_destroy_lock
N’initialise pas un verrou.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void omp_destroy_lock(  
   omp_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>Remarques  
 où,  
  
 `lock`  
 Une variable de type [omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md) qui a été initialisée avec [fonctions omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md).  
  
## <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [3.2.2 fonctions omp_destroy_lock et omp_destroy_nest_lock fonctions](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).  
  
## <a name="example"></a>Exemple  
 Consultez [fonctions omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md) pour obtenir un exemple d’utilisation de `omp_destroy_lock`.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../../parallel/openmp/reference/openmp-functions.md)