---
title: lastprivate | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- lastprivate
dev_langs:
- C++
helpviewer_keywords:
- lastprivate OpenMP clause
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7945edb879d81bb50753619c1206b9da575dbcda
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="lastprivate"></a>lastprivate
Spécifie que la version du contexte englobant de la variable est définie égale à la version privée du thread exécute la dernière itération (construction de la boucle for) ou la dernière section (sections #pragma).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
lastprivate(var)  
```  
  
## <a name="remarks"></a>Notes  
 où,  
  
 `var`  
 La variable est égale à la version privée du thread exécute la dernière itération (construction de la boucle for) ou la dernière section (sections #pragma).  
  
## <a name="remarks"></a>Notes  
 `lastprivate` s’applique aux directives suivantes :  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Pour plus d’informations, consultez [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md).  
  
## <a name="example"></a>Exemple  
 Consultez [planification](../../../parallel/openmp/reference/schedule.md) pour obtenir un exemple d’utilisation de `lastprivate` clause.  
  
## <a name="see-also"></a>Voir aussi  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)