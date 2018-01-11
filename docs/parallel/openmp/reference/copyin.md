---
title: copyin | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: copyin
dev_langs: C++
helpviewer_keywords: copyin OpenMP clause
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3190c1f6914ae8ea24b968a8cf286de1867938cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="copyin"></a>copyin
Permet aux threads d’accéder à valeur du thread principal, pour un [threadprivate](../../../parallel/openmp/reference/threadprivate.md) variable.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
copyin(var)  
```  
  
## <a name="remarks"></a>Notes  
 où,  
  
 `var`  
 Le `threadprivate` variable qui sera initialisée avec la valeur de la variable dans le thread principal, tel qu’il existe avant la construction parallèle.  
  
## <a name="remarks"></a>Notes  
 `copyin`s’applique aux directives suivantes :  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Pour plus d’informations, consultez [2.7.2.7 copyin](../../../parallel/openmp/2-7-2-7-copyin.md).  
  
## <a name="example"></a>Exemple  
 Consultez [threadprivate](../../../parallel/openmp/reference/threadprivate.md) pour obtenir un exemple d’utilisation de `copyin`.  
  
## <a name="see-also"></a>Voir aussi  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)