---
title: "CScrollView Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CScrollView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CScrollView class"
  - "scrolling views"
  - "vues, défilement"
ms.assetid: 4ba16dac-1acb-4be0-bb55-5fb695b6948d
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CScrollView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CView](../../mfc/reference/cview-class.md) avec les fonctions de défilement.  
  
## Syntaxe  
  
```  
class CScrollView : public CView  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CScrollView::CScrollView](../Topic/CScrollView::CScrollView.md)|Construit un objet `CScrollView`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CScrollView::CheckScrollBars](../Topic/CScrollView::CheckScrollBars.md)|Indique si la zone de défilement a des barres de défilement horizontale et verticale.|  
|[CScrollView::FillOutsideRect](../Topic/CScrollView::FillOutsideRect.md)|Remplit une zone d'une vue à l'extérieur de la zone faisante défilement.|  
|[CScrollView::GetDeviceScrollPosition](../Topic/CScrollView::GetDeviceScrollPosition.md)|Obtient la position actuelle de défilement dans les unités.|  
|[CScrollView::GetDeviceScrollSizes](../Topic/CScrollView::GetDeviceScrollSizes.md)|Obtient le mode de mappage en cours, la taille totale, et la ligne et la taille de page de la vue déroulante.  Les tailles sont des unités.|  
|[CScrollView::GetScrollPosition](../Topic/CScrollView::GetScrollPosition.md)|Obtient la position actuelle de défilement en unités logiques.|  
|[CScrollView::GetTotalSize](../Topic/CScrollView::GetTotalSize.md)|Obtient la taille totale de la zone de défilement en unités logiques.|  
|[CScrollView::ResizeParentToFit](../Topic/CScrollView::ResizeParentToFit.md)|Fait dicter la taille de la vue la taille de son frame.|  
|[CScrollView::ScrollToPosition](../Topic/CScrollView::ScrollToPosition.md)|Fait défiler la vue à un point donné, spécifié dans des unités logiques.|  
|[CScrollView::SetScaleToFitSize](../Topic/CScrollView::SetScaleToFitSize.md)|Met la zone de défilement en mode d'échelle\-à\- ajustement.|  
|[CScrollView::SetScrollSizes](../Topic/CScrollView::SetScrollSizes.md)|Définit le mode de mappage de la zone de défilement, taille totale, et le défilement horizontal et vertical s'élève.|  
  
## Notes  
 Vous pouvez gérer le défilement standard vous\-même dans toute classe dérivée d' `CView` en substituant les fonctions membres message\- mappées d' [OnHScroll](../Topic/CWnd::OnHScroll.md) et d' [OnVScroll](../Topic/CWnd::OnVScroll.md) .  Mais `CScrollView` ajoute les fonctionnalités suivantes à ses fonctions d' `CView` :  
  
-   Il gère la fenêtre et la taille et les modes de mappage de la fenêtre d'affichage.  
  
-   Elle fait défiler automatiquement en réponse à des messages de barre de défilement.  
  
-   Elle fait défiler automatiquement en réponse à des messages de clavier, d'une souris non défilement, ou de la roue d'IntelliMouse.  
  
 Pour faire défiler automatiquement en réponse à des messages de clavier, ajoutez un message WM\_KEYDOWN, et déterminez VK\_DOWN, VK\_PREV et appel [SetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787597).  
  
 Vous pouvez gérer le défilement de roulette de la souris vous\-même en substituant les fonctions membres message\-mappées d' [OnMouseWheel](../Topic/CWnd::OnMouseWheel.md) et d' [OnRegisteredMouseWheel](../Topic/CWnd::OnRegisteredMouseWheel.md) .  Lorsqu'elles sont pour `CScrollView`, ces fonctions membres prennent en charge le comportement recommandé pour [WM\_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617), le message de rotation de roue.  
  
 Pour tirer parti du défilement automatique, dérivez votre classe d'affichage d' `CScrollView` au lieu d ' `CView`.  Lorsque la vue est d'abord créée, si vous souhaitez calculer la taille de la vue déroulante en fonction de la taille du document, appelez la fonction membre d' `SetScrollSizes` de votre substitution de [CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) ou de [CView::OnUpdate](../Topic/CView::OnUpdate.md).  \(Vous devez écrire votre propre code pour interroger la taille du document.  Pour obtenir un exemple, consultez [Griffonnez l'exemple](../../top/visual-cpp-samples.md).\)  
  
 L'appel à la fonction membre d' `SetScrollSizes` définit le mode de mappage de la vue, toutes les dimensions de la zone de défilement, et les montants pour défiler horizontalement et verticalement.  Toutes les tailles sont en unités logiques.  La taille logique de la vue est généralement calculée des données stockées dans le document, mais dans certains cas vous pouvez spécifier une taille fixe.  Pour obtenir des exemples de deux approches, consultez [CScrollView::SetScrollSizes](../Topic/CScrollView::SetScrollSizes.md).  
  
 Vous spécifiez les montants pour défiler horizontalement et verticalement en unités logiques.  Par défaut, si l'utilisateur clique sur un axe de barre de défilement en dehors de la case de défilement, `CScrollView` fait défiler une page « . » Si l'utilisateur clique sur une flèche de défilement à l'un ou l'autre de fin d'une barre de défilement, `CScrollView` fait défiler une ligne « . » Par défaut, une page est 1\/10 de la taille totale de la vue ; une ligne est 1\/10 de la Taille de la page.  Remplacez ces valeurs par défaut en passant les tailles personnalisées dans la fonction membre d' `SetScrollSizes` .  Par exemple, vous pouvez définir la taille horizontale à une fraction de la largeur de la taille totale et la taille verticale à la hauteur d'une ligne de la police actuelle.  
  
 Au lieu de défilement, `CScrollView` peut automatiquement mesurer la vue à la taille de la fenêtre active.  Dans ce mode, la vue n'a aucune barre de défilement et la vue logique est étirée ou réduite pour adapter exactement la zone cliente de la fenêtre.  Pour utiliser cette fonctionnalité échelle\-à\- d'ajustement, appelez [CScrollView::SetScaleToFitSize](../Topic/CScrollView::SetScaleToFitSize.md).  \(Invoke `SetScaleToFitSize` ou `SetScrollSizes`, mais pas les deux.\)  
  
 Avant que la fonction membre d' `OnDraw` de votre classe d'affichage dérivée appelée, `CScrollView` ajuste automatiquement l'origine de la fenêtre d'affichage de l'objet contexte de périphérique d' `CPaintDC` qu'elle passe à `OnDraw`.  
  
 Pour ajuster l'origine de la fenêtre d'affichage de la fenêtre de défilement, `CScrollView` remplace [CView::OnPrepareDC](../Topic/CView::OnPrepareDC.md).  Ce réglage automatique est pour le contexte de périphérique d' `CPaintDC` qu' `CScrollView` passe à `OnDraw`, mais vous devez appeler **CScrollView::OnPrepareDC** vous\-même pour tous les autres contextes de périphérique que vous utilisez, par exemple `CClientDC`.  Vous pouvez substituer **CScrollView::OnPrepareDC** pour définir le stylet, la couleur d'arrière\-plan, et d'autres attributs de dessin, mais appelez la classe de base pour effectuer la mise à l'échelle.  
  
 Les barres de défilement peuvent apparaître dans trois emplacements par rapport à une vue, comme indiqué dans les cas suivants :  
  
-   Les barres de défilement standard de style de fenêtre peuvent être définies pour la vue utilisation **WS\_HSCROLL** et **WS\_VSCROLL**[styles Windows](../../mfc/reference/window-styles.md).  
  
-   Les contrôles de barre de défilement peuvent également être ajoutés au frame contenant la vue dans ce cas, l'infrastructure transféré `WM_HSCROLL` et des messages d' `WM_VSCROLL` de la fenêtre frame en cours \(vue active.  
  
-   L'infrastructure transféré également les messages de défilement d'un contrôle separator d' `CSplitterWnd` actuel \- le volet actif de séparateur \(une vue\).  Lorsque la valeur dans [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) avec les barres de défilement partagées, un objet d' `CScrollView` utilisera partagés au lieu de créer son propre.  
  
 Pour plus d'informations sur l'utilisation `CScrollView`, consultez [architecture Document\/Vue](../../mfc/document-view-architecture.md) et le [classes d'affichage dérivées disponibles dans MFC](../../mfc/derived-view-classes-available-in-mfc.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CScrollView`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [DIBLOOK exemple MFC](../../top/visual-cpp-samples.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CSplitterWnd Class](../../mfc/reference/csplitterwnd-class.md)