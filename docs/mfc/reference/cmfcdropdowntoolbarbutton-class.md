---
title: "CMFCDropDownToolbarButton Class | Microsoft Docs"
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
  - "CMFCDropDownToolbarButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDropDownToolbarButton class"
  - "OnCancelMode method"
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
caps.latest.revision: 31
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDropDownToolbarButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un type de bouton de barre d'outils qui se comporte comme un bouton normal lorsqu'un utilisateur clique dessus.  Toutefois, il ouvre une barre d'outils de liste déroulante \([CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md) si l'utilisateur appuie sur et contient le bouton de barre d'outils.  
  
## Syntaxe  
  
```  
class CMFCDropDownToolbarButton : public CMFCToolBarButton  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../Topic/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton.md)|Construit un objet `CMFCDropDownToolbarButton`.|  
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCDropDownToolbarButton::CopyFrom](../Topic/CMFCDropDownToolbarButton::CopyFrom.md)|Copie les propriétés d'un autre bouton de barre d'outils sur le bouton actuel.  \(Substitutions [CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md).\)|  
|`CMFCDropDownToolbarButton::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCDropDownToolbarButton::DropDownToolbar](../Topic/CMFCDropDownToolbarButton::DropDownToolbar.md)|Ouvre une barre d'outils déroulante.|  
|[CMFCDropDownToolbarButton::ExportToMenuButton](../Topic/CMFCDropDownToolbarButton::ExportToMenuButton.md)|Les copies du texte du bouton de barre d'outils à un menu.  \(Substitutions [CMFCToolBarButton::ExportToMenuButton](../Topic/CMFCToolBarButton::ExportToMenuButton.md).\)|  
|[CMFCDropDownToolbarButton::GetDropDownToolBar](../Topic/CMFCDropDownToolbarButton::GetDropDownToolBar.md)|Extrait la barre d'outils déroulante associée au bouton.|  
|`CMFCDropDownToolbarButton::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCDropDownToolbarButton::IsDropDown](../Topic/CMFCDropDownToolbarButton::IsDropDown.md)|Détermine si la barre d'outils déroulante est actuellement ouverte.|  
|[CMFCDropDownToolbarButton::IsExtraSize](../Topic/CMFCDropDownToolbarButton::IsExtraSize.md)|Détermine si le bouton peut être affiché avec une bordure étendue.  \(Substitutions [CMFCToolBarButton::IsExtraSize](../Topic/CMFCToolBarButton::IsExtraSize.md).\)|  
|[CMFCDropDownToolbarButton::OnCalculateSize](../Topic/CMFCDropDownToolbarButton::OnCalculateSize.md)|Appelé par l'infrastructure pour calculer la taille du bouton pour le contexte de périphérique et l'état spécifié d'ancrage.  \(Substitutions [CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md).\)|  
|`CMFCDropDownToolbarButton::OnCancelMode`|Appelé par l'infrastructure pour gérer le message de [WM\_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) .  \(Substitutions `CMCToolBarButton::OnCancelMode`.\)|  
|[CMFCDropDownToolbarButton::OnChangeParentWnd](../Topic/CMFCDropDownToolbarButton::OnChangeParentWnd.md)|Appelé par l'infrastructure lorsque le bouton est inséré dans une nouvelle barre d'outils.  \(Substitutions [CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md).\)|  
|[CMFCDropDownToolbarButton::OnClick](../Topic/CMFCDropDownToolbarButton::OnClick.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton de la souris.  \(Substitutions [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md).\)|  
|[CMFCDropDownToolbarButton::OnClickUp](../Topic/CMFCDropDownToolbarButton::OnClickUp.md)|Appelé par l'infrastructure lorsque l'utilisateur relâche le bouton de la souris.  \(Substitutions [CMFCToolBarButton::OnClickUp](../Topic/CMFCToolBarButton::OnClickUp.md).\)|  
|[CMFCDropDownToolbarButton::OnContextHelp](../Topic/CMFCDropDownToolbarButton::OnContextHelp.md)|Appelé par l'infrastructure lorsque la barre d'outils parent gère un message d' `WM_HELPHITTEST` .  \(Substitutions [CMFCToolBarButton::OnContextHelp](../Topic/CMFCToolBarButton::OnContextHelp.md).\)|  
|[CMFCDropDownToolbarButton::OnCustomizeMenu](../Topic/CMFCDropDownToolbarButton::OnCustomizeMenu.md)|Modifie le menu fourni lorsque l'application affiche un menu contextuel dans la barre d'outils parente.  \(Substitutions [CMFCToolBarButton::OnCustomizeMenu](../Topic/CMFCToolBarButton::OnCustomizeMenu.md).\)|  
|[CMFCDropDownToolbarButton::OnDraw](../Topic/CMFCDropDownToolbarButton::OnDraw.md)|Appelé par l'infrastructure pour dessiner le bouton en utilisant des styles et des options spécifiés.  \(Substitutions [CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md).\)|  
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](../Topic/CMFCDropDownToolbarButton::OnDrawOnCustomizeList.md)|Appelé par l'infrastructure pour dessiner le bouton dans le volet **Commandes** de la boîte de dialogue **Personnaliser** .  \(Substitutions [CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md).\)|  
|[CMFCDropDownToolbarButton::Serialize](../Topic/CMFCDropDownToolbarButton::Serialize.md)|Lit cet objet d'une archive ou l'écrit dans une archive.  \(Substitutions [CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md).\)|  
|[CMFCDropDownToolbarButton::SetDefaultCommand](../Topic/CMFCDropDownToolbarButton::SetDefaultCommand.md)|Définit la commande par défaut que l'infrastructure utilise lorsqu'un utilisateur clique sur le bouton.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCDropDownToolbarButton::m\_uiShowBarDelay](../Topic/CMFCDropDownToolbarButton::m_uiShowBarDelay.md)|Spécifie la durée qu'un utilisateur doit contenir le bouton de la souris avant la barre d'outils déroulante s'affiche.|  
  
## Notes  
 `CMFCDropDownToolBarButton` diffère d'un bouton simple car il a une petite flèche dans le coin inférieur droit du bouton.  Une fois que l'utilisateur sélectionne un bouton de la barre d'outils déroulante, l'infrastructure affiche son icône sur le bouton de barre d'outils de niveau supérieur \(bouton avec la petite flèche dans le coin inférieur droit\).  
  
 Pour plus d'informations sur la manière d'implémenter une barre d'outils déroulante, consultez [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md).  
  
 L'objet d' `CMFCDropDownToolBarButton` peut être exporté vers un objet de [CMFCToolBarMenuButton Class](../../mfc/reference/cmfctoolbarmenubutton-class.md) et afficher un bouton de menu à un menu contextuel.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)  
  
## Configuration requise  
 **en\-tête :** afxdropdowntoolbar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarMenuButton Class](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [Procédure pas à pas : placement de contrôles dans les barres d'outils](../../mfc/walkthrough-putting-controls-on-toolbars.md)