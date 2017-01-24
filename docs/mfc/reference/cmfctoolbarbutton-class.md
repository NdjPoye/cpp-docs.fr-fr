---
title: "CMFCToolBarButton Class | Microsoft Docs"
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
  - "CMFCToolBarButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarButton class"
ms.assetid: 8a6ecffb-86b0-4f5c-8211-a9146b463efd
caps.latest.revision: 34
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités de bouton à des barres d'outils.  
  
## Syntaxe  
  
```  
class CMFCToolBarButton : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarButton::CMFCToolBarButton](../Topic/CMFCToolBarButton::CMFCToolBarButton.md)|Les éléments et initialise un objet d' `CMFCToolBarButton` .|  
|`CMFCToolBarButton::~CMFCToolBarButton`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarButton::CanBeDropped](../Topic/CMFCToolBarButton::CanBeDropped.md)|Spécifie si un utilisateur peut positionner un bouton dans une barre d'outils ou le menu pendant la personnalisation.|  
|[CMFCToolBarButton::CanBeStored](../Topic/CMFCToolBarButton::CanBeStored.md)|Spécifie si le bouton peut être stocké.|  
|[CMFCToolBarButton::CanBeStretched](../Topic/CMFCToolBarButton::CanBeStretched.md)|Spécifie si un utilisateur peut étirer le bouton pendant la personnalisation.|  
|[CMFCToolBarButton::CompareWith](../Topic/CMFCToolBarButton::CompareWith.md)|Compare cette instance à l'objet fourni d' `CMFCToolBarButton` .|  
|[CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md)|Copie les propriétés d'un autre bouton de barre d'outils sur le bouton actuel.|  
|[CMFCToolBarButton::CreateFromOleData](../Topic/CMFCToolBarButton::CreateFromOleData.md)|Crée un objet d' `CMFCToolBarButton` de l'objet fourni d' `COleDataObject` .|  
|`CMFCToolBarButton::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCToolBarButton::EnableWindow](../Topic/CMFCToolBarButton::EnableWindow.md)|Active ou désactive l'entrée de souris et de clavier.|  
|[CMFCToolBarButton::ExportToMenuButton](../Topic/CMFCToolBarButton::ExportToMenuButton.md)|Les copies du texte du bouton de barre d'outils à un menu.|  
|[CMFCToolBarButton::GetClipboardFormat](../Topic/CMFCToolBarButton::GetClipboardFormat.md)|Récupère le format de presse\-papiers global pour l'application.|  
|[CMFCToolBarButton::GetHwnd](../Topic/CMFCToolBarButton::GetHwnd.md)|Récupère le handle de fenêtre associée au bouton de barre d'outils.|  
|[CMFCToolBarButton::GetImage](../Topic/CMFCToolBarButton::GetImage.md)|Récupère l'index d'image du bouton.|  
|[CMFCToolBarButton::GetInvalidateRect](../Topic/CMFCToolBarButton::GetInvalidateRect.md)|Extrait la zone de la zone cliente du bouton qui doit être redessiné.|  
|[CMFCToolBarButton::GetParentWnd](../Topic/CMFCToolBarButton::GetParentWnd.md)|Extrait la fenêtre parente du bouton.|  
|[CMFCToolBarButton::GetProtectedCommands](../Topic/CMFCToolBarButton::GetProtectedCommands.md)|Récupère la liste des commandes que l'utilisateur ne peut pas personnaliser.|  
|[CMFCToolBarButton::GetTextSize](../Topic/CMFCToolBarButton::GetTextSize.md)|Extrait la taille du texte du bouton.|  
|[CMFCToolBarButton::HasFocus](../Topic/CMFCToolBarButton::HasFocus.md)|Détermine si le bouton a le focus d'entrée actuel.|  
|[CMFCToolBarButton::HaveHotBorder](../Topic/CMFCToolBarButton::HaveHotBorder.md)|Détermine si une bordure du bouton s'affiche lorsqu'un utilisateur sélectionne le bouton.|  
|[CMFCToolBarButton::IsDrawImage](../Topic/CMFCToolBarButton::IsDrawImage.md)|Détermine si une image est affichée sur le bouton.|  
|[CMFCToolBarButton::IsDrawText](../Topic/CMFCToolBarButton::IsDrawText.md)|Détermine si une étiquette de texte s'affiche sur le bouton.|  
|[CMFCToolBarButton::IsDroppedDown](../Topic/CMFCToolBarButton::IsDroppedDown.md)|Détermine si le bouton affiche un sous\-menu.|  
|[CMFCToolBarButton::IsEditable](../Topic/CMFCToolBarButton::IsEditable.md)|Détermine si le bouton peut être personnalisé.|  
|[CMFCToolBarButton::IsExtraSize](../Topic/CMFCToolBarButton::IsExtraSize.md)|Détermine si le bouton peut être affiché avec une bordure étendue.|  
|[CMFCToolBarButton::IsFirstInGroup](../Topic/CMFCToolBarButton::IsFirstInGroup.md)|Détermine si le bouton est dans la première position à son groupe de boutons.|  
|[CMFCToolBarButton::IsHidden](../Topic/CMFCToolBarButton::IsHidden.md)|Détermine si le bouton est masqué.|  
|[CMFCToolBarButton::IsHorizontal](../Topic/CMFCToolBarButton::IsHorizontal.md)|Détermine si le bouton se trouve sur une barre d'outils horizontale.|  
|[CMFCToolBarButton::IsLastInGroup](../Topic/CMFCToolBarButton::IsLastInGroup.md)|Spécifie si le bouton est en dernière position à son groupe de boutons.|  
|[CMFCToolBarButton::IsLocked](../Topic/CMFCToolBarButton::IsLocked.md)|Détermine si le bouton est d'une barre d'outils \(non personnalisable\) verrouillée.|  
|[CMFCToolBarButton::IsOwnerOf](../Topic/CMFCToolBarButton::IsOwnerOf.md)|Détermine si le bouton est le propriétaire de le handle de fenêtre fournie.|  
|[CMFCToolBarButton::IsVisible](../Topic/CMFCToolBarButton::IsVisible.md)|Détermine si le bouton de barre d'outils est visible.|  
|[CMFCToolBarButton::IsWindowVisible](../Topic/CMFCToolBarButton::IsWindowVisible.md)|Détermine si le handle de fenêtre sous\-jacente du bouton est visible.|  
|[CMFCToolBarButton::NotifyCommand](../Topic/CMFCToolBarButton::NotifyCommand.md)|Spécifie si le bouton traite le message de [WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) .|  
|[CMFCToolBarButton::OnAddToCustomizePage](../Topic/CMFCToolBarButton::OnAddToCustomizePage.md)|Appelé par l'infrastructure lorsque le bouton est ajouté à une boîte de dialogue **Personnaliser** .|  
|[CMFCToolBarButton::OnBeforeDrag](../Topic/CMFCToolBarButton::OnBeforeDrag.md)|Spécifie si le bouton peut être déplacé.|  
|[CMFCToolBarButton::OnBeforeDrop](../Topic/CMFCToolBarButton::OnBeforeDrop.md)|Spécifie si un utilisateur peut supprimer le bouton sur la barre d'outils cible.|  
|[CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md)|Appelé par l'infrastructure pour calculer la taille du bouton pour le contexte de périphérique et l'état spécifié d'ancrage.|  
|[CMFCToolBarButton::OnCancelMode](../Topic/CMFCToolBarButton::OnCancelMode.md)|Appelé par l'infrastructure pour gérer le message de [WM\_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) .|  
|[CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md)|Appelé par l'infrastructure lorsque le bouton est inséré dans une nouvelle barre d'outils.|  
|[CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton de la souris.|  
|[CMFCToolBarButton::OnClickUp](../Topic/CMFCToolBarButton::OnClickUp.md)|Appelé par l'infrastructure lorsque l'utilisateur relâche le bouton de la souris.|  
|[CMFCToolBarButton::OnContextHelp](../Topic/CMFCToolBarButton::OnContextHelp.md)|Appelé par l'infrastructure lorsque la barre d'outils parent gère un message d' `WM_HELPHITTEST` .|  
|[CMFCToolBarButton::OnCtlColor](../Topic/CMFCToolBarButton::OnCtlColor.md)|Appelé par l'infrastructure lorsque la barre d'outils parent gère un message d' `WM_CTLCOLOR` .|  
|[CMFCToolBarButton::OnCustomizeMenu](../Topic/CMFCToolBarButton::OnCustomizeMenu.md)|Permet au bouton pour modifier le menu fourni lorsque l'application affiche un menu contextuel dans la barre d'outils parente.|  
|[CMFCToolBarButton::OnDblClk](../Topic/CMFCToolBarButton::OnDblClk.md)|Appelé par l'infrastructure lorsque la barre d'outils parent gère un message de [WM\_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) .|  
|[CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md)|Appelé par l'infrastructure pour dessiner le bouton en utilisant des styles et des options spécifiés.|  
|[CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md)|Appelé par l'infrastructure pour dessiner le bouton dans le volet **Commandes** de la boîte de dialogue **Personnaliser** .|  
|[CMFCToolBarButton::OnGetCustomToolTipText](../Topic/CMFCToolBarButton::OnGetCustomToolTipText.md)|Appelé par l'infrastructure pour récupérer le texte personnalisé d'info\-bulle pour le bouton.|  
|[CMFCToolBarButton::OnGlobalFontsChanged](../Topic/CMFCToolBarButton::OnGlobalFontsChanged.md)|Appelé par l'infrastructure lorsque la police globale a changé.|  
|[CMFCToolBarButton::OnMove](../Topic/CMFCToolBarButton::OnMove.md)|Appelé par l'infrastructure lorsque la barre d'outils parent passe.|  
|[CMFCToolBarButton::OnShow](../Topic/CMFCToolBarButton::OnShow.md)|Appelé par l'infrastructure lorsque le bouton devient visible ou invisible.|  
|[CMFCToolBarButton::OnSize](../Topic/CMFCToolBarButton::OnSize.md)|Appelé par l'infrastructure lorsque la barre d'outils parent modifie sa taille ou position et cette modification implique de le bouton de modifier la taille.|  
|[CMFCToolBarButton::OnToolHitTest](../Topic/CMFCToolBarButton::OnToolHitTest.md)|Appelé par l'infrastructure lorsque la barre d'outils parent doit déterminer si un point se trouve dans le rectangle englobant du bouton.|  
|[CMFCToolBarButton::OnUpdateToolTip](../Topic/CMFCToolBarButton::OnUpdateToolTip.md)|Appelé par l'infrastructure lorsque la barre d'outils parent gère son texte d'info\-bulle.|  
|[CMFCToolBarButton::PrepareDrag](../Topic/CMFCToolBarButton::PrepareDrag.md)|Appelé par l'infrastructure lorsque le bouton est sur le point d'exécuter une opération de glisser\-déplacer.|  
|[CMFCToolBarButton::Rect](../Topic/CMFCToolBarButton::Rect.md)|Récupère le rectangle englobant du bouton.|  
|[CMFCToolBarButton::ResetImageToDefault](../Topic/CMFCToolBarButton::ResetImageToDefault.md)|Définit la valeur par défaut l'image associée au bouton.|  
|[CMFCToolBarButton::SaveBarState](../Topic/CMFCToolBarButton::SaveBarState.md)|Enregistre l'état du bouton de barre d'outils.|  
|[CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md)|Lit cet objet d'une archive ou l'écrit dans une archive.  \(Substitutions [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CMFCToolBarButton::SetACCData](../Topic/CMFCToolBarButton::SetACCData.md)|Remplit l'objet fourni d' `CAccessibilityData` avec les données d'accessibilité du bouton de barre d'outils.|  
|[CMFCToolBarButton::SetClipboardFormatName](../Topic/CMFCToolBarButton::SetClipboardFormatName.md)|Renomme le format de presse\-papiers global.|  
|[CMFCToolBarButton::SetImage](../Topic/CMFCToolBarButton::SetImage.md)|Définit l'index d'image du bouton.|  
|[CMFCToolBarButton::SetProtectedCommands](../Topic/CMFCToolBarButton::SetProtectedCommands.md)|Définit la liste des commandes que l'utilisateur ne peut pas personnaliser.|  
|[CMFCToolBarButton::SetRadio](../Topic/CMFCToolBarButton::SetRadio.md)|Appelé par l'infrastructure lorsqu'un bouton modifie son état activé.|  
|[CMFCToolBarButton::SetRect](../Topic/CMFCToolBarButton::SetRect.md)|Définit le rectangle englobant du bouton.|  
|[CMFCToolBarButton::SetStyle](../Topic/CMFCToolBarButton::SetStyle.md)|Définit le style du bouton.|  
|[CMFCToolBarButton::SetVisible](../Topic/CMFCToolBarButton::SetVisible.md)|Spécifie si le bouton est visible.|  
|[CMFCToolBarButton::Show](../Topic/CMFCToolBarButton::Show.md)|Affiche ou masque le bouton.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarButton::m\_bImage](../Topic/CMFCToolBarButton::m_bImage.md)|Spécifie si une image est affichée sur le bouton.|  
|[CMFCToolBarButton::m\_bText](../Topic/CMFCToolBarButton::m_bText.md)|Spécifie si une étiquette de texte s'affiche sur le bouton.|  
|[CMFCToolBarButton::m\_bTextBelow](../Topic/CMFCToolBarButton::m_bTextBelow.md)|Spécifie si l'étiquette de texte s'affiche sous l'image sur le bouton.|  
|[CMFCToolBarButton::m\_bUserButton](../Topic/CMFCToolBarButton::m_bUserButton.md)|Spécifie si le bouton a une image définie par l'utilisateur.|  
|[CMFCToolBarButton::m\_bWholeText](../Topic/CMFCToolBarButton::m_bWholeText.md)|Spécifie si le bouton affiche l'étiquette de texte intégral même s'il ne tient pas dans le rectangle englobant.|  
|[CMFCToolBarButton::m\_bWrap](../Topic/CMFCToolBarButton::m_bWrap.md)|Spécifie si le bouton en regard d'un séparateur est mis sur la ligne suivante.|  
|[CMFCToolBarButton::m\_bWrapText](../Topic/CMFCToolBarButton::m_bWrapText.md)|Spécifie si les étiquettes de texte multilignes sont activées.|  
|[CMFCToolBarButton::m\_nID](../Topic/CMFCToolBarButton::m_nID.md)|l'ID de commande du bouton.|  
|[CMFCToolBarButton::m\_nStyle](../Topic/CMFCToolBarButton::m_nStyle.md)|Le style du bouton.|  
|[CMFCToolBarButton::m\_strText](../Topic/CMFCToolBarButton::m_strText.md)|l'étiquette de texte du bouton.|  
  
## Notes  
 Un objet d' `CMFCToolbarButton` est un contrôle qui réside sur une barre d'outils.  Son comportement ressemble à celui d'un bouton simple.  Vous pouvez assigner une image et une étiquette de texte à cet objet.  Un bouton de barre d'outils peut également avoir un ID de commande  Lorsque l'utilisateur clique sur le bouton de barre d'outils, l'infrastructure exécute la commande que cet ID spécifie.  
  
 En général, les boutons de barre d'outils peuvent être personnalisés : l'utilisateur peut faire glisser des boutons d'une barre d'outils vers un autre, et copier, coller, supprimer, et modifier des étiquettes de texte et des images.  Pour empêcher l'utilisateur de personnaliser la barre d'outils, vous pouvez verrouiller la barre d'outils de deux façons.  L'un ou l'autre a défini la balise d' `bLocked` à `TRUE` lorsque vous appelez [CMFCToolBar::LoadToolBar](../Topic/CMFCToolBar::LoadToolBar.md), ou ajoute l'ID de commande d'un bouton individuel à la liste globale de commandes protégées à l'aide de la méthode de [CMFCToolBarButton::SetProtectedCommands](../Topic/CMFCToolBarButton::SetProtectedCommands.md) .  
  
 `CMFCToolBarButton` objets afficher des images des collections globales d'images de barre d'outils de l'application.  Ces collections sont mises à jour dans la barre d'outils parente, [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md).  Pour plus d'informations, consultez [CMFCToolBarImages Class](../../mfc/reference/cmfctoolbarimages-class.md).  
  
 Lorsque l'utilisateur clique sur un bouton de barre d'outils, sa barre d'outils parente traite le message de la souris et communique les actions appropriées au bouton.  Si le bouton a un ID de commande valide, la barre d'outils parent envoie le message d' `WM_COMMAND` au frame parent.  
  
 La classe d' `CMFCToolBarButton` est la classe de base pour d'autres classes de bouton de barre d'outils, telles que [CMFCToolBarMenuButton Class](../../mfc/reference/cmfctoolbarmenubutton-class.md), [CMFCToolBarEditBoxButton Class](../../mfc/reference/cmfctoolbareditboxbutton-class.md), et [CMFCToolBarComboBoxButton Class](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md).  
  
## Exemple  
 L'exemple suivant montre comment configurer un objet d' `CMFCToolBarButton` en utilisant différentes méthodes dans la classe d' `CMFCToolBarButton` .  L'exemple montre comment activer le clavier et de souris d'entrer, de définir l'index d'image du bouton, de définir le rectangle englobant du bouton, et de rendre le bouton visible.  Cet extrait de code fait partie d' [Exemple de contrôle tab](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_TabControl#1](../../mfc/reference/codesnippet/CPP/cmfctoolbarbutton-class_1.cpp)]  
[!code-cpp[NVC_MFC_TabControl#2](../../mfc/reference/codesnippet/CPP/cmfctoolbarbutton-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
## Configuration requise  
 **en\-tête :** afxtoolbarbutton.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarImages Class](../../mfc/reference/cmfctoolbarimages-class.md)   
 [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md)   
 [CMFCToolBarButton::NotifyCommand](../Topic/CMFCToolBarButton::NotifyCommand.md)