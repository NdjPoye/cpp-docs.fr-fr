---
title: "CMFCOutlookBarTabCtrl Class | Microsoft Docs"
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
  - "CMFCOutlookBarTabCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCOutlookBarTabCtrl class"
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
caps.latest.revision: 26
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCOutlookBarTabCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un contrôle onglet qui a l'aspect visuel **Volet de navigation** dans Microsoft Outlook.  
  
## Syntaxe  
  
```  
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|Constructeur par défaut.|  
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCOutlookBarTabCtrl::AddControl](../Topic/CMFCOutlookBarTabCtrl::AddControl.md)|Ajoute un contrôle Windows comme un nouvel onglet dans la barre Outlook.|  
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|Appelé par l'infrastructure pour déterminer les dimensions de la zone d'édition qui apparaît lorsqu'un utilisateur renomme une table.  \(Substitutions `CMFCBaseTabCtrl::CalcRectEdit`.\)|  
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](../Topic/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons.md)|Appelés par l'infrastructure pendant les opérations de dimensionnement pour déterminer si moins boutons de la page d'onglets de barre Outlook peuvent être affichés que sont actuellement visible.|  
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](../Topic/CMFCOutlookBarTabCtrl::CanShowMorePageButtons.md)|Appelés par l'infrastructure pendant les opérations de dimensionnement pour déterminer si plus de boutons de la page d'onglets de barre Outlook peuvent être affichés que sont actuellement visible.|  
|[CMFCOutlookBarTabCtrl::Create](../Topic/CMFCOutlookBarTabCtrl::Create.md)|Crée le contrôle onglet de barre Outlook.|  
|`CMFCOutlookBarTabCtrl::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCOutlookBarTabCtrl::EnableAnimation](../Topic/CMFCOutlookBarTabCtrl::EnableAnimation.md)|Spécifie si l'animation qui se produit pendant le basculer entre les onglets actif est activée.|  
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](../Topic/CMFCOutlookBarTabCtrl::EnableInPlaceEdit.md)|Spécifie si un utilisateur peut modifier les étiquettes de texte sur les boutons de l'onglet de la barre Outlook.  \(Substitutions [CMFCBaseTabCtrl::EnableInPlaceEdit](../Topic/CMFCBaseTabCtrl::EnableInPlaceEdit.md).\)|  
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](../Topic/CMFCOutlookBarTabCtrl::EnableScrollButtons.md)|Appelé par l'infrastructure pour activer des boutons qui permettent à l'utilisateur de faire défiler les boutons dans le volet de barre Outlook.|  
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|Identifie le volet qui contient un point spécifié.  \(Substitutions [CMFCBaseTabCtrl::FindTargetWnd](../Topic/CMFCBaseTabCtrl::FindTargetWnd.md).\)|  
|[CMFCOutlookBarTabCtrl::GetBorderSize](../Topic/CMFCOutlookBarTabCtrl::GetBorderSize.md)|Retourne la taille de la bordure du contrôle onglet Outlook.|  
|`CMFCOutlookBarTabCtrl::GetTabArea`|Extrait la taille et la position du domaine d'onglet de contrôle tab.  \(Substitutions [CMFCBaseTabCtrl::GetTabArea](../Topic/CMFCBaseTabCtrl::GetTabArea.md).\)|  
|`CMFCOutlookBarTabCtrl::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](../Topic/CMFCOutlookBarTabCtrl::GetVisiblePageButtons.md)||  
|[CMFCOutlookBarTabCtrl::IsAnimation](../Topic/CMFCOutlookBarTabCtrl::IsAnimation.md)|Détermine si l'animation qui se produit pendant le basculer entre les onglets actif est activée.|  
|[CMFCOutlookBarTabCtrl::IsMode2003](../Topic/CMFCOutlookBarTabCtrl::IsMode2003.md)|Détermine si le contrôle onglet de barre Outlook est dans un état qui émule Microsoft Outlook 2003.|  
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|Détermine si un point se trouve à l'intérieur de la zone de l'onglet.  \(Substitutions [CMFCBaseTabCtrl::IsPtInTabArea](../Topic/CMFCBaseTabCtrl::IsPtInTabArea.md).\)|  
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|Détermine si un onglet est détachable.  \(Substitutions [CMFCBaseTabCtrl::IsTabDetachable](../Topic/CMFCBaseTabCtrl::IsTabDetachable.md).\)|  
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|Appelé par l'infrastructure lorsqu'un onglet est inséré ou supprimé.  \(Substitutions `CMFCBaseTabCtrl::OnChangeTabs`.\)|  
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](../Topic/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons.md)|Appelé par l'infrastructure pour réduire le nombre de boutons de la page d'onglets qui sont visibles.|  
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](../Topic/CMFCOutlookBarTabCtrl::OnShowMorePageButtons.md)|Appelé par l'infrastructure pour augmenter le nombre de boutons de la page d'onglets qui sont visibles.|  
|[CMFCOutlookBarTabCtrl::OnShowOptions](../Topic/CMFCOutlookBarTabCtrl::OnShowOptions.md)|Affiche la boîte de dialogue **Options du volet de navigation** .|  
|`CMFCOutlookBarTabCtrl::RecalcLayout`|Recalcule la disposition interne du contrôle onglet.  \(Substitutions [CMFCBaseTabCtrl::RecalcLayout](../Topic/CMFCBaseTabCtrl::RecalcLayout.md).\)|  
|[CMFCOutlookBarTabCtrl::SetActiveTab](../Topic/CMFCOutlookBarTabCtrl::SetActiveTab.md)|Définit l'onglet actif.  \(Substitutions [CMFCBaseTabCtrl::SetActiveTab](../Topic/CMFCBaseTabCtrl::SetActiveTab.md).\)|  
|[CMFCOutlookBarTabCtrl::SetBorderSize](../Topic/CMFCOutlookBarTabCtrl::SetBorderSize.md)|Définit la taille de la bordure du contrôle onglet Outlook.|  
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](../Topic/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign.md)|Définit l'alignement des étiquettes de texte sur les boutons de l'onglet de la barre Outlook.|  
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](../Topic/CMFCOutlookBarTabCtrl::SetToolbarImageList.md)|Définit la bitmap qui contient les icônes affichées en bas de la barre Outlook en mode Outlook 2003 \(consultez [CMFCOutlookBar, Classe](../../mfc/reference/cmfcoutlookbar-class.md)\).|  
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](../Topic/CMFCOutlookBarTabCtrl::SetVisiblePageButtons.md)||  
  
## Notes  
 Pour créer défendez Outlook qui assure la prise en charge d'ancrage, utilisez un objet d' `CMFCOutlookBar` pour héberger le contrôle onglet de barre Outlook.  Pour plus d'informations, consultez [CMFCOutlookBar, Classe](../../mfc/reference/cmfcoutlookbar-class.md).  
  
## Exemple  
 L'exemple suivant montre comment initialiser un objet d' `CMFCOutlookBarTabCtrl` et utiliser différentes méthodes dans `CMFCOutlookBarTabCtrl` classe.  L'exemple montre comment activer la modification sur place de l'étiquette de texte sur les boutons de la page d'onglets de la barre Outlook, permettent l'animation, permettent les handles de défilement qui permettent à l'utilisateur de parcourir les boutons dans le volet de barre Outlook, de définir la taille de la bordure du contrôle onglet Outlook, et de définir l'alignement des étiquettes de texte sur les boutons de l'onglet de la barre Outlook.  Cet extrait de code fait partie d' [Exemple de démonstration d'Outlook](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookDemo#1](../../mfc/reference/codesnippet/CPP/cmfcoutlookbartabctrl-class_1.cpp)]  
[!code-cpp[NVC_MFC_OutlookDemo#2](../../mfc/reference/codesnippet/CPP/cmfcoutlookbartabctrl-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)  
  
## Configuration requise  
 **en\-tête :** afxoutlookbartabctrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md)   
 [CMFCOutlookBar, Classe](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md)