---
title: "Using IDispEventSimpleImpl | Microsoft Docs"
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
  - "IDispEventSimpleImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventSimpleImpl class, using"
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Using IDispEventSimpleImpl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lors de l'utilisation `IDispEventSimpleImpl` pour gérer des événements, vous aurez besoin :  
  
-   Dérivez votre classe d' [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md).  
  
-   Ajoutez [table de récepteurs d'événements](../Topic/BEGIN_SINK_MAP.md) à votre classe.  
  
-   Définissez les structures de [\_ATL\_FUNC\_INFORMATION](../atl/reference/atl-func-info-structure.md) décrivant les événements.  
  
-   Ajouter des entrées à la table de récepteurs d'événements à l'aide de la macro de [SINK\_ENTRY\_INFORMATION](../Topic/SINK_ENTRY_INFO.md) .  
  
-   Implémentez les méthodes que vous êtes intéressé par la gestion.  
  
-   Avertit et unadvise la source d'événement.  
  
## Exemple  
 L'exemple suivant vous montre comment gérer l'événement de **DocumentChange** avez déclenché par l'objet Application Word.  Cet événement est définie comme une méthode sur la dispinterface d' **ApplicationEvents** .  
  
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
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/CPP/using-idispeventsimpleimpl_1.h)]  
  
 Les seules informations de la bibliothèque de types réellement utilisée dans cet exemple sont le CLSID de l'objet Application Word et de l'IID de l'interface d' **ApplicationEvents** .  Ces informations sont uniquement utilisées au moment de la compilation.  
  
 Le code suivant apparaît dans Simple.h.  Le code approprié est indiqué par les commentaires :  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#3](../atl/codesnippet/CPP/using-idispeventsimpleimpl_2.h)]  
  
 Le code suivant est de Simple.cpp :  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#4](../atl/codesnippet/CPP/using-idispeventsimpleimpl_3.cpp)]  
  
## Voir aussi  
 [Gestion des événements](../atl/event-handling-and-atl.md)   
 [Exemple ATLEventHandling](../top/visual-cpp-samples.md)