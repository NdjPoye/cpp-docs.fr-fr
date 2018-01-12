---
title: "Image des Classes de fenêtre (Architecture) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.frame
dev_langs: C++
helpviewer_keywords: frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f1caf8e4b93e18675b810ced962df6e8adcf521a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="frame-window-classes-architecture"></a>Classes de fenêtre frame (architecture)
Dans l’architecture document/vue, fenêtres frame sont des fenêtres qui contiennent une fenêtre d’affichage. Ils prennent également en charge ayant contrôle barres qui leur sont attachées.  
  
 Dans plusieurs applications d’interface (multidocument MDI) document, la fenêtre principale est dérivée de `CMDIFrameWnd`. Il contient des frames les documents qui sont indirectement `CMDIChildWnd` objets. Le `CMDIChildWnd` objets, à son tour, affichent des documents.  
  
 Dans les applications SDI (interface) de document unique, la fenêtre principale, dérivé de `CFrameWnd`, contient la vue du document actif.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 La classe de base pour la fenêtre frame principale d’une application SDI. Également la classe de base pour toutes les autres classes de fenêtre frame.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 La classe de base pour la fenêtre frame principale d’une application MDI.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 La classe de base pour les fenêtres frame de document d’une application MDI.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Fournit la fenêtre frame pour une vue lorsqu’un document serveur est en cours de modification en place.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../mfc/class-library-overview.md)

