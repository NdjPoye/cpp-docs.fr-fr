---
title: "Using IDispEventImpl | Microsoft Docs"
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
  - "IDispEventImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventImpl class, using"
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Using IDispEventImpl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lors de l'utilisation `IDispEventImpl` pour gérer des événements, vous aurez besoin :  
  
-   Dérivez votre classe d' [IDispEventImpl](../atl/reference/idispeventimpl-class.md).  
  
-   Ajoutez [table de récepteurs d'événements](../Topic/BEGIN_SINK_MAP.md) à votre classe.  
  
-   Ajouter des entrées à la table de récepteurs d'événements à l'aide de la macro de [SINK\_ENTRY](../Topic/SINK_ENTRY.md) ou de [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY_EX.md) .  
  
-   Implémentez les méthodes que vous êtes intéressé par la gestion.  
  
-   Avertit et unadvise la source d'événement.  
  
## Exemple  
 L'exemple suivant montre comment gérer l'événement de **DocumentChange** l'a déclenché par l'objet Application Word.  Cet événement est définie comme une méthode sur la dispinterface d' **ApplicationEvents** .  
  
 l'exemple est d' [Exemple ATLEventHandling](../top/visual-cpp-samples.md).  
  
 `[`  
  
 `uuid(000209F7-0000-0000-C000-000000000046),`  
  
 `hidden`  
  
 `]`  
  
 `dispinterface ApplicationEvents {`  
  
 `properties:`  
  
 `methods:`  
  
 `[id(0x00000001), restricted, hidden]`  
  
 `void Startup();`  
  
 `[id(0x00000002)]`  
  
 `void Quit();`  
  
 `[id(0x00000003)]`  
  
 `void DocumentChange();`  
  
 `};`  
  
 L'exemple utilise `#import` générer les fichiers d'en\-tête requis de la bibliothèque de types Word.  Si vous souhaitez utiliser cet exemple avec d'autres versions de Word, vous devez spécifier le fichier DLL correct de mso.  Par exemple, fournit mso9.dll Office 2000 et Office XP fournit mso.dll.  Ce code est simplifié stdafx.h :  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/CPP/using-idispeventimpl_1.h)]  
  
 Le code suivant apparaît dans NotSoSimple.h.  Le code approprié est indiqué par les commentaires :  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/CPP/using-idispeventimpl_2.h)]  
  
## Voir aussi  
 [Gestion des événements](../atl/event-handling-and-atl.md)   
 [Exemple ATLEventHandling](../top/visual-cpp-samples.md)