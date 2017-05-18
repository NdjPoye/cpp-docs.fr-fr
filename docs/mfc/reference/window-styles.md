---
title: "Styles de fenêtre | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WS_MINIMIZEBOX
- WS_SIZEBOX
- WS_CLIPCHILDREN
- WS_TILED
- WS_GROUP
- WS_VSCROLL
- WS_CHILD
- WS_TABSTOP
- WS_HSCROLL
- WS_THICKFRAME
- WS_DISABLED
- WS_POPUP
- WS_ICONIC
- WS_MAXIMIZE
- WS_VISIBLE
- WS_POPUPWINDOW
- WS_TILEDWINDOW
- WS_DLGFRAME
- WS_MINIMIZE
- WS_CAPTION
- WS_OVERLAPPED
- WS_BORDER
- WS_MAXIMIZEBOX
- WS_OVERLAPPEDWINDOW
- WS_SYSMENU
- WS_CHILDWINDOW
- WS_CLIPSIBLINGS
dev_langs:
- C++
helpviewer_keywords:
- WS_THICKFRAME constant
- WS_TILEDWINDOW constant
- WS_MAXIMIZEBOX constant
- WS_DLGFRAME constant
- WS_CHILDWINDOW constant
- window styles, in MFC
- WS_CHILD constant
- WS_GROUP constant
- WS_MINIMIZE constant
- WS_CAPTION constant
- WS_MAXIMIZE constant
- WS_POPUP constant
- WS_SYSMENU constant
- WS_TILED constant
- window styles
- WS_POPUPWINDOW constant
- WS_CLIPSIBLINGS constant
- WS_BORDER constant
- WS_DISABLED constant
- WS_VSCROLL constant
- WS_OVERLAPPED constant
- WS_MINIMIZEBOX constant
- WS_VISIBLE constant
- WS_OVERLAPPEDWINDOW constant
- WS_TABSTOP constant
- WS_ICONIC constant
- WS_SIZEBOX constant
- WS_HSCROLL constant
- WS_CLIPCHILDREN constant
- styles, windows
ms.assetid: c85ffbe4-f4ff-4227-917a-48ec4a411842
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: d814e3a10132fb3fe88969ce434f8286b02afba5
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="window-styles"></a>Styles de fenêtre
-   `WS_BORDER`Crée une fenêtre qui a une bordure.  
  
-   **WS_CAPTION** crée une fenêtre comportant une barre de titre (implique la `WS_BORDER` style). Ne peut pas être utilisé avec les **WS_DLGFRAME** style.  
  
-   **WS_CHILD** crée une fenêtre enfant. Ne peut pas être utilisé avec les `WS_POPUP` style.  
  
-   **WS_CHILDWINDOW** identique à la **WS_CHILD** style.  
  
-   **WS_CLIPCHILDREN** exclut la zone occupée par les fenêtres enfants lorsque vous dessinez dans la fenêtre parente. Utilisé lors de la création de la fenêtre parente.  
  
-   **WS_CLIPSIBLINGS** fenêtres enfants de Clips par rapport aux autres, c'est-à-dire lorsqu’une fenêtre enfant reçoit un message de peinture, les **WS_CLIPSIBLINGS** style clips windows de tous les autres enfants superposés hors de la région de la fenêtre enfant à mettre à jour. (Si **WS_CLIPSIBLINGS** n’est pas accordée et enfant windows se chevauchent, lorsque vous dessinez dans la zone cliente d’une fenêtre enfant, il est possible de dessiner dans la zone cliente d’une fenêtre enfant voisins.) Pour une utilisation avec le **WS_CHILD** style uniquement.  
  
-   **WS_DISABLED** crée une fenêtre qui est initialement désactivée.  
  
-   **WS_DLGFRAME** crée une fenêtre avec une double bordure mais aucun titre.  
  
-   **WS_GROUP** Spécifie le premier contrôle d’un groupe de contrôles dans lesquels l’utilisateur peut déplacer d’un contrôle à l’autre avec les touches de direction. Tous les contrôles définis avec la **WS_GROUP** style **FALSE** après le premier contrôle appartiennent au même groupe. Le contrôle suivant avec les **WS_GROUP** style démarre le groupe suivant (autrement dit, un groupe se termine où commence la prochaine).  
  
-   **WS_HSCROLL** crée une fenêtre comportant une barre de défilement horizontale.  
  
-   **WS_ICONIC** crée une fenêtre réduite initialement. Identique à la **WS_MINIMIZE** style.  
  
-   **WS_MAXIMIZE** crée une fenêtre de taille maximale.  
  
-   **WS_MAXIMIZEBOX** crée une fenêtre comportant un bouton d’agrandissement.  
  
-   **WS_MINIMIZE** crée une fenêtre réduite initialement. Pour une utilisation avec le **WS_OVERLAPPED** style uniquement.  
  
-   **WS_MINIMIZEBOX** crée une fenêtre comportant un bouton réduire.  
  
-   **WS_OVERLAPPED** crée une fenêtre superposée. Une fenêtre superposée a généralement une légende et une bordure.  
  
-   **WS_OVERLAPPEDWINDOW** crée une fenêtre superposée avec la **WS_OVERLAPPED**, **WS_CAPTION**, **WS_SYSMENU**, **WS_THICKFRAME**, **WS_MINIMIZEBOX**, et **WS_MAXIMIZEBOX** styles.  
  
-   `WS_POPUP`Crée une fenêtre indépendante. Ne peut pas être utilisé avec les **WS_CHILD** style.  
  
-   **WS_POPUPWINDOW** crée une fenêtre contextuelle avec le `WS_BORDER`, `WS_POPUP`, et **WS_SYSMENU** styles. Le **WS_CAPTION** style doit être combiné avec la **WS_POPUPWINDOW** style pour afficher le menu contrôle.  
  
-   **WS_SIZEBOX** crée une fenêtre comportant une bordure de redimensionnement. Identique à la **WS_THICKFRAME** style.  
  
-   **WS_SYSMENU** crée une fenêtre qui possède un menu système dans sa barre de titre. Utilisé uniquement pour windows avec des barres de titre.  
  
-   **WS_TABSTOP** spécifie un nombre quelconque de contrôles par le biais duquel l’utilisateur peut passer à l’aide de la touche TAB. La touche TAB déplace l’utilisateur vers le contrôle suivant est spécifié par le **WS_TABSTOP** style.  
  
-   **WS_THICKFRAME** crée une fenêtre avec une image épaisse qui peut être utilisée pour redimensionner la fenêtre.  
  
-   **WS_TILED** crée une fenêtre superposée. Une fenêtre superposée a une barre de titre et une bordure. Identique à la **WS_OVERLAPPED** style.  
  
-   **WS_TILEDWINDOW** crée une fenêtre superposée avec la **WS_OVERLAPPED**, **WS_CAPTION**, **WS_SYSMENU**, **WS_THICKFRAME**, **WS_MINIMIZEBOX**, et **WS_MAXIMIZEBOX** styles. Identique à la **WS_OVERLAPPEDWINDOW** style.  
  
-   **WS_VISIBLE** crée une fenêtre qui est initialement visible.  
  
-   **WS_VSCROLL** crée une fenêtre comportant une barre de défilement verticale.  
  
## <a name="see-also"></a>Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CWnd::Create](../../mfc/reference/cwnd-class.md#create)   
 [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)   
 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)


