---
title: "Composite Control Global Functions | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles composites, fonctions globales"
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
caps.latest.revision: 20
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Composite Control Global Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ces fonctions fournissent la prise en charge pour créer des boîtes de dialogue, et de créer, d'héberger et d'autoriser des contrôles ActiveX.  
  
> [!IMPORTANT]
>  Les fonctions répertoriées dans le tableau suivant ne peuvent pas être utilisées dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlAxDialogBox](../Topic/AtlAxDialogBox.md)|Crée une boîte de dialogue modale d'un modèle de boîte de dialogue fourni par l'utilisateur.  La boîte de dialogue peut contenir des contrôles ActiveX.|  
|[AtlAxCreateDialog](../Topic/AtlAxCreateDialog.md)|Crée une boîte de dialogue non modale d'un modèle de boîte de dialogue fourni par l'utilisateur.  La boîte de dialogue peut contenir des contrôles ActiveX.|  
|[AtlAxCreateControl](../Topic/AtlAxCreateControl.md)|Crée un contrôle ActiveX, l'initialise, et le héberge dans la fenêtre spécifiée.|  
|[AtlAxCreateControlEx](../Topic/AtlAxCreateControlEx.md)|Crée un contrôle ActiveX, l'initialise, le héberge dans la fenêtre spécifiée, et extrait un pointeur d'interface \(ou des pointeurs\) du contrôle.|  
|[AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md)|Crée un contrôle ActiveX autorisé, l'initialise, et le héberge dans la fenêtre spécifiée.|  
|[AtlAxCreateControlLicEx](../Topic/AtlAxCreateControlLicEx.md)|Crée un contrôle ActiveX autorisé, l'initialise, le héberge dans la fenêtre spécifiée, et extrait un pointeur d'interface \(ou des pointeurs\) du contrôle.|  
|[AtlAxAttachControl](../Topic/AtlAxAttachControl.md)|Joint un contrôle précédemment créé dans la fenêtre spécifiée.|  
|[AtlAxGetHost](../Topic/AtlAxGetHost.md)|Utilisé pour obtenir un pointeur d'interface direct au conteneur pour une fenêtre spécifiée \(le cas échéant\), avec son handle.|  
|[AtlAxGetControl](../Topic/AtlAxGetControl.md)|Utilisé pour obtenir un pointeur d'interface direct à l'intérieur de contenu par contrôle une fenêtre spécifiée \(le cas échéant\), donnée son handle.|  
|[AtlSetChildSite](../Topic/AtlSetChildSite.md)|Initialise **IUnknown** du site enfant.|  
|[AtlAxWinInit](../Topic/AtlAxWinInit.md)|Initialise le code d'hébergement pour les objets d'AxWin.|  
|[AtlAxWinTerm](../Topic/AtlAxWinTerm.md)|Uninitializes code d'hébergement pour les objets d'AxWin.|  
|[AtlGetObjectSourceInterface](../Topic/AtlGetObjectSourceInterface.md)|Retourne des informations sur l'interface source par défaut d'un objet.|  
  
## Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)   
 [Composite Control Macros](../../atl/reference/composite-control-macros.md)