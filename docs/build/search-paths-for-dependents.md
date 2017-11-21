---
title: "Chemins de recherche des dépendants | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cf777c89c78ab844b61138c30a5a9a25ca6b91d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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