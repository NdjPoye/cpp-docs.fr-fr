---
title: "Chemins de recherche des dépendants | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6093db4ac8e0c88dfe6e4b5a5463e5ee8d24349
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="search-paths-for-dependents"></a>Chemins de recherche des dépendants
À chaque dépendant correspond un chemin de recherche facultatif, spécifié comme suit :  
  
## <a name="syntax"></a>Syntaxe  
  
```  
{directory[;directory...]}dependent  
```  
  
## <a name="remarks"></a>Notes  
 NMAKE recherche d’un dépendant dans le répertoire en cours, puis dans les répertoires dans l’ordre spécifié. Une macro peut spécifier tout ou partie d’un chemin de recherche. Placez les noms de répertoires entre accolades ({}) ; Séparez les répertoires multiples par un point-virgule ( ;). Aucun des espaces ou des onglets ne sont autorisées.  
  
## <a name="see-also"></a>Voir aussi  
 [Dépendants](../build/dependents.md)