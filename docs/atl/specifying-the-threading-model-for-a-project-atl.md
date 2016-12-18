---
title: "Sp&#233;cification du mod&#232;le de thread pour un projet (ATL) | Microsoft Docs"
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
helpviewer_keywords: 
  - "_ATL_APARTMENT_THREADED macro"
  - "_ATL_FREE_THREADED macro"
  - "_ATL_SINGLE_THREADED macro"
  - "ATL, multithreading"
  - "threads (ATL), modèles"
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sp&#233;cification du mod&#232;le de thread pour un projet (ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les macros suivantes sont disponibles pour spécifier le modèle de thread d'un projet ATL :  
  
|Macro|Directives pour l'utilisation|  
|-----------|-----------------------------------|  
|\_ATL\_SINGLE\_THREADED|Définissez si tous les objets utilisent le modèle monothread.|  
|\_ATL\_APARTMENT\_THREADED|Définissez si un ou plusieurs de vos objets utilisent le thread cloisonné \(STA\).|  
|\_ATL\_FREE\_THREADED|Définissez si un ou plusieurs de votre utilisation d'objets ou libre de threads neutre.  Le code existant peut contenir des références à un [\_ATL\_MULTI\_THREADED](../Topic/_ATL_MULTI_THREADED.md)équivalent.|  
  
 Si vous ne définissez pas l'un de ces macros pour votre projet, le \_ATL\_FREE\_THREADED sera appliquée.  
  
 Les macros affectent les performances d'exécution comme suit :  
  
-   Spécifier la macro qui correspond aux objets dans votre projet peut améliorer les performances d'exécution.  
  
-   Spécifier un niveau supérieur de la macro, par exemple si vous spécifiez le \_ATL\_APARTMENT\_THREADED lorsque tous les objets sont thread unique, dégradera légèrement les performances d'exécution.  
  
-   Spécifier un niveau inférieur de la macro, par exemple, si vous spécifiez le \_ATL\_SINGLE\_THREADED lorsqu'un ou plusieurs de vos objets utilisent le thread cloisonné \(STA\) ou le modèle de thread libre, peut générer votre application d'échouer au moment de l'exécution.  
  
 Consultez l' [Options, l'Assistant Objet simple ATL](../atl/reference/options-atl-simple-object-wizard.md) pour une description des modèles de thread disponibles pour un objet ATL.  
  
## Voir aussi  
 [Concepts](../atl/active-template-library-atl-concepts.md)