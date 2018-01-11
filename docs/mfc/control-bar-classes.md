---
title: "Classes de barre de contrôle | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.control
dev_langs: C++
helpviewer_keywords: control bars [MFC], classes
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 44fcecbf1d7ddb6c46469f25349d972c8b317809
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="control-bar-classes"></a>Classes de barre de contrôle
Barres de contrôles sont attachés à une fenêtre frame. Elles contiennent des boutons, les volets d’état ou un modèle de boîte de dialogue. Barres de contrôles de flottants, également appelés palettes d’outils, sont implémentées par les joindre à un [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md) objet.  
  
## <a name="framework-control-bars"></a>Barres de contrôles de Framework  
 Ces barres de contrôle font partie intégrante de l’infrastructure MFC. Ils sont plus faciles à utiliser et plus puissants que les barres de contrôles Windows, car ils sont intégrés à l’infrastructure. La plupart des applications MFC utilisent ces barres de contrôle, plutôt que les barres de contrôles Windows.  
  
 [CControlBar](../mfc/reference/ccontrolbar-class.md)  
 La classe de base pour les barres de contrôles MFC répertoriés dans cette section. Une barre de contrôle est une fenêtre alignée sur le bord d’une fenêtre frame. La barre de contrôle contient `HWND`-en fonction des contrôles enfants ou des contrôles non basés sur un `HWND`, tels que les boutons de barre d’outils.  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 Une barre de contrôle qui est basée sur un modèle de boîte de dialogue.  
  
 [CReBar](../mfc/reference/crebar-class.md)  
 Prend en charge une barre d’outils qui peut contenir des fenêtres enfants supplémentaires sous la forme de contrôles.  
  
 [CToolBar](../mfc/reference/ctoolbar-class.md)  
 Les fenêtres de contrôle de barre d’outils contenant des boutons de commande de bitmap non basée sur un `HWND`. La plupart des applications MFC utilisent cette classe au lieu de `CToolBarCtrl`.  
  
 [CStatusBar](../mfc/reference/cstatusbar-class.md)  
 La classe de base pour les fenêtres de contrôle de barre d’état. La plupart des applications MFC utilisent cette classe au lieu de `CStatusBarCtrl`.  
  
## <a name="windows-control-bars"></a>Barres de contrôles Windows  
 Ces barres de contrôles sont des wrappers pour les contrôles Windows correspondants. Car ils ne sont pas intégrées avec l’infrastructure, ils sont plus difficiles à utiliser que les barres de contrôles répertoriés précédemment. La plupart des applications MFC utilisent les barres de contrôles répertoriés précédemment.  
  
 [CRebarCtrl](../mfc/reference/crebarctrl-class.md)  
 Implémente le contrôle interne de la `CRebar` objet.  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 Une fenêtre horizontale, généralement divisée en volets, dans laquelle une application peut afficher des informations d’état.  
  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Fournit les fonctionnalités du contrôle commun de barre d'outils Windows.  
  
## <a name="related-classes"></a>Classes associées  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 Une petite fenêtre contextuelle qui affiche une ligne unique de texte qui décrit le rôle d’un outil dans une application.  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 Gère le stockage persistant d’ancrage des données d’état pour les barres de contrôles.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../mfc/class-library-overview.md)

