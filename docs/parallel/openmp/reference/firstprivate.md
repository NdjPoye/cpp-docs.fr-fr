---
title: firstprivate | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: firstprivate
dev_langs: C++
helpviewer_keywords: firstprivate OpenMP clause
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8c7d4a5ba23e343f7858bf3320ed05ebce84f1c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="firstprivate"></a>firstprivate
Spécifie que chaque thread doit avoir sa propre instance d’une variable, et que la variable doit être initialisée avec la valeur de la variable, car il existe avant la construction parallèle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
firstprivate(var)  
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`var`|La variable à avoir des instances dans chaque thread et qui sera être initialisée avec la valeur de la variable, car il existe avant la construction parallèle. Si plusieurs variables est spécifié, séparez les noms de variables par des virgules.|  
  
## <a name="remarks"></a>Notes  
  
## <a name="remarks"></a>Notes  
 `firstprivate`s’applique aux directives suivantes :  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [single](../../../parallel/openmp/reference/single.md)  
  
 Pour plus d’informations, consultez [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md).  
  
## <a name="example"></a>Exemple  
 Pour obtenir un exemple d’utilisation de `firstprivate`, consultez l’exemple de [privé](../../../parallel/openmp/reference/private-openmp.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)