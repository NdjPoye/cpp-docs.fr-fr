---
title: "What Is the ATL Control-Hosting API? | Microsoft Docs"
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
  - "API (C++), héberger"
  - "control-hosting API"
  - "controls [ATL], API d'hébergement"
ms.assetid: 75b27e45-cfba-4950-aa35-96cc7d8da753
caps.latest.revision: 15
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# What Is the ATL Control-Hosting API?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'API d'hébergement du contrôle ATL est l'ensemble de fonctions qui permet à n'importe quelle fenêtre pour agir comme un conteneur de contrôles ActiveX.  Ces fonctions peuvent incorporer statiquement ou dynamiquement dans votre projet étant donné qu'ils sont disponibles en tant que code source et exposé par ATL90.dll.  Les fonctions de contrôle hébergement sont répertoriées dans le tableau ci\-dessous.  
  
|Fonction|Description|  
|--------------|-----------------|  
|[AtlAxAttachControl](../Topic/AtlAxAttachControl.md)|Crée un objet hôte, le connecte à la fenêtre fournie, puis lie un contrôle existant.|  
|[AtlAxCreateControl](../Topic/AtlAxCreateControl.md)|Crée un objet hôte, le connecte à la fenêtre fournie, puis charge un contrôle.|  
|[AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md)|Crée un contrôle ActiveX autorisé, l'initialise, et le héberge dans la fenêtre spécifiée, semblable à [AtlAxCreateControl](../Topic/AtlAxCreateControl.md).|  
|[AtlAxCreateControlEx](../Topic/AtlAxCreateControlEx.md)|Crée un objet hôte, le connecte à la fenêtre fournie, puis charge un contrôle \(permet également des récepteurs d'événements à installer\).|  
|[AtlAxCreateControlLicEx](../Topic/AtlAxCreateControlLicEx.md)|Crée un contrôle ActiveX autorisé, l'initialise, et le héberge dans la fenêtre spécifiée, semblable à [AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md).|  
|[AtlAxCreateDialog](../Topic/AtlAxCreateDialog.md)|Crée une boîte de dialogue non modale d'une ressource de boîte de dialogue et retourne le handle de fenêtre.|  
|[AtlAxDialogBox](../Topic/AtlAxDialogBox.md)|Crée une boîte de dialogue modale d'une ressource de boîte de dialogue.|  
|[AtlAxGetControl](../Topic/AtlAxGetControl.md)|Retourne le pointeur d'interface de **IUnknown** du contrôle hébergé dans une fenêtre.|  
|[AtlAxGetHost](../Topic/AtlAxGetHost.md)|Retourne le pointeur d'interface de **IUnknown** de l'objet hôte connecté à une fenêtre.|  
|[AtlAxWinInit](../Topic/AtlAxWinInit.md)|Initialise le code de contrôle hébergement.|  
|[AtlAxWinTerm](../Topic/AtlAxWinTerm.md)|Uninitializes le code de contrôle hébergement.|  
  
 Les paramètres d' `HWND` dans les trois premières fonctions doivent être une fenêtre existante \(presque\) de tout type.  Si vous appelez l'une de ces trois fonctions de manière explicite \(en général, vous devez pas\), ne passez pas un handle vers une fenêtre qui agit comme déjà hôte \(dans ce cas, l'objet hôte existant ne sera pas libéré\).  
  
 Appel de sept le premier fonctions [AtlAxWinInit](../Topic/AtlAxWinInit.md) implicitement.  
  
> [!NOTE]
>  L'API de contrôle hébergement forme la base de la prise en charge ATL de la relation contenant\-contenu de contrôle ActiveX.  Toutefois, il y a généralement peu de besoin d'appeler ces fonctions directement si vous tirez parti ou utiliser pleinement les classes wrapper ATL.  Pour plus d'informations, consultez [Classe ATL qui facilitent la relation contenant\-contenu de contrôle ActiveX ?](../atl/which-atl-classes-facilitate-activex-control-containment-q.md).  
  
## Voir aussi  
 [FAQ sur la relation contenant\-contenu des contrôles](../atl/atl-control-containment-faq.md)