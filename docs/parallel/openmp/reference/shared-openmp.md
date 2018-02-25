---
title: "partagé (OpenMP) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Shared
dev_langs:
- C++
helpviewer_keywords:
- shared OpenMP clause
ms.assetid: 7887dc95-67a2-462f-a3a2-8e0632bf5d04
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 90491e6e8b415c79e21b4fa518f7e60327ac823e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="shared-openmp"></a>shared (OpenMP)
Spécifie qu’une ou plusieurs variables doivent être partagées entre tous les threads.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
shared(var)  
```  
  
## <a name="remarks"></a>Notes  
 où,  
  
 `var`  
 Variables de plus d’un à partager. Si plusieurs variables est spécifié, séparez les noms de variables par des virgules.  
  
## <a name="remarks"></a>Notes  
 Est également possible de partager les variables entre les threads avec le [copyprivate](../../../parallel/openmp/reference/copyprivate.md) clause.  
  
 `shared` s’applique aux directives suivantes :  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Pour plus d’informations, consultez [2.7.2.4 partagé](../../../parallel/openmp/2-7-2-4-shared.md).  
  
## <a name="example"></a>Exemple  
 Consultez [privé](../../../parallel/openmp/reference/private-openmp.md) pour obtenir un exemple d’utilisation de `shared`.  
  
## <a name="see-also"></a>Voir aussi  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)