---
title: "CTreeCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTreeCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl class"
  - "directory lists"
  - "file lists [C++]"
  - "tree view controls"
ms.assetid: 96e20031-6161-4143-8c12-8d1816c66d90
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTreeCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités du contrôle arborescence communs windows.  
  
## Syntaxe  
  
```  
class CTreeCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CTreeCtrl::CTreeCtrl](../Topic/CTreeCtrl::CTreeCtrl.md)|Construit un objet `CTreeCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CTreeCtrl::Create](../Topic/CTreeCtrl::Create.md)|Crée un contrôle arborescence et l'attache à un objet d' `CTreeCtrl` .|  
|[CTreeCtrl::CreateDragImage](../Topic/CTreeCtrl::CreateDragImage.md)|Crée une bitmap glissante pour l'élément d'arborescence spécifié.|  
|[CTreeCtrl::CreateEx](../Topic/CTreeCtrl::CreateEx.md)|Crée un contrôle d'arborescence avec les styles étendus par windows spécifiées et l'attache à un objet d' `CTreeCtrl` .|  
|[CTreeCtrl::DeleteAllItems](../Topic/CTreeCtrl::DeleteAllItems.md)|Supprime tous les éléments dans un contrôle arborescence.|  
|[CTreeCtrl::DeleteItem](../Topic/CTreeCtrl::DeleteItem.md)|Supprime un nouvel élément dans un contrôle arborescence.|  
|[CTreeCtrl::EditLabel](../Topic/CTreeCtrl::EditLabel.md)|Modifie un élément d'arborescence spécifié sur place.|  
|[CTreeCtrl::EndEditLabelNow](../Topic/CTreeCtrl::EndEditLabelNow.md)|Annule la modification sur l'étiquette d'un élément d'arborescence dans le contrôle arborescence actuel.|  
|[CTreeCtrl::EnsureVisible](../Topic/CTreeCtrl::EnsureVisible.md)|Garantit qu'un élément d'arborescence est visible dans le contrôle arborescence.|  
|[CTreeCtrl::Expand](../Topic/CTreeCtrl::Expand.md)|Grandit, ou les opérations en virgule flottante, les éléments enfants de l'élément d'arborescence spécifié.|  
|[CTreeCtrl::GetBkColor](../Topic/CTreeCtrl::GetBkColor.md)|Extrait la couleur d'arrière\-plan du contrôle.|  
|[CTreeCtrl::GetCheck](../Topic/CTreeCtrl::GetCheck.md)|Récupère l'état d'activation d'un élément de contrôle d'arborescence.|  
|[CTreeCtrl::GetChildItem](../Topic/CTreeCtrl::GetChildItem.md)|Extrait l'enfant d'un élément d'arborescence spécifié.|  
|[CTreeCtrl::GetCount](../Topic/CTreeCtrl::GetCount.md)|Récupère le nombre d'éléments d'arborescence associés à un contrôle arborescence.|  
|[CTreeCtrl::GetDropHilightItem](../Topic/CTreeCtrl::GetDropHilightItem.md)|Extrait la cible d'une opération de glisser\-déplacer.|  
|[CTreeCtrl::GetEditControl](../Topic/CTreeCtrl::GetEditControl.md)|Récupère le handle du contrôle d'édition utilisé pour modifier l'élément d'arborescence spécifié.|  
|[CTreeCtrl::GetExtendedStyle](../Topic/CTreeCtrl::GetExtendedStyle.md)|Récupère les styles étendus que le contrôle arborescence utilise actuellement.|  
|[CTreeCtrl::GetFirstVisibleItem](../Topic/CTreeCtrl::GetFirstVisibleItem.md)|Récupère le premier élément visible de l'élément d'arborescence spécifié.|  
|[CTreeCtrl::GetImageList](../Topic/CTreeCtrl::GetImageList.md)|Récupère le handle de la liste d'images associée à un contrôle arborescence.|  
|[CTreeCtrl::GetIndent](../Topic/CTreeCtrl::GetIndent.md)|Récupère l'offset \(en pixels\) d'un élément d'arborescence de son parent.|  
|[CTreeCtrl::GetInsertMarkColor](../Topic/CTreeCtrl::GetInsertMarkColor.md)|Extrait la couleur utilisée pour dessiner la marque d'insertion de l'arborescence.|  
|[CTreeCtrl::GetItem](../Topic/CTreeCtrl::GetItem.md)|Récupère les attributs d'un élément d'arborescence spécifié.|  
|[CTreeCtrl::GetItemData](../Topic/CTreeCtrl::GetItemData.md)|Retourne la valeur spécifique à l'application de 32 bits associé à un élément.|  
|[CTreeCtrl::GetItemExpandedImageIndex](../Topic/CTreeCtrl::GetItemExpandedImageIndex.md)|Extrait l'index de l'image à afficher lorsque l'élément spécifié du contrôle arborescence actuel se trouve dans l'état développé.|  
|[CTreeCtrl::GetItemHeight](../Topic/CTreeCtrl::GetItemHeight.md)|Extrait la hauteur actuelle des éléments d'arborescence.|  
|[CTreeCtrl::GetItemImage](../Topic/CTreeCtrl::GetItemImage.md)|Récupère les images associées à un élément.|  
|[CTreeCtrl::GetItemPartRect](../Topic/CTreeCtrl::GetItemPartRect.md)|Récupère le rectangle englobant d'une partie spécifique d'un élément spécifié dans le contrôle arborescence actuel.|  
|[CTreeCtrl::GetItemRect](../Topic/CTreeCtrl::GetItemRect.md)|Récupère le rectangle englobant d'un élément d'arborescence.|  
|[CTreeCtrl::GetItemState](../Topic/CTreeCtrl::GetItemState.md)|Retourne l'état d'un élément.|  
|[CTreeCtrl::GetItemStateEx](../Topic/CTreeCtrl::GetItemStateEx.md)|Récupère l'état étendue de l'élément spécifié dans le contrôle arborescence actuel.|  
|[CTreeCtrl::GetItemText](../Topic/CTreeCtrl::GetItemText.md)|Retourne le texte d'un élément.|  
|[CTreeCtrl::GetLastVisibleItem](../Topic/CTreeCtrl::GetLastVisibleItem.md)|Récupère le dernier élément développé dans le contrôle arborescence actuel.|  
|[CTreeCtrl::GetLineColor](../Topic/CTreeCtrl::GetLineColor.md)|Extrait la couleur de ligne active du contrôle arborescence.|  
|[CTreeCtrl::GetNextItem](../Topic/CTreeCtrl::GetNextItem.md)|Extrait l'élément d'arborescence qui correspond à une relation spécifiée.|  
|[CTreeCtrl::GetNextSiblingItem](../Topic/CTreeCtrl::GetNextSiblingItem.md)|Récupère le prochain frères de l'élément d'arborescence spécifié.|  
|[CTreeCtrl::GetNextVisibleItem](../Topic/CTreeCtrl::GetNextVisibleItem.md)|Extrait l'élément visible de l'élément d'arborescence spécifié.|  
|[CTreeCtrl::GetParentItem](../Topic/CTreeCtrl::GetParentItem.md)|Récupère le parent de l'élément d'arborescence spécifié.|  
|[CTreeCtrl::GetPrevSiblingItem](../Topic/CTreeCtrl::GetPrevSiblingItem.md)|Récupère le frère précédent de l'élément d'arborescence spécifié.|  
|[CTreeCtrl::GetPrevVisibleItem](../Topic/CTreeCtrl::GetPrevVisibleItem.md)|Récupère l'élément visible précédent de l'élément d'arborescence spécifié.|  
|[CTreeCtrl::GetRootItem](../Topic/CTreeCtrl::GetRootItem.md)|Extrait la racine de l'élément d'arborescence spécifié.|  
|[CTreeCtrl::GetScrollTime](../Topic/CTreeCtrl::GetScrollTime.md)|Extrait la durée de défilement maximale du contrôle arborescence.|  
|[CTreeCtrl::GetSelectedCount](../Topic/CTreeCtrl::GetSelectedCount.md)|Récupère le nombre d'éléments sélectionnés dans le contrôle arborescence actuel.|  
|[CTreeCtrl::GetSelectedItem](../Topic/CTreeCtrl::GetSelectedItem.md)|Récupère l'élément d'arborescence actuellement sélectionné.|  
|[CTreeCtrl::GetTextColor](../Topic/CTreeCtrl::GetTextColor.md)|Extrait la couleur actuelle de texte du contrôle.|  
|[CTreeCtrl::GetToolTips](../Topic/CTreeCtrl::GetToolTips.md)|Récupère le handle au contrôle d'info\-bulle enfant utilisé par un contrôle arborescence.|  
|[CTreeCtrl::GetVisibleCount](../Topic/CTreeCtrl::GetVisibleCount.md)|Récupère le nombre d'éléments visibles d'arborescence associés à un contrôle arborescence.|  
|[CTreeCtrl::HitTest](../Topic/CTreeCtrl::HitTest.md)|Retourne la position actuelle du curseur en rapport avec l'objet d' `CTreeCtrl` .|  
|[CTreeCtrl::InsertItem](../Topic/CTreeCtrl::InsertItem.md)|Insère un nouvel élément dans un contrôle arborescence.|  
|[CTreeCtrl::ItemHasChildren](../Topic/CTreeCtrl::ItemHasChildren.md)|Retourne une valeur différente de zéro si l'élément spécifié a des éléments enfants.|  
|[CTreeCtrl::MapAccIdToItem](../Topic/CTreeCtrl::MapAccIdToItem.md)|Mappe l'identificateur spécifié d'accessibilité au handle à un élément d'arborescence dans le contrôle arborescence actuel.|  
|[CTreeCtrl::MapItemToAccID](../Topic/CTreeCtrl::MapItemToAccID.md)|Mappe le handle spécifié à un élément d'arborescence dans le contrôle arborescence actuel à un identificateur d'accessibilité.|  
|[CTreeCtrl::Select](../Topic/CTreeCtrl::Select.md)|Sélectionne, défile dans la vue, ou redessine un élément d'arborescence spécifié.|  
|[CTreeCtrl::SelectDropTarget](../Topic/CTreeCtrl::SelectDropTarget.md)|Redessine l'élément d'arborescence comme cible d'une opération de glisser\-déplacer.|  
|[CTreeCtrl::SelectItem](../Topic/CTreeCtrl::SelectItem.md)|Sélectionne un élément d'arborescence spécifié.|  
|[CTreeCtrl::SelectSetFirstVisible](../Topic/CTreeCtrl::SelectSetFirstVisible.md)|Sélectionne un élément d'arborescence spécifié comme premier élément visible.|  
|[CTreeCtrl::SetAutoscrollInfo](../Topic/CTreeCtrl::SetAutoscrollInfo.md)|Définit le taux de défilement automatique du contrôle arborescence actuel.|  
|[CTreeCtrl::SetBkColor](../Topic/CTreeCtrl::SetBkColor.md)|Définit la couleur d'arrière\-plan du contrôle.|  
|[CTreeCtrl::SetCheck](../Topic/CTreeCtrl::SetCheck.md)|Définit l'état d'activation d'un élément de contrôle d'arborescence.|  
|[CTreeCtrl::SetExtendedStyle](../Topic/CTreeCtrl::SetExtendedStyle.md)|Définit les styles étendus pour le contrôle arborescence actuel.|  
|[CTreeCtrl::SetImageList](../Topic/CTreeCtrl::SetImageList.md)|Définit le handle de la liste d'images associée à un contrôle arborescence.|  
|[CTreeCtrl::SetIndent](../Topic/CTreeCtrl::SetIndent.md)|Définit l'offset \(en pixels\) d'un élément d'arborescence de son parent.|  
|[CTreeCtrl::SetInsertMark](../Topic/CTreeCtrl::SetInsertMark.md)|Définit la marque d'insertion dans un contrôle arborescence.|  
|[CTreeCtrl::SetInsertMarkColor](../Topic/CTreeCtrl::SetInsertMarkColor.md)|Définit la couleur utilisée pour dessiner la marque d'insertion de l'arborescence.|  
|[CTreeCtrl::SetItem](../Topic/CTreeCtrl::SetItem.md)|Définit les attributs d'un élément d'arborescence spécifié.|  
|[CTreeCtrl::SetItemData](../Topic/CTreeCtrl::SetItemData.md)|Définit la valeur spécifique à l'application de 32 bits associé à un élément.|  
|[CTreeCtrl::SetItemExpandedImageIndex](../Topic/CTreeCtrl::SetItemExpandedImageIndex.md)|Définit l'index de l'image à afficher lorsque l'élément spécifié du contrôle arborescence actuel se trouve dans l'état développé.|  
|[CTreeCtrl::SetItemHeight](../Topic/CTreeCtrl::SetItemHeight.md)|Définit la hauteur des éléments d'arborescence.|  
|[CTreeCtrl::SetItemImage](../Topic/CTreeCtrl::SetItemImage.md)|Associe des images à un élément.|  
|[CTreeCtrl::SetItemState](../Topic/CTreeCtrl::SetItemState.md)|Définit l'état d'un élément.|  
|[CTreeCtrl::SetItemStateEx](../Topic/CTreeCtrl::SetItemStateEx.md)|Définit l'état étendue de l'élément spécifié dans le contrôle arborescence actuel.|  
|[CTreeCtrl::SetItemText](../Topic/CTreeCtrl::SetItemText.md)|Définit le texte d'un élément.|  
|[CTreeCtrl::SetLineColor](../Topic/CTreeCtrl::SetLineColor.md)|Définit la couleur de ligne active du contrôle arborescence.|  
|[CTreeCtrl::SetScrollTime](../Topic/CTreeCtrl::SetScrollTime.md)|Définit la durée de défilement maximale du contrôle arborescence.|  
|[CTreeCtrl::SetTextColor](../Topic/CTreeCtrl::SetTextColor.md)|Définit la couleur de texte du contrôle.|  
|[CTreeCtrl::SetToolTips](../Topic/CTreeCtrl::SetToolTips.md)|Définit le contrôle d'info\-bulle enfants d'un contrôle arborescence.|  
|[CTreeCtrl::ShowInfoTip](../Topic/CTreeCtrl::ShowInfoTip.md)|Affiche l'infotip pour l'élément spécifié dans le contrôle arborescence actuel.|  
|[CTreeCtrl::SortChildren](../Topic/CTreeCtrl::SortChildren.md)|Trie les enfants d'un élément parent donné.|  
|[CTreeCtrl::SortChildrenCB](../Topic/CTreeCtrl::SortChildrenCB.md)|Trie les enfants d'un élément parent donné à l'aide d'une fonction définie par l'application de tri.|  
  
## Notes  
 Un « contrôle arborescence » est une fenêtre qui affiche une liste hiérarchique d'éléments, tels que les titres dans un document, les entrées d'un index, ou les fichiers et les dossiers sur un disque.  Chaque élément se compose d'une étiquette et une image générée une correspondance de bits facultative, et chaque élément peut contenir une liste de sous\-éléments associés à celui\-ci.  En cliquant sur un élément, l'utilisateur peut développer et réduire la liste associée de sous\-éléments.  
  
 Ce contrôle \(et par conséquent la classe d' `CTreeCtrl` \) est disponible uniquement aux programmes s'exécutant sous la version 4 de Windows 98 et Windows NT et versions ultérieures.  
  
 Pour plus d'informations sur l'utilisation `CTreeCtrl`, consultez :  
  
-   [Contrôles](../../mfc/controls-mfc.md)  
  
-   [Utilisation CTreeCtrl](../../mfc/using-ctreectrl.md)  
  
-   [référence de contrôle arborescence](http://msdn.microsoft.com/library/windows/desktop/bb759988) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
-   Article de la Base de connaissances Q222905 : HOWTO : Afficher un menu contextuel pour CTreeCtrl  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTreeCtrl`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [MFC exemple CMNCTRL1](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CImageList Class](../../mfc/reference/cimagelist-class.md)