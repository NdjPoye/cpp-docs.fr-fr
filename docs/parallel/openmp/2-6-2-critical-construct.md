---
title: "2.6.2 critical Construct | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.2 critical Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La directive de **critique** identifie un élément qui restreint l'exécution du bloc structuré associé à un seul thread à la fois.  La syntaxe de la directive de **critique** est la suivante :  
  
```  
#pragma omp critical [(name)]  new-line  
   structured-block  
```  
  
 *Une étiquette* facultative peut être utilisé pour identifier la zone critique.  Les identificateurs utilisés pour identifier une région critique ont une liaison externe et sont dans un espace de noms distinct des espaces de noms utilisés par les noms, des balises, des membres, et les identificateurs ordinaires.  
  
 un thread attend au début d'une région critique jusqu'à ce qu'aucun autre thread n'exécute une région critique \(n'importe où dans le programme\) avec le même nom.  Tous les mappages sans nom de directives de **critique** le même nom non spécifié.