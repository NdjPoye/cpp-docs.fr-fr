---
title: copyin | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- copyin
dev_langs:
- C++
helpviewer_keywords:
- copyin OpenMP clause
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae680b2af468b9b11a7d2de44966ad554eec0150
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
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
 `copyin` s’applique aux directives suivantes :  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Pour plus d’informations, consultez [2.7.2.7 copyin](../../../parallel/openmp/2-7-2-7-copyin.md).  
  
## <a name="example"></a>Exemple  
 Consultez [threadprivate](../../../parallel/openmp/reference/threadprivate.md) pour obtenir un exemple d’utilisation de `copyin`.  
  
## <a name="see-also"></a>Voir aussi  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)