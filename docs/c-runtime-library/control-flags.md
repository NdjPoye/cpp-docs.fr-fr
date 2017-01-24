---
title: "Indicateurs de contr&#244;le | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.flags"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tas de débogage, indicateurs de contrôle"
  - "indicateurs, contrôle"
  - "allocation des tas, indicateurs de contrôle"
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Indicateurs de contr&#244;le
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La version de débogage de la bibliothèque Runtime de Microsoft C utilise les indicateurs suivants pour contrôler le processus d'allocation de tas et de rapports.  Pour plus d'informations, consultez [CRT Debugging Techniques](../Topic/CRT%20Debugging%20Techniques.md).  
  
|Indicateur|Description|  
|----------------|-----------------|  
|[\_CRTDBG\_MAP\_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|Mappe les fonctions de tas de base en leurs équivalents de la version de débogage|  
|[\_DEBUG](../c-runtime-library/debug.md)|Permet d'utiliser les versions de débogage des fonctions d'exécution|  
|[\_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|Contrôle la manière dont le gestionnaire de tas de débogage suit les allocations|  
  
 Ces indicateurs peuvent être définis avec une option de ligne de commande a\/D ou avec une directive `#define`.  Lorsque l'indicateur est défini avec `#define`, la directive doit figurer avant que le fichier d'en\-tête n'incluse l'instruction pour les déclarations de routine.  
  
## Voir aussi  
 [Variables globales et types standard](../c-runtime-library/global-variables-and-standard-types.md)