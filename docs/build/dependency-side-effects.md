---
title: "Effets secondaires des dépendances | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dependencies, side effects
- NMAKE program, dependents
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9d19426a34620cfdd14b426b94757715ca2d1cbd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="dependency-side-effects"></a>Effets secondaires des dépendances
Si une cible est spécifiée par un signe deux-points ( :) sur deux lignes de dépendance dans différents emplacements, et si les commandes apparaissent uniquement après l’une des lignes, NMAKE interprète les dépendances, comme si adjacentes ou combinées. Il n’appelle pas une règle d’inférence pour la dépendance qui n’a aucune commande, mais suppose que les dépendances appartiennent à un bloc d’une description et exécute les commandes spécifiées avec l’autre dépendance. Par exemple, cet ensemble de règles :  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
```  
  
 est évalué comme ceci :  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 Cela ne se produit pas si un double deux-points (`::`) est utilisé. Par exemple, cet ensemble de règles :  
  
```Output  
bounce.exe :: jump.obj  
   echo Building bounce.exe...  
  
bounce.exe :: up.obj  
```  
  
 est évalué comme ceci :  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
# invokes an inference rule  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Targets (Cibles MSBuild)](../build/targets.md)