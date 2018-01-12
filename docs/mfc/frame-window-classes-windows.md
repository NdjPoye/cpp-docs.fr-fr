---
title: "Classes de fenêtre (Windows) de frame | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.frame
dev_langs: C++
helpviewer_keywords: frame window classes [MFC], reference
ms.assetid: 6342ec5f-f922-4da8-a78e-2f5f994c7142
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c2668a8334192d4de199f1c42a648b74add1ca5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="frame-window-classes-windows"></a>Classes de fenêtre frame (Fenêtres)
Fenêtres frame sont des fenêtres frame d’une application ou une partie d’une application. Fenêtres frame contiennent généralement des autres fenêtres, telles que les vues, les barres d’outils et les barres d’état. Dans le cas de `CMDIFrameWnd`, ils peuvent contenir `CMDIChildWnd` objets indirectement.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 La classe de base pour la fenêtre frame principale d’une application SDI. Également la classe de base pour toutes les autres classes de fenêtre frame.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 La classe de base pour la fenêtre frame principale d’une application MDI.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 La classe de base pour les fenêtres frame de document d’une application MDI.  
  
 [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md)  
 Une fenêtre frame de demi-hauteur généralement visible autour de barres d’outils flottantes.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Fournit la fenêtre frame pour une vue lorsqu’un document serveur est en cours de modification en place.  
  
## <a name="related-class"></a>Classe connexe  
 Classe `CMenu` fournit une interface permettant d’accéder aux menus de votre application. Il est utile pour la manipulation des menus dynamiquement au moment de l’exécution ; par exemple, lors de l’ajout ou la suppression d’éléments de menu en fonction du contexte. Bien que les menus sont souvent utilisées avec des fenêtres frame, elles peuvent également servir avec les boîtes de dialogue et les autres fenêtres non-enfant.  
  
 [CMenu](../mfc/reference/cmenu-class.md)  
 Encapsule une `HMENU` handle vers la barre de menus et les menus contextuels de l’application.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../mfc/class-library-overview.md)

