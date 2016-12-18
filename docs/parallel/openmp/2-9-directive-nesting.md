---
title: "2.9 Directive Nesting | Microsoft Docs"
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
ms.assetid: 6565a43c-fd2d-4366-8322-8d75e1b06600
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.9 Directive Nesting
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'imbrication dynamique des directives doit respecter les règles suivantes :  
  
-   Une directive de **parallèle** dynamiquement à l'intérieur d'un autre **parallèle** génère logiquement une nouvelle équipe, composée du thread actuel uniquement, à moins que le parallélisme imbriqué est activé.  
  
-   n'est pas autorisé à**pour**, **sections**, les directives et d' **unique** qui les lient à même **parallèle** pour être imbriqué à l'intérieur de l'un de l'autre.  
  
-   il ne permet pas aux directives de**critique** avec le même nom à être imbriqué à l'intérieur de l'un de l'autre.  Notez que cette restriction n'est pas suffisant pour empêcher l'interblocage.  
  
-   **pour**, **sections**, les directives et d' **unique** ne sont pas autorisés dans l'étendue dynamique de **critique**, de **dimensionné**, et des zones de **page maître** si les directives les lient à même **parallèle** que les régions.  
  
-   les directives de**cloisonnement** ne sont pas autorisées dans l'étendue dynamique de **pour**, de **dimensionné**, de **sections**, d' **unique**, de **page maître**, et des zones de **critique** si les directives les lient à même **parallèle** que les régions.  
  
-   les directives de**page maître** ne sont pas autorisées dans l'étendue dynamique de **pour**, de **sections**, les directives et d' **unique** si les directives de **page maître** les lient à même **parallèle** que les directives de partage du travail.  
  
-   vous ne pouvez pas utiliser de directives de**dimensionné** dans l'étendue dynamique des zones de **critique** si les directives les lient à même **parallèle** que les régions.  
  
-   Toute directive qui est autorisée lorsque dynamiquement exécuté dans une région parallèle est également autorisée lorsque extérieur exécuté une région parallèle.  Une fois exécutée dynamiquement à l'extérieur d'une région parallèle spécifiée par l'utilisateur, la directive est exécutée par l'équipe composée de thread principal uniquement.