---
title: "2.8 Directive Binding | Microsoft Docs"
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
ms.assetid: 7bdac45e-ab55-42f0-bd47-a2e3d5bbab3e
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.8 Directive Binding
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La liaison dynamique des directives doit respecter les règles suivantes :  
  
-   **pour**, **sections**, **unique**, **page maître**, et lier des directives de **cloisonnement** à **parallèle**dynamiquement englobant, le cas échéant, quelle que soit la valeur d'une clause d' **if** qui peut être présente sur cette directive.  Si aucune zone parallèle actuellement n'est exécutée, les directives sont exécutées par une équipe composée de thread principal uniquement.  
  
-   Les liaisons de directive de **dimensionné** à **pour**dynamiquement englobant.  
  
-   La directive d' **atomique** applique l'accès exclusif par rapport à les directives d' **atomique** dans tous les threads, et pas seulement l'équipe actuelle.  
  
-   La directive de **critique** applique l'accès exclusif par rapport à les directives de **critique** dans tous les threads, et pas seulement l'équipe actuelle.  
  
-   Une directive ne peut jamais la lier à toute directive en dehors de **parallèle**dynamiquement englobant le plus proche.