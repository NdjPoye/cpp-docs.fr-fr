---
title: "Debugging and Error Reporting Macros | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "macros, rapport d'erreurs"
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Debugging and Error Reporting Macros
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ces macros permettent le débogage utiles et suivent des fonctionnalités.  
  
|||  
|-|-|  
|[\_ATL\_DEBUG\_INTERFACES](../Topic/_ATL_DEBUG_INTERFACES.md)|Écrit, dans la fenêtre Sortie, toutes les fuites de l'interface qui sont détectées lors `_Module.Term` est appelé.|  
|[\_ATL\_DEBUG\_QI](../Topic/_ATL_DEBUG_QI.md)|Écrit tous les appels à `QueryInterface` dans la fenêtre Sortie.|  
|[ATLASSERT](../Topic/ATLASSERT.md)|Exécute les mêmes fonctionnalités que la macro de [\_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) recherchée dans la bibliothèque Runtime C.|  
|[ATLENSURE](../Topic/ATLENSURE.md)|Exécute la validation de paramètres.  Appel `AtlThrow` si nécessaire|  
|[ATLTRACENOTIMPL](../Topic/ATLTRACENOTIMPL.md)|Envoie un message à l'unité de vidage que la fonction spécifiée n'est pas implémenté.|  
|[ATLTRACE](../Topic/ATLTRACE%20\(ATL\).md)|Stocke des avertissements à un périphérique de sortie, telles que la fenêtre du débogueur, en fonction de les balises et les niveaux indiqués.  Inclus pour la compatibilité descendante.|  
|[ATLTRACE2](../Topic/ATLTRACE2.md)|Stocke des avertissements à un périphérique de sortie, telles que la fenêtre du débogueur, en fonction de les balises et les niveaux indiqués.|  
  
## Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)   
 [Debugging and Error Reporting Global Functions](../../atl/reference/debugging-and-error-reporting-global-functions.md)