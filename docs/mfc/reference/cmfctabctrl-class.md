---
title: "CMFCTabCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCTabCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTabCtrl class"
  - "CMFCTabCtrl constructor"
  - "CMFCTabCtrl::GetTabFromPoint method"
  - "CMFCTabCtrl::IsPtInTabArea method"
  - "CMFCTabCtrl::MoveTab method"
  - "CMFCTabCtrl::PreTranslateMessage method"
  - "CMFCTabCtrl::RecalcLayout method"
  - "CMFCTabCtrl::SwapTabs method"
ms.assetid: d441385d-2c72-4203-96fa-deae2273da35
caps.latest.revision: 33
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCTabCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCTabCtrl` fournit les fonctionnalités pour un contrôle onglet.  Le contrôle onglet affiche une fenêtre ancrable avec les onglets plate ou en trois dimensions à son haut ou bas.  Les tabulations peuvent le texte et une image et peuvent changer la couleur si actifs.  
  
## Syntaxe  
  
```  
class CMFCTabCtrl : public CMFCBaseTabCtrl  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCTabCtrl::CMFCTabCtrl`|Constructeur par défaut.|  
|`CMFCTabCtrl::~CMFCTabCtrl`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCTabCtrl::ActivateMDITab](../Topic/CMFCTabCtrl::ActivateMDITab.md)|Affiche l'onglet spécifié du contrôle onglet actuel et définit le focus sur cette table.|  
|[CMFCTabCtrl::AllowDestroyEmptyTabbedPane](../Topic/CMFCTabCtrl::AllowDestroyEmptyTabbedPane.md)||  
|[CMFCTabCtrl::AutoSizeWindow](../Topic/CMFCTabCtrl::AutoSizeWindow.md)|Spécifie si l'infrastructure est de redimensionner la zone cliente de toutes les fenêtres de contrôle onglet lorsqu'un élément de l'interface utilisateur du contrôle onglet change.|  
|[CMFCTabCtrl::CalcRectEdit](../Topic/CMFCTabCtrl::CalcRectEdit.md)|Dégonfle la taille de la zone spécifiée d'onglet.  \(Substitutions `CMFCBaseTabCtrl::CalcRectEdit`.\)|  
|[CMFCTabCtrl::Create](../Topic/CMFCTabCtrl::Create.md)|Crée le contrôle onglet et l'attache à l'objet d' `CMFCTabCtrl` .|  
|`CMFCTabCtrl::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCTabCtrl::EnableActiveTabCloseButton](../Topic/CMFCTabCtrl::EnableActiveTabCloseButton.md)|Affiche ou masque un bouton Fermer**X**\(\) sur l'onglet actif.|  
|[CMFCTabCtrl::EnableInPlaceEdit](../Topic/CMFCTabCtrl::EnableInPlaceEdit.md)|Active ou désactive les étiquettes modifiables de l'onglet.  \(Substitutions [CMFCBaseTabCtrl::EnableInPlaceEdit](../Topic/CMFCBaseTabCtrl::EnableInPlaceEdit.md).\)|  
|[CMFCTabCtrl::EnableTabDocumentsMenu](../Topic/CMFCTabCtrl::EnableTabDocumentsMenu.md)|Remplace deux boutons qui mettent défiler les onglets de fenêtre avec un bouton qui ouvre un menu de windows avec onglets.|  
|[CMFCTabCtrl::EnsureVisible](../Topic/CMFCTabCtrl::EnsureVisible.md)|Garantit qu'un onglet soit visible.|  
|[CMFCTabCtrl::GetDocumentIcon](../Topic/CMFCTabCtrl::GetDocumentIcon.md)|Récupère le symbole associé à un onglet dans un menu contextuel des fenêtres à onglet.|  
|[CMFCTabCtrl::GetFirstVisibleTabNum](../Topic/CMFCTabCtrl::GetFirstVisibleTabNum.md)|Récupère l'index du premier onglet qui est visible dans le contrôle onglet actuel.|  
|[CMFCTabCtrl::GetResizeMode](../Topic/CMFCTabCtrl::GetResizeMode.md)|Récupère une valeur qui spécifie comment le contrôle onglet actuel peut être redimensionné.|  
|[CMFCTabCtrl::GetScrollBar](../Topic/CMFCTabCtrl::GetScrollBar.md)|Extrait un pointeur vers l'objet de barre de défilement qui est associé au contrôle onglet.|  
|[CMFCTabCtrl::GetTabArea](../Topic/CMFCTabCtrl::GetTabArea.md)|Récupère le rectangle englobant de la zone d'étiquette d'onglet en haut ou en bas du contrôle onglet.  \(Substitutions [CMFCBaseTabCtrl::GetTabArea](../Topic/CMFCBaseTabCtrl::GetTabArea.md).\)|  
|`CMFCTabCtrl::GetTabFromPoint`|Récupère l'onglet qui contient un point spécifié.  \(Substitutions [CMFCBaseTabCtrl::GetTabFromPoint](../Topic/CMFCBaseTabCtrl::GetTabFromPoint.md).\)|  
|[CMFCTabCtrl::GetTabMaxWidth](../Topic/CMFCTabCtrl::GetTabMaxWidth.md)|Extrait la largeur maximale d'une table.|  
|[CMFCTabCtrl::GetTabsHeight](../Topic/CMFCTabCtrl::GetTabsHeight.md)|Extrait la hauteur du domaine d'onglet du contrôle onglet actuel.|  
|[CMFCTabCtrl::GetTabsRect](../Topic/CMFCTabCtrl::GetTabsRect.md)|Récupère un rectangle limites que le domaine d'onglet du contrôle onglet actuel.  \(Substitutions [CMFCBaseTabCtrl::GetTabsRect](../Topic/CMFCBaseTabCtrl::GetTabsRect.md).\)|  
|`CMFCTabCtrl::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCTabCtrl::GetWndArea](../Topic/CMFCTabCtrl::GetWndArea.md)|Récupère les limites de la zone cliente du contrôle onglet actuel.|  
|[CMFCTabCtrl::HideActiveWindowHorzScrollBar](../Topic/CMFCTabCtrl::HideActiveWindowHorzScrollBar.md)|Masque la barre de défilement horizontale, le cas échéant, de la fenêtre active.|  
|[CMFCTabCtrl::HideInactiveWindow](../Topic/CMFCTabCtrl::HideInactiveWindow.md)|Spécifie si l'infrastructure est d'afficher des fenêtres de contrôle tab inactives.|  
|[CMFCTabCtrl::HideNoTabs](../Topic/CMFCTabCtrl::HideNoTabs.md)|Active ou désactive dessiner la zone de l'onglet s'il n'existe aucun onglet visible.|  
|[CMFCTabCtrl::HideSingleTab](../Topic/CMFCTabCtrl::HideSingleTab.md)|Active ou désactive dessiner un onglet lors d'une fenêtre avec onglets unique.  \(Substitutions [CMFCBaseTabCtrl::HideSingleTab](../Topic/CMFCBaseTabCtrl::HideSingleTab.md).\)|  
|[CMFCTabCtrl::IsActiveInMDITabGroup](../Topic/CMFCTabCtrl::IsActiveInMDITabGroup.md)|Indique si l'onglet actuel d'un contrôle onglet est l'onglet actif à un groupe d'onglets d'interface multidocument.|  
|[CMFCTabCtrl::IsActiveTabBoldFont](../Topic/CMFCTabCtrl::IsActiveTabBoldFont.md)|Indique si le texte de l'onglet actif est restitué à l'aide d'une police de caractère grasse.|  
|[CMFCTabCtrl::IsActiveTabCloseButton](../Topic/CMFCTabCtrl::IsActiveTabCloseButton.md)|Indique si le bouton Fermer**X**\(\) s'affiche sur un onglet actif ou l'angle supérieur droit de la zone de l'onglet.|  
|[CMFCTabCtrl::IsDrawFrame](../Topic/CMFCTabCtrl::IsDrawFrame.md)|Indique si la fenêtre avec onglets dessine un rectangle de frame autour de les volets incorporés.|  
|[CMFCTabCtrl::IsFlatFrame](../Topic/CMFCTabCtrl::IsFlatFrame.md)|Indique si le cadre autour de la zone d'onglet est stable ou 3D.|  
|[CMFCTabCtrl::IsFlatTab](../Topic/CMFCTabCtrl::IsFlatTab.md)|Indique, de l'apparence des onglets dans le contrôle onglet actuel soit en deux dimensions ou pas.|  
|[CMFCTabCtrl::IsLeftRightRounded](../Topic/CMFCTabCtrl::IsLeftRightRounded.md)|Indique si l'apparence du côté gauche et droite d'un onglet dans le contrôle onglet actuel est arrondie.|  
|[CMFCTabCtrl::IsMDITabGroup](../Topic/CMFCTabCtrl::IsMDITabGroup.md)|Indique si le contrôle onglet actuel est contenu dans la zone cliente d'une fenêtre d'interface multidocument.|  
|[CMFCTabCtrl::IsOneNoteStyle](../Topic/CMFCTabCtrl::IsOneNoteStyle.md)|Indique si le contrôle onglet actuel est affiché dans le style Microsoft OneNote.|  
|`CMFCTabCtrl::IsPtInTabArea`|Détermine si un point se trouve à l'intérieur de la zone de l'onglet.  \(Substitutions [CMFCBaseTabCtrl::IsPtInTabArea](../Topic/CMFCBaseTabCtrl::IsPtInTabArea.md).\)|  
|[CMFCTabCtrl::IsSharedScroll](../Topic/CMFCTabCtrl::IsSharedScroll.md)|Indique si le contrôle onglet actuel a une barre de défilement qui peut faire défiler ses onglets en tant que groupe.|  
|[CMFCTabCtrl::IsTabDocumentsMenu](../Topic/CMFCTabCtrl::IsTabDocumentsMenu.md)|Indique si le contrôle onglet affiche des boutons de défilement ou un bouton qui affiche un menu de windows avec onglets.|  
|[CMFCTabCtrl::IsVS2005Style](../Topic/CMFCTabCtrl::IsVS2005Style.md)|Indique si les onglets sont affichés dans le style Visual Studio .NET 2005.|  
|[CMFCTabCtrl::ModifyTabStyle](../Topic/CMFCTabCtrl::ModifyTabStyle.md)|Spécifie l'apparence des onglets dans le contrôle onglet actuel.|  
|`CMFCTabCtrl::MoveTab`|Déplace un onglet à une autre position d'onglet.  \(Substitutions [CMFCBaseTabCtrl::MoveTab](../Topic/CMFCBaseTabCtrl::MoveTab.md).\)|  
|[CMFCTabCtrl::OnDragEnter](../Topic/CMFCTabCtrl::OnDragEnter.md)|Appelé par l'infrastructure lorsque le curseur est d'abord glisser dans la fenêtre de contrôle tab.|  
|[CMFCTabCtrl::OnDragOver](../Topic/CMFCTabCtrl::OnDragOver.md)|Appelé par l'infrastructure pendant une opération de glissement lorsque la souris est déplacé sur la fenêtre cible de déplacement.  \(Substitutions [CMFCBaseTabCtrl::OnDragOver](../Topic/CMFCBaseTabCtrl::OnDragOver.md).\)|  
|[CMFCTabCtrl::OnShowTabDocumentsMenu](../Topic/CMFCTabCtrl::OnShowTabDocumentsMenu.md)|Affiche un menu contextuel des fenêtres à onglets, attend que l'utilisateur sélectionne un onglet, puis fait à l'onglet sélectionné l'onglet actif.|  
|`CMFCTabCtrl::PreTranslateMessage`|Traduit des messages de fenêtre pour qu'ils soient distribués aux fonctions Windows de [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et de [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) .  \(Substitutions [CMFCBaseTabCtrl::PreTranslateMessage](../Topic/CMFCBaseTabCtrl::PreTranslateMessage.md).\)|  
|`CMFCTabCtrl::RecalcLayout`|Recalcule la disposition interne du contrôle onglet.  \(Substitutions [CMFCBaseTabCtrl::RecalcLayout](../Topic/CMFCBaseTabCtrl::RecalcLayout.md).\)|  
|[CMFCTabCtrl::SetActiveInMDITabGroup](../Topic/CMFCTabCtrl::SetActiveInMDITabGroup.md)|Définit l'onglet actuel d'un contrôle onglet comme onglet actif à un groupe d'onglets d'interface multidocument.|  
|[CMFCTabCtrl::SetActiveTab](../Topic/CMFCTabCtrl::SetActiveTab.md)|Lance une table.  \(Substitutions [CMFCBaseTabCtrl::SetActiveTab](../Topic/CMFCBaseTabCtrl::SetActiveTab.md).\)|  
|[CMFCTabCtrl::SetActiveTabBoldFont](../Topic/CMFCTabCtrl::SetActiveTabBoldFont.md)|Active ou désactive de utilisation d'une police de caractère grasse sur les onglets actifs.|  
|[CMFCTabCtrl::SetDrawFrame](../Topic/CMFCTabCtrl::SetDrawFrame.md)|Active ou désactive le rectangle du frame de drawinga autour d'une barre incorporée.|  
|[CMFCTabCtrl::SetFlatFrame](../Topic/CMFCTabCtrl::SetFlatFrame.md)|Spécifie si dessiner un plate ou un frame 3D autour de la zone de l'onglet.|  
|[CMFCTabCtrl::SetImageList](../Topic/CMFCTabCtrl::SetImageList.md)|Spécifie une liste d'images.  \(Substitutions [CMFCBaseTabCtrl::SetImageList](../Topic/CMFCBaseTabCtrl::SetImageList.md).\)|  
|[CMFCTabCtrl::SetResizeMode](../Topic/CMFCTabCtrl::SetResizeMode.md)|Spécifie comment le contrôle onglet actuel peut être redimensionné et affiche à nouveau le contrôle.|  
|[CMFCTabCtrl::SetTabMaxWidth](../Topic/CMFCTabCtrl::SetTabMaxWidth.md)|Spécifie la largeur maximale de l'onglet dans une fenêtre avec onglets.|  
|[CMFCTabCtrl::StopResize](../Topic/CMFCTabCtrl::StopResize.md)|Termine la actuelle se redimensionnent l'opération sur le contrôle onglet.|  
|`CMFCTabCtrl::SwapTabs`|Permute une paire d'onglets.  \(Substitutions [CMFCBaseTabCtrl::SwapTabs](../Topic/CMFCBaseTabCtrl::SwapTabs.md).\)|  
|[CMFCTabCtrl::SynchronizeScrollBar](../Topic/CMFCTabCtrl::SynchronizeScrollBar.md)|Dessine une barre de défilement horizontale sur un contrôle onglet qui affiche des onglets à deux dimensions.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCTabCtrl::m\_bEnableActivate](../Topic/CMFCTabCtrl::m_bEnableActivate.md)|Empêché la vue active du focus perdant lorsqu'un nouvel onglet est inséré et activé.|  
  
## Notes  
 Prend en charge de classe d' `CMFCTabCtrl` :  
  
-   Styles de contrôle onglet qui incluent 3D, plate, et plate par une barre de défilement horizontale partagée.  
  
-   Onglets situés en haut ou en bas de la fenêtre.  
  
-   Onglets qui texte, des images, ou texte et images.  
  
-   Onglets qui change la couleur lorsque l'onglet est actif.  
  
-   Modifications de bordure de taille pour les onglets réglables.  
  
-   Fenêtres à détachables onglet.  
  
 La classe d' `CMFCTabCtrl` peut être utilisé dans une boîte de dialogue, mais est prévue pour les applications qui utilisent ancrer des barres de contrôles comme [!INCLUDE[ofprexcel](../../mfc/reference/includes/ofprexcel_md.md)] et [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  Pour plus d'informations, consultez [CDockablePane Class](../../mfc/reference/cdockablepane-class.md).  
  
 Procédez comme suit pour ajouter un redimensionnable, ancrage en le contrôle onglet dans votre application :  
  
1.  Créez une instance de [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md).  
  
2.  Appelez [CDockablePane::Create](../Topic/CDockablePane::Create.md).  
  
3.  Utilisez [CBaseTabbedPane::AddTab](../Topic/CBaseTabbedPane::AddTab.md) ou [CMFCBaseTabCtrl::InsertTab](../Topic/CMFCBaseTabCtrl::InsertTab.md) pour ajouter de nouveaux onglets.  
  
4.  Appelez [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md) afin que le contrôle onglet actuel d'ancrage puisse l'ancrer à la fenêtre frame principale.  
  
5.  Appelez [CFrameWndEx::DockPane](../Topic/CFrameWndEx::DockPane.md) pour ancrer la fenêtre avec onglets au frame principal.  
  
 Pour obtenir un exemple de création d'une fenêtre avec onglets comme une barre de contrôles d'ancrage, consultez [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md).  Pour utiliser `CMFCTabCtrl` comme un contrôle non ancrage, créez un objet d' `CMFCTabCtrl` puis appelez [CMFCTabCtrl::Create](../Topic/CMFCTabCtrl::Create.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCTabCtrl` pour configurer un objet d' `CMFCTabCtrl` .  L'exemple montre comment ajouter un onglet, afficher le bouton Fermer sur l'onglet actif, activer les étiquettes modifiables de l'onglet, puis afficher un menu contextuel des étiquettes de fenêtre avec onglets.  Cet exemple est extrait d' [Exemple de collection d'état](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection#1](../../mfc/reference/codesnippet/CPP/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection#3](../../mfc/reference/codesnippet/CPP/cmfctabctrl-class_2.cpp)]  
  
## Configuration requise  
 **en\-tête :** afxtabctrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)   
 [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md)