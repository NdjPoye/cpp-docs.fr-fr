---
title: OMP_DYNAMIC | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OMP_DYNAMIC
dev_langs: C++
helpviewer_keywords: OMP_DYNAMIC OpenMP environment variable
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 900f3e4ddd0e9901e72ed65f12bc036d87a6956e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ompdynamic"></a>OMP_DYNAMIC
Spécifie si la durée d’exécution de OpenMP peut ajuster le nombre de threads dans une région parallèle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
set OMP_DYNAMIC[=TRUE | =FALSE]  
```  
  
## <a name="remarks"></a>Notes  
 Le `OMP_DYNAMIC` variable d’environnement peut être remplacée par la [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) (fonction).  
  
 La valeur par défaut dans l’implémentation Visual C++ de la norme OpenMP est `OMP_DYNAMIC=FALSE`.  
  
 Pour plus d’informations, consultez [OMP_DYNAMIC 4.3](../../../parallel/openmp/4-3-omp-dynamic.md).  
  
## <a name="example"></a>Exemple  
 La commande suivante définit le `OMP_DYNAMIC` variable d’environnement pour la valeur TRUE :  
  
```  
set OMP_DYNAMIC=TRUE  
```  
  
 La commande suivante affiche le paramètre actuel de la `OMP_DYNAMIC` variable d’environnement :  
  
```  
set OMP_DYNAMIC  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Variables d’environnement](../../../parallel/openmp/reference/openmp-environment-variables.md)