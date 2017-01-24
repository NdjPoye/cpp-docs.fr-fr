---
title: "Windows Support Classes | Microsoft Docs"
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
  - "vc.atl.windows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, fenêtres"
  - "windows [C++], ATL"
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Support Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes suivantes fournissent la prise en charge des fenêtres :  
  
-   [\_U\_MENUorID](../atl/reference/u-menuorid-class.md) Fournit des wrappers pour **CreateWindow** et **CreateWindowEx**.  
  
-   [CWindow](../atl/reference/cwindow-class.md) contient des méthodes pour manipuler une fenêtre.  `CWindow` est la classe de base pour `CWindowImpl`, `CDialogImpl` et `CContainedWindow`.  
  
-   [CWindowImpl](../atl/reference/cwindowimpl-class.md) implémente une fenêtre selon une nouvelle classe de fenêtre.  Vous pouvez également sous\-classer ou à la surclassement de la fenêtre.  
  
-   [CDialogImpl](../atl/reference/cdialogimpl-class.md) implémente une boîte de dialogue.  
  
-   [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) implémente une boîte de dialogue \(modale ou non modale\) que des contrôles ActiveX d'hôtes.  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md) implémente une boîte de dialogue \(modale ou non modale\) avec la fonctionnalité de base.  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) manipule une fenêtre qui héberge un contrôle ActiveX.  
  
-   [CAxWindow2T](../atl/reference/caxwindow2t-class.md) fournit des méthodes pour manipuler une fenêtre qui héberge un contrôle ActiveX et a également une prise en charge de l'hébergement des contrôles ActiveX autorisés.  
  
-   [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) implémente une fenêtre contenue dans un autre objet.  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) gère les informations d'une nouvelle classe de fenêtre.  
  
-   Chaînage dynamique prend en charge de[CDynamicChain](../atl/reference/cdynamicchain-class.md) des tables des messages.  
  
-   [CMessageMap](../atl/reference/cmessagemap-class.md) permet à un objet d'exposer ses tables des messages à d'autres objets.  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md) fournit une méthode simple de standardiser les caractéristiques d'un objet window ATL.  
  
-   [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) fournit des valeurs par défaut des styles de fenêtre et des styles étendus utilisés pour créer une fenêtre.  Ces valeurs sont ajoutées, à l'aide de l'opérateur OR logique, les valeurs fournies lors de la création d'une fenêtre.  
  
## Articles connexes  
 [Classes de fenêtres ATL](../atl/atl-window-classes.md)  
  
 [Didacticiel ATL](../atl/active-template-library-atl-tutorial.md)  
  
## Voir aussi  
 [Class Overview](../atl/atl-class-overview.md)   
 [Message Map Macros](../atl/reference/message-map-macros-atl.md)   
 [Window Class Macros](../atl/reference/window-class-macros.md)