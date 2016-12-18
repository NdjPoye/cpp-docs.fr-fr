---
title: "Styles de fen&#234;tre | Microsoft Docs"
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
  - "WS_MINIMIZEBOX"
  - "WS_SIZEBOX"
  - "WS_CLIPCHILDREN"
  - "WS_TILED"
  - "WS_GROUP"
  - "WS_VSCROLL"
  - "WS_CHILD"
  - "WS_TABSTOP"
  - "WS_HSCROLL"
  - "WS_THICKFRAME"
  - "WS_DISABLED"
  - "WS_POPUP"
  - "WS_ICONIC"
  - "WS_MAXIMIZE"
  - "WS_VISIBLE"
  - "WS_POPUPWINDOW"
  - "WS_TILEDWINDOW"
  - "WS_DLGFRAME"
  - "WS_MINIMIZE"
  - "WS_CAPTION"
  - "WS_OVERLAPPED"
  - "WS_BORDER"
  - "WS_MAXIMIZEBOX"
  - "WS_OVERLAPPEDWINDOW"
  - "WS_SYSMENU"
  - "WS_CHILDWINDOW"
  - "WS_CLIPSIBLINGS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "styles, fenêtres"
  - "styles de fenêtres"
  - "styles de fenêtres, dans MFC"
  - "WS_BORDER (constante)"
  - "WS_CAPTION (constante)"
  - "WS_CHILD (constante)"
  - "WS_CHILDWINDOW (constante)"
  - "WS_CLIPCHILDREN (constante)"
  - "WS_CLIPSIBLINGS (constante)"
  - "WS_DISABLED (constante)"
  - "WS_DLGFRAME (constante)"
  - "WS_GROUP (constante)"
  - "WS_HSCROLL (constante)"
  - "WS_ICONIC (constante)"
  - "WS_MAXIMIZE (constante)"
  - "WS_MAXIMIZEBOX (constante)"
  - "WS_MINIMIZE (constante)"
  - "WS_MINIMIZEBOX (constante)"
  - "WS_OVERLAPPED (constante)"
  - "WS_OVERLAPPEDWINDOW (constante)"
  - "WS_POPUP (constante)"
  - "WS_POPUPWINDOW (constante)"
  - "WS_SIZEBOX (constante)"
  - "WS_SYSMENU (constante)"
  - "WS_TABSTOP (constante)"
  - "WS_THICKFRAME (constante)"
  - "WS_TILED (constante)"
  - "WS_TILEDWINDOW (constante)"
  - "WS_VISIBLE (constante)"
  - "WS_VSCROLL (constante)"
ms.assetid: c85ffbe4-f4ff-4227-917a-48ec4a411842
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Styles de fen&#234;tre
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   `WS_BORDER` Crée une fenêtre possédant une bordure.  
  
-   **WS\_CAPTION** Crée une fenêtre qui a une barre de titre \(implique le style `WS_BORDER` \).  Ne peut pas être utilisé avec le style **WS\_DLGFRAME**.  
  
-   **WS\_CHILD** Crée une fenêtre enfant.  Ne peut pas être utilisé avec le style `WS_POPUP`.  
  
-   **WS\_CHILDWINDOW** Identique au style **WS\_CHILD**.  
  
-   **WS\_CLIPCHILDREN** Exclut la zone occupée par les fenêtres enfants lorsque vous dessinez dans la fenêtre parente.  Utilisée lorsque vous créez la fenêtre parente.  
  
-   **WS\_CLIPSIBLINGS** Coupe les fenêtres enfants les unes par rapport aux autres ; autrement dit, quand une fenêtre enfant particulière reçoit un message de peinture, le style **WS\_CLIPSIBLINGS** découpe toutes les autres fenêtres enfants superposées hors de la zone de la fenêtre enfant à mettre à jour. \(Si **WS\_CLIPSIBLINGS** n'est pas donné et que les fenêtres enfants se chevauchent, lorsque vous dessinez dans la zone cliente d'une fenêtre enfant, il est possible de dessiner dans la zone cliente d'une fenêtre enfant voisine.\) À utiliser avec le style **WS\_CHILD** uniquement.  
  
-   **WS\_DISABLED** Crée une fenêtre qui est initialement désactivée.  
  
-   **WS\_DLGFRAME** Crée une fenêtre avec une double bordure, mais sans titre.  
  
-   **WS\_GROUP** Spécifie le premier contrôle d'un groupe de contrôles dans lequel l'utilisateur peut se déplacer d'un contrôle à l'autre avec les touches de direction.  Tous les contrôles définis avec le style **WS\_GROUP FALSE** après le premier contrôle appartiennent au même groupe.  Le prochain contrôle avec le style **WS\_GROUP** démarre le prochain groupe \(en d'autres termes, un groupe se termine là où commence le suivant\).  
  
-   **WS\_HSCROLL** Crée une fenêtre avec une barre de défilement horizontal.  
  
-   **WS\_ICONIC** Crée une fenêtre qui est initialement réduite.  Identique au style **WS\_MINIMIZE**.  
  
-   **WS\_MAXIMIZE** Crée une fenêtre de taille maximale.  
  
-   **WS\_MAXIMIZEBOX** Crée une fenêtre avec un bouton d'agrandissement.  
  
-   **WS\_MINIMIZE** Crée une fenêtre qui est initialement réduite.  À utiliser avec le style **WS\_OVERLAPPED** uniquement.  
  
-   **WS\_MINIMIZEBOX** Crée une fenêtre avec un bouton de réduction.  
  
-   **WS\_OVERLAPPED** Crée une fenêtre superposée.  Une fenêtre avec chevauchement a habituellement une légende et une bordure.  
  
-   **WS\_OVERLAPPEDWINDOW** Crée une fenêtre superposée avec les styles **WS\_OVERLAPPED**, **WS\_CAPTION**, **WS\_SYSMENU**, **WS\_THICKFRAME**, **WS\_MINIMIZEBOX** et **WS\_MAXIMIZEBOX**.  
  
-   `WS_POPUP` Crée une fenêtre contextuelle.  Ne peut pas être utilisé avec le style **WS\_CHILD**.  
  
-   **WS\_POPUPWINDOW** Crée une fenêtre indépendante avec les styles `WS_BORDER`, `WS_POPUP` et **WS\_SYSMENU**.  Le style **WS\_CAPTION** doit être associé au style **WS\_POPUPWINDOW** pour rendre le menu système visible.  
  
-   **WS\_SIZEBOX** Crée une fenêtre possédant une bordure de redimensionnement.  Identique au style **WS\_THICKFRAME**.  
  
-   **WS\_SYSMENU** Crée une fenêtre dotée d'une case de menu Système dans la barre de titre.  Utilisé uniquement pour les fenêtres avec des barres de titre.  
  
-   **WS\_TABSTOP** spécifie un des nombreux contrôles à travers lesquels l'utilisateur peut se déplacer à l'aide de la touche TAB.  La touche TAB déplace l'utilisateur au contrôle suivant spécifié par le style **WS\_TABSTOP**.  
  
-   **WS\_THICKFRAME** Crée une fenêtre dotée d'un frame épais permettant de la dimensionner.  
  
-   **WS\_TILED** Crée une fenêtre superposée.  Une fenêtre avec chevauchement a une barre de titre et une bordure.  Identique au style **WS\_OVERLAPPED** .  
  
-   **WS\_TILEDWINDOW** Crée une fenêtre superposée avec les styles **WS\_OVERLAPPED**, **WS\_CAPTION**, **WS\_SYSMENU**, **WS\_THICKFRAME**, **WS\_MINIMIZEBOX** et **WS\_MAXIMIZEBOX**.  Identique au style **WS\_OVERLAPPEDWINDOW**.  
  
-   **WS\_VISIBLE** Crée une fenêtre initialement visible.  
  
-   **WS\_VSCROLL** Crée une fenêtre avec une barre de défilement vertical.  
  
## Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CWnd::Create](../Topic/CWnd::Create.md)   
 [CWnd::CreateEx](../Topic/CWnd::CreateEx.md)   
 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)