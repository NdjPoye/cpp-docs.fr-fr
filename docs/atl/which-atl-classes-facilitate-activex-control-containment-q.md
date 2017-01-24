---
title: "Which ATL Classes Facilitate ActiveX Control Containment? | Microsoft Docs"
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
  - "conteneurs de contrôles ActiveX (C++), ATL control hosting"
  - "hosting controls using ATL"
ms.assetid: 803a4605-7f4c-4139-8638-49d8783d31b0
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Which ATL Classes Facilitate ActiveX Control Containment?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le code du contrôle hébergement ATL ne requiert pas de vous de n'utiliser aucune classe ATL ; vous pouvez simplement créer une fenêtre de **"AtlAxWin80"** et utiliser l'API de contrôle hébergement si nécessaire \(pour plus d'informations, consultez [Quel est l'API d'Hébergement contrôle ATL ?](../atl/what-is-the-atl-control-hosting-api-q.md)\).  Toutefois, les classes suivantes facilitent les fonctionnalités de relation contenant\-contenu pour utiliser.  
  
|Classe|Description|  
|------------|-----------------|  
|[CAxWindow](../atl/reference/caxwindow-class.md)|Encapsule une fenêtre de **"AtlAxWin80"** , en fournissant des méthodes pour créer la fenêtre, créer un contrôle et\/ou lier un contrôle à la fenêtre, et récupérer des pointeurs d'interface sur l'objet hôte.|  
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|Encapsule une fenêtre de **"AtlAxWinLic80"** , en fournissant des méthodes pour créer la fenêtre, créer un contrôle et\/ou liaison d'un contrôle sous licence dans la fenêtre, et récupérer des pointeurs d'interface sur l'objet hôte.|  
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|Sert de classe de base pour les classes de contrôle ActiveX sur une ressource de boîte de dialogue.  De ces contrôles peuvent contenir d'autres contrôles ActiveX.|  
|[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)|Sert de classe de base pour les classes de boîte de dialogue en fonction d'une ressource de boîte de dialogue.  De ces boîtes peuvent contenir des contrôles ActiveX.|  
|[CWindow](../atl/reference/cwindow-class.md)|Fournit une méthode, [GetDlgControl](../Topic/CWindow::GetDlgControl.md), qui retourne un pointeur d'interface d'un contrôle, vu l'ID de sa fenêtre hôte.  En outre, les wrappers d'API Windows exposés par `CWindow` permettent généralement la gestion des fenêtres.|  
  
## Voir aussi  
 [FAQ sur la relation contenant\-contenu des contrôles](../atl/atl-control-containment-faq.md)