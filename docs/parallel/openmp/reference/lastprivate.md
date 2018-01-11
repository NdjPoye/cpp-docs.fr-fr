---
title: lastprivate | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: lastprivate
dev_langs: C++
helpviewer_keywords: lastprivate OpenMP clause
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7ad36a68078856706a4d1d994e72fd001c36dbaf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
 `lastprivate`s’applique aux directives suivantes :  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Pour plus d’informations, consultez [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md).  
  
## <a name="example"></a>Exemple  
 Consultez [planification](../../../parallel/openmp/reference/schedule.md) pour obtenir un exemple d’utilisation de `lastprivate` clause.  
  
## <a name="see-also"></a>Voir aussi  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)