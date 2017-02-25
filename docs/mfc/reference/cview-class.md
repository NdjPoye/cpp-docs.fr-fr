---
title: "CView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fenêtres enfants, vues"
  - "CView class"
  - "document/view architecture"
  - "frame windows [C++], vues"
  - "entrée, and view class"
  - "MDI (C++), view windows"
  - "vues multiples"
  - "aperçu avant impression, view windows"
  - "user input [C++], interpreting through view class"
  - "vues (C++), view classes"
  - "windows [C++], vues"
ms.assetid: 9cff3c56-7564-416b-b9a4-71a9254ed755
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités de base des classes d'affichage définies par l'utilisateur.  
  
## Syntaxe  
  
```  
class AFX_NOVTABLE CView : public CWnd  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CView::CView](../Topic/CView::CView.md)|Construit un objet `CView`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CView::DoPreparePrinting](../Topic/CView::DoPreparePrinting.md)|La boîte de dialogue d'impression d'affichages et crée le contexte de périphérique d'impression ; appel en substituant la fonction membre d' `OnPreparePrinting` .|  
|[CView::GetDocument](../Topic/CView::GetDocument.md)|Retourne le document associé à la vue.|  
|[CView::IsSelected](../Topic/CView::IsSelected.md)|Teste si un élément de document est sélectionné.  Requis pour le OLE en charge.|  
|[CView::OnDragEnter](../Topic/CView::OnDragEnter.md)|Appelé lorsqu'un élément est d'abord glisser dans la zone de glisser\-déplacer d'une vue.|  
|[CView::OnDragLeave](../Topic/CView::OnDragLeave.md)|Appelé lorsqu'un élément déplacé quitte la région du glisser\-déplacer d'une vue.|  
|[CView::OnDragOver](../Topic/CView::OnDragOver.md)|Appelé lorsqu'un élément est déplacé sur la zone de glisser\-déplacer d'une vue.|  
|[CView::OnDragScroll](../Topic/CView::OnDragScroll.md)|Appelé pour déterminer si le curseur est déplacé dans la zone de défilement de la fenêtre.|  
|[CView::OnDrop](../Topic/CView::OnDrop.md)|Appelé lorsqu'un élément a été supprimé dans la zone de glisser\-déplacer d'une vue, gestionnaire par défaut.|  
|[CView::OnDropEx](../Topic/CView::OnDropEx.md)|Appelé lorsqu'un élément a été supprimé dans la zone de glisser\-déplacer d'une vue, gestionnaire primaire.|  
|[CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md)|Appelé après une vue soit d'abord liée à un document.|  
|[CView::OnPrepareDC](../Topic/CView::OnPrepareDC.md)|Appelé avant que la fonction membre d' `OnDraw` appelée pour l'écran ou la fonction membre d' `OnPrint` est appelé pour imprimer ou aperçu avant impression.|  
|[CView::OnScroll](../Topic/CView::OnScroll.md)|Appelé lorsque de OLE éléments sont déplacés au delà de les bordures de la vue.|  
|[CView::OnScrollBy](../Topic/CView::OnScrollBy.md)|Appelé lorsqu'une vue contenant de OLE éléments sur place actifs vous faites est.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CView::OnActivateFrame](../Topic/CView::OnActivateFrame.md)|Appelé lorsque la fenêtre frame contenant la vue est activée ou désactivée.|  
|[CView::OnActivateView](../Topic/CView::OnActivateView.md)|Appelé lorsqu'une vue est activée.|  
|[CView::OnBeginPrinting](../Topic/CView::OnBeginPrinting.md)|Appelé lorsqu'un travail d'impression démarre ; substitution pour allouer des ressources \(GDI\) de Graphics Device Interface.|  
|[CView::OnDraw](../Topic/CView::OnDraw.md)|Appelé pour afficher une image de le document pour l'écran, l'impression, ou l'aperçu avant impression.  Implémentation requise.|  
|[CView::OnEndPrinting](../Topic/CView::OnEndPrinting.md)|Appelé lorsqu'un travail d'impression se termine ; substitution pour libérer les ressources GDI.|  
|[CView::OnEndPrintPreview](../Topic/CView::OnEndPrintPreview.md)|Appelé lorsque le mode d'aperçu est annulé.|  
|[CView::OnPreparePrinting](../Topic/CView::OnPreparePrinting.md)|Appelé avant qu'un document ne soit imprimé ou affiché un aperçu de ; substitution pour initialiser la boîte de dialogue d'impression.|  
|[CView::OnPrint](../Topic/CView::OnPrint.md)|Appelé pour imprimer ou afficher un aperçu d'une page du document.|  
|[CView::OnUpdate](../Topic/CView::OnUpdate.md)|Appelé pour indiquer une vue que le document a été modifié.|  
  
## Notes  
 Une vue est attachée à un document et sert d'intermédiaire entre le document et l'utilisateur : la vue affiche une image de le document sur l'écran ou une imprimante et interprète les entrées d'utilisateur comme opérations sur le document.  
  
 Une vue est un enfant d'une fenêtre frame.  Plusieurs vues peuvent partager une fenêtre frame, comme dans le cas d'une fenêtre fractionnée.  La relation entre une classe d'affichage, une classe de fenêtre frame, et une classe de document est générée par un objet d' `CDocTemplate` .  Lorsque l'utilisateur ouvre une nouvelle fenêtre ou fractionne existant, l'infrastructure construit une nouvelle vue et la lié au document.  
  
 Une vue peut être jointe à un document, mais un document peut avoir plusieurs points de vue liés à est immédiatement — par exemple, si le document est affiché dans une fenêtre fractionnée ou de plusieurs fenêtres enfants dans une application d'interface multidocument \(MDI\).  Votre application peut prendre en charge différents types de vues pour un type de document donné ; par exemple, un programme de traitement de texte peut fournir une vue de texte complet d'un document et un mode Plan qui affiche uniquement les en\-têtes de section.  Ces différents types de vues peuvent être placés dans des fenêtres frames séparées ou dans des volets distincts d'une fenêtre frame unique si vous utilisez une fenêtre fractionnée.  
  
 Une vue peut être chargé de gérer plusieurs types d'entrée, tels que l'entrée au clavier, l'entrée de souris ou d'entrée via le glisser\-déplacer, ainsi que les commandes des menus, barres d'outils, ou des barres de défilement.  Une vue reçoit des commandes faites suivre par sa fenêtre frame.  Si la vue ne gère pas la commande donnée, il effectue le suivi de la commande son document associé.  Comme toutes les cibles de la commande, une vue gère les messages via une table des messages.  
  
 La vue est chargé d'afficher et de modifier les données du document mais pas de l'enregistrer.  Le document fournit à la vue des détails nécessaires sur ses données.  Vous pouvez laisser l'accès de vue des données membres du document directement, ou vous pouvez fournir des fonctions membres dans la classe de le document pour la classe d'affichage à l'appel.  
  
 Lorsque les données d'un document, la vue responsable des modifications appelle généralement la fonction de [CDocument::UpdateAllViews](../Topic/CDocument::UpdateAllViews.md) pour le document, qui signale toutes les autres affichages en appelant la fonction membre d' `OnUpdate` pour chacun.  L'implémentation par défaut d' `OnUpdate` invalide la zone cliente entière de la vue.  Vous pouvez le substituer pour invalider uniquement les régions de la zone cliente qui mappent aux parties modifiées du document.  
  
 Pour utiliser `CView`, dérivez une classe de celle\-ci et implémentez la fonction membre d' `OnDraw` pour exécuter l'écran.  Vous pouvez également utiliser `OnDraw` pour effectuer l'impression et l'aperçu avant impression.  L'infrastructure gère la boucle d'impression pour l'impression et afficher un aperçu de votre document.  
  
 Une vue gère les messages de la barre de défilement avec les fonctions membres de [CWnd::OnHScroll](../Topic/CWnd::OnHScroll.md) et de [CWnd::OnVScroll](../Topic/CWnd::OnVScroll.md) .  Vous pouvez implémenter la gestion des messages de barre de défilement dans ces fonctions, ou vous pouvez utiliser la classe dérivée par `CView`[CScrollView](../../mfc/reference/cscrollview-class.md) pour gérer le défilement pour vous.  
  
 Outre l' `CScrollView`, la bibliothèque MFC fournit neuf autres classes dérivées d' `CView`:  
  
-   [CCtrlView](../../mfc/reference/cctrlview-class.md), une vue qui permet l'utilisation de l'architecture Document\/Vue avec l'arborescence, la liste, puis les contrôles richedit.  
  
-   [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md), une vue qui affiche des enregistrements de base de données dans la boîte de dialogue contrôle.  
  
-   [CEditView](../../mfc/reference/ceditview-class.md), une vue qui fournit un éditeur de texte multiligne simple.  Vous pouvez utiliser un objet d' `CEditView` comme un contrôle dans une boîte de dialogue et de vues sur un document.  
  
-   [CFormView](../../mfc/reference/cformview-class.md), une vue déroulante qui contient des contrôles de boîte de dialogue et est basé sur une ressource modèle de boîte de dialogue.  
  
-   [CListView](../../mfc/reference/clistview-class.md), une vue qui permet l'utilisation de l'architecture Document\/Vue avec les contrôles de liste.  
  
-   [CRecordView](../../mfc/reference/crecordview-class.md), une vue qui affiche des enregistrements de base de données dans la boîte de dialogue contrôle.  
  
-   [CRichEditView](../../mfc/reference/cricheditview-class.md), une vue qui permet l'utilisation de l'architecture Document\/Vue avec les contrôles richedit.  
  
-   [CScrollView](../../mfc/reference/cscrollview-class.md), une vue qui fournit automatiquement la prise en charge de défilement.  
  
-   [CTreeView](../../mfc/reference/ctreeview-class.md), une vue qui permet l'utilisation de l'architecture Document\/Vue avec l'arborescence contrôle.  
  
 La classe d' `CView` a également une classe dérivée d'implémentation nommée **CPreviewView**, qui est utilisée par l'infrastructure pour exécuter afficher un aperçu d'impression.  Cette classe fournit la prise en charge des fonctionnalités uniques dans la fenêtre d'aperçu avant impression, telle qu'une barre d'outils, un aperçu unique ou à double page, et un zoom, c. autrement dit., agrandissant l'image affichée un aperçu de.  Vous n'avez besoin d'appeler ou remplacer aucune des fonctions membres de CPreviewView sauf si vous souhaitez implémenter votre propre interface pour l'aperçu avant impression \(par exemple, si vous souhaitez prendre en charge la modification en mode aperçu avant impression\).  Pour plus d'informations sur l'utilisation `CView`, consultez [architecture Document\/Vue](../../mfc/document-view-architecture.md) et l' [imprimer](../../mfc/printing.md).  En outre, consultez [note technique 30](../../mfc/tn030-customizing-printing-and-print-preview.md) pour plus d'informations sur la personnalisation de l'aperçu avant impression.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CView`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [MFC exemple MDIDOCVW](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [CSplitterWnd Class](../../mfc/reference/csplitterwnd-class.md)   
 [CDC, classe](../../mfc/reference/cdc-class.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)