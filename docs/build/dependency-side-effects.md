---
title: "Effets secondaires des d&#233;pendances | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dépendances, effets secondaires"
  - "Programme NMAKE, dépendants"
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Effets secondaires des d&#233;pendances
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si une cible est spécifiée par un signe deux-points ( :) en deux lignes de dépendance dans différents emplacements, et si les commandes apparaissent après seulement l’une des lignes, NMAKE interprète les dépendances comme si adjacentes ou combinées. Il n’appelle pas une règle d’inférence pour la dépendance qui n’a aucune commande, mais suppose que les dépendances appartiennent au bloc d’une description et exécute les commandes spécifiées avec l’autre dépendance. Par exemple, ce groupe de règles :  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
```  
  
 est évaluée comme ceci :  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 Cela ne se produit pas si un double deux-points (`::`) est utilisé. Par exemple, ce groupe de règles :  
  
```Output  
bounce.exe :: jump.obj  
   echo Building bounce.exe...  
  
bounce.exe :: up.obj  
```  
  
 est évaluée comme ceci :  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
# invokes an inference rule  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Cibles](../build/targets.md)