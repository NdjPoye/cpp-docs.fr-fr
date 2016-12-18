---
title: "CMFCToolBarMenuButton Class | Microsoft Docs"
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
  - "CMFCToolBarMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarMenuButton class"
ms.assetid: cfa50176-7e4b-4527-9904-86a1b48fc1bc
caps.latest.revision: 31
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarMenuButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un bouton de barre d'outils qui contient un menu contextuel.  
  
## Syntaxe  
  
```  
class CMFCToolBarMenuButton : public CMFCToolBarButton  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarMenuButton::CMFCToolBarMenuButton](../Topic/CMFCToolBarMenuButton::CMFCToolBarMenuButton.md)|Construit un objet `CMFCToolBarMenuButton`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarMenuButton::CompareWith](../Topic/CMFCToolBarMenuButton::CompareWith.md)|Compare cette instance à l'objet fourni d' `CMFCToolBarButton` .  \(Substitutions [CMFCToolBarButton::CompareWith](../Topic/CMFCToolBarButton::CompareWith.md).\)|  
|[CMFCToolBarMenuButton::CopyFrom](../Topic/CMFCToolBarMenuButton::CopyFrom.md)|Copie les propriétés d'un autre bouton de barre d'outils sur le bouton actuel.  \(Substitutions [CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md).\)|  
|[CMFCToolBarMenuButton::CreateFromMenu](../Topic/CMFCToolBarMenuButton::CreateFromMenu.md)|Initialise le menu de la barre d'outils d'un handle de menu de windows.|  
|[CMFCToolBarMenuButton::CreateMenu](../Topic/CMFCToolBarMenuButton::CreateMenu.md)|Crée un menu de windows qui inclut des commandes dans le menu de la barre d'outils.  Retourne un handle vers le menu de windows.|  
|[CMFCToolBarMenuButton::CreatePopupMenu](../Topic/CMFCToolBarMenuButton::CreatePopupMenu.md)|Crée un objet de menu contextuel \([CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)\) pour afficher le menu de la barre d'outils.|  
|[CMFCToolBarMenuButton::EnableQuickCustomize](../Topic/CMFCToolBarMenuButton::EnableQuickCustomize.md)||  
|[CMFCToolBarMenuButton::GetCommands](../Topic/CMFCToolBarMenuButton::GetCommands.md)|Fournit l'accès en lecture seule à la liste des commandes dans le menu de la barre d'outils.|  
|[CMFCToolBarMenuButton::GetImageRect](../Topic/CMFCToolBarMenuButton::GetImageRect.md)|Récupère le rectangle englobant de l'image du bouton.|  
|[CMFCToolBarMenuButton::GetPaletteRows](../Topic/CMFCToolBarMenuButton::GetPaletteRows.md)|Retourne le nombre de lignes dans le menu contextuel quand le menu est en mode de la palette.|  
|[CMFCToolBarMenuButton::GetPopupMenu](../Topic/CMFCToolBarMenuButton::GetPopupMenu.md)|Retourne un pointeur vers l'objet de menu contextuel associé au bouton.|  
|[CMFCToolBarMenuButton::HasButton](../Topic/CMFCToolBarMenuButton::HasButton.md)||  
|[CMFCToolBarMenuButton::HaveHotBorder](../Topic/CMFCToolBarMenuButton::HaveHotBorder.md)|Détermine si une bordure du bouton s'affiche lorsqu'un utilisateur sélectionne le bouton.  \(Substitutions [CMFCToolBarButton::HaveHotBorder](../Topic/CMFCToolBarButton::HaveHotBorder.md).\)|  
|[CMFCToolBarMenuButton::IsBorder](../Topic/CMFCToolBarMenuButton::IsBorder.md)||  
|[CMFCToolBarMenuButton::IsClickedOnMenu](../Topic/CMFCToolBarMenuButton::IsClickedOnMenu.md)||  
|[CMFCToolBarMenuButton::IsDroppedDown](../Topic/CMFCToolBarMenuButton::IsDroppedDown.md)|Détermine si le menu contextuel s'affiche.|  
|[CMFCToolBarMenuButton::IsEmptyMenuAllowed](../Topic/CMFCToolBarMenuButton::IsEmptyMenuAllowed.md)|Appelé par l'infrastructure pour déterminer si un utilisateur peut ouvrir un sous\-menu de l'élément de menu sélectionné.|  
|[CMFCToolBarMenuButton::IsExclusive](../Topic/CMFCToolBarMenuButton::IsExclusive.md)|Détermine si le bouton est en mode exclusif, c. autrement dit., si le menu contextuel reste ouvert même lorsque l'utilisateur déplace le pointeur sur une barre d'outils ou d'un bouton.|  
|[CMFCToolBarMenuButton::IsMenuPaletteMode](../Topic/CMFCToolBarMenuButton::IsMenuPaletteMode.md)|Détermine si le menu contextuel est en mode de la palette.|  
|[CMFCToolBarMenuButton::IsQuickMode](../Topic/CMFCToolBarMenuButton::IsQuickMode.md)||  
|[CMFCToolBarMenuButton::IsTearOffMenu](../Topic/CMFCToolBarMenuButton::IsTearOffMenu.md)|Détermine si le menu contextuel a une barre d'arrachement.|  
|[CMFCToolBarMenuButton::OnAfterCreatePopupMenu](../Topic/CMFCToolBarMenuButton::OnAfterCreatePopupMenu.md)||  
|[CMFCToolBarMenuButton::OnBeforeDrag](../Topic/CMFCToolBarMenuButton::OnBeforeDrag.md)|Spécifie si le bouton peut être déplacé.  \(Substitutions [CMFCToolBarButton::OnBeforeDrag](../Topic/CMFCToolBarButton::OnBeforeDrag.md).\)|  
|[CMFCToolBarMenuButton::OnCalculateSize](../Topic/CMFCToolBarMenuButton::OnCalculateSize.md)|Appelé par l'infrastructure pour calculer la taille du bouton pour le contexte de périphérique et l'état spécifié d'ancrage.  \(Substitutions [CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md).\)|  
|[CMFCToolBarMenuButton::OnCancelMode](../Topic/CMFCToolBarMenuButton::OnCancelMode.md)|Appelé par l'infrastructure pour gérer le message de [WM\_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) .  \(Substitutions [CMFCToolBarButton::OnCancelMode](../Topic/CMFCToolBarButton::OnCancelMode.md).\)|  
|[CMFCToolBarMenuButton::OnChangeParentWnd](../Topic/CMFCToolBarMenuButton::OnChangeParentWnd.md)|Appelé par l'infrastructure lorsque le bouton est inséré dans une nouvelle barre d'outils.  \(Substitutions [CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md).\)|  
|[CMFCToolBarMenuButton::OnClick](../Topic/CMFCToolBarMenuButton::OnClick.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton de la souris.  \(Substitutions [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md).\)|  
|[CMFCToolBarMenuButton::OnClickMenuItem](../Topic/CMFCToolBarMenuButton::OnClickMenuItem.md)|Appelé par l'infrastructure lorsque l'utilisateur sélectionne un élément dans le menu contextuel.|  
|[CMFCToolBarMenuButton::OnContextHelp](../Topic/CMFCToolBarMenuButton::OnContextHelp.md)|Appelé par l'infrastructure lorsque la barre d'outils parent gère un message d' `WM_HELPHITTEST` .  \(Substitutions [CMFCToolBarButton::OnContextHelp](../Topic/CMFCToolBarButton::OnContextHelp.md).\)|  
|[CMFCToolBarMenuButton::OnDraw](../Topic/CMFCToolBarMenuButton::OnDraw.md)|Appelé par l'infrastructure pour dessiner le bouton en utilisant des styles et des options spécifiés.  \(Substitutions [CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md).\)|  
|[CMFCToolBarMenuButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarMenuButton::OnDrawOnCustomizeList.md)|Appelé par l'infrastructure pour dessiner le bouton dans le volet **Commandes** de la boîte de dialogue **Personnaliser** .  \(Substitutions [CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md).\)|  
|[CMFCToolBarMenuButton::OpenPopupMenu](../Topic/CMFCToolBarMenuButton::OpenPopupMenu.md)|Appelé par l'infrastructure lorsque l'utilisateur ouvre le menu contextuel.|  
|[CMFCToolBarMenuButton::ResetImageToDefault](../Topic/CMFCToolBarMenuButton::ResetImageToDefault.md)|Définit la valeur par défaut l'image associée au bouton.  \(Substitutions [CMFCToolBarButton::ResetImageToDefault](../Topic/CMFCToolBarButton::ResetImageToDefault.md).\)|  
|[CMFCToolBarMenuButton::SaveBarState](../Topic/CMFCToolBarMenuButton::SaveBarState.md)|Enregistre l'état du bouton de barre d'outils.  \(Substitutions [CMFCToolBarButton::SaveBarState](../Topic/CMFCToolBarButton::SaveBarState.md).\)|  
|[CMFCToolBarMenuButton::Serialize](../Topic/CMFCToolBarMenuButton::Serialize.md)|Lit cet objet d'une archive ou l'écrit dans une archive.  \(Substitutions [CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md).\)|  
|[CMFCToolBarMenuButton::SetACCData](../Topic/CMFCToolBarMenuButton::SetACCData.md)|Remplit l'objet fourni d' `CAccessibilityData` avec les données d'accessibilité du bouton de barre d'outils.  \(Substitutions [CMFCToolBarButton::SetACCData](../Topic/CMFCToolBarButton::SetACCData.md).\)|  
|[CMFCToolBarMenuButton::SetMenuOnly](../Topic/CMFCToolBarMenuButton::SetMenuOnly.md)|Spécifie si le bouton peut être ajouté à une barre d'outils.|  
|[CMFCToolBarMenuButton::SetMenuPaletteMode](../Topic/CMFCToolBarMenuButton::SetMenuPaletteMode.md)|Spécifie si le menu contextuel est en mode de la palette.|  
|[CMFCToolBarMenuButton::SetMessageWnd](../Topic/CMFCToolBarMenuButton::SetMessageWnd.md)||  
|[CMFCToolBarMenuButton::SetRadio](../Topic/CMFCToolBarMenuButton::SetRadio.md)|Force le bouton de menu dans la barre d'outils pour afficher une icône qui indique qu'elle est sélectionnée.|  
|[CMFCToolBarMenuButton::SetTearOff](../Topic/CMFCToolBarMenuButton::SetTearOff.md)|Spécifie un ID de barre d'arrachement pour le menu contextuel.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarMenuButton::DrawDocumentIcon](../Topic/CMFCToolBarMenuButton::DrawDocumentIcon.md)|Dessine une icône sur le bouton de menu.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarMenuButton::m\_bAlwaysCallOwnerDraw](../Topic/CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw.md)|Si `TRUE`, l'infrastructure appelle toujours [CFrameWndEx::OnDrawMenuImage](../Topic/CFrameWndEx::OnDrawMenuImage.md) lorsqu'un clic est dessiné.|  
  
## Notes  
 `CMFCToolBarMenuButton` peut apparaître menu, élément de menu qui contient un sous\-menu, un bouton qui exécute une commande ou affiche un menu, ou bouton qui affiche un seul menu.  Vous déterminez le comportement et l'apparence du bouton de menu en spécifiant des paramètres tels que l'image, du texte, du handle de menu, et l'ID de commande qui est associé au bouton dans le constructeur `CMFCToolbarMenuButton::CMFCToolbarMenuButton`.  
  
 Une classe personnalisée dérivée de la classe d' `CMFCToolbarMenuButton` doit utiliser la macro de [DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md) .  La macro de [DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md) génère une erreur lorsque l'application se ferme.  
  
## Exemple  
 L'exemple suivant montre comment configurer un objet d' `CMFCToolBarMenuButton` .  Le code montre comment spécifier le menu déroulant est en mode de la palette, et spécifier l'ID de la barre d'arrachement qui est créée lorsque l'utilisateur fait glisser le bouton de menu en fonction de la barre de menus.  Cet extrait de code fait partie d' [Exemple de protection de Word](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#10](../../mfc/reference/codesnippet/CPP/cmfctoolbarmenubutton-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
## Configuration requise  
 **en\-tête :** afxtoolbarmenubutton.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)