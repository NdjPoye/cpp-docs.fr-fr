---
title: "CMFCListCtrl Class | Microsoft Docs"
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
  - "CMFCListCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCListCtrl class"
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
caps.latest.revision: 29
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCListCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCListCtrl` étend les fonctionnalités de la classe de [CListCtrl Class](../../mfc/reference/clistctrl-class.md) en prenant en charge les fonctionnalités avancées de contrôle header de [CMFCHeaderCtrl Class](../../mfc/reference/cmfcheaderctrl-class.md).  
  
## Syntaxe  
  
```  
class CMFCListCtrl : public CListCtrl  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCListCtrl::EnableMarkSortedColumn](../Topic/CMFCListCtrl::EnableMarkSortedColumn.md)|Active la capacité de marquer une colonne triée avec une couleur d'arrière\-plan différente.|  
|[CMFCListCtrl::EnableMultipleSort](../Topic/CMFCListCtrl::EnableMultipleSort.md)|Active plusieurs mode de tri.|  
|[CMFCListCtrl::GetHeaderCtrl](../Topic/CMFCListCtrl::GetHeaderCtrl.md)|Retourne une référence au contrôle header souligné.|  
|[CMFCListCtrl::IsMultipleSort](../Topic/CMFCListCtrl::IsMultipleSort.md)|Contrôle si le contrôle de liste est dans plusieurs mode de tri.|  
|[CMFCListCtrl::OnCompareItems](../Topic/CMFCListCtrl::OnCompareItems.md)|Appelé par l'infrastructure lorsqu'il doit comparer deux éléments de contrôle liste.|  
|[CMFCListCtrl::OnGetCellBkColor](../Topic/CMFCListCtrl::OnGetCellBkColor.md)|Appelé par l'infrastructure lorsqu'il doit déterminer la couleur d'arrière\-plan d'une cellule individuelle.|  
|[CMFCListCtrl::OnGetCellFont](../Topic/CMFCListCtrl::OnGetCellFont.md)|Appelé par l'infrastructure lorsqu'il doit obtenir la police de la cellule est dessinée.|  
|[CMFCListCtrl::OnGetCellTextColor](../Topic/CMFCListCtrl::OnGetCellTextColor.md)|Appelé par l'infrastructure lorsqu'il doit déterminer la couleur du texte d'une cellule individuelle.|  
|[CMFCListCtrl::RemoveSortColumn](../Topic/CMFCListCtrl::RemoveSortColumn.md)|Supprime une colonne de tri de la liste de colonnes triées.|  
|[CMFCListCtrl::SetSortColumn](../Topic/CMFCListCtrl::SetSortColumn.md)|Définit la colonne triée actuelle et l'ordre de tri.|  
|[CMFCListCtrl::Sort](../Topic/CMFCListCtrl::Sort.md)|Trie le contrôle de liste.|  
  
## Notes  
 `CMFCListCtrl` offre deux améliorations à la classe de [CListCtrl Class](../../mfc/reference/clistctrl-class.md) .  d'abord, elle indique que le tri de colonne est une option disponible en dessinant automatiquement une flèche de tri sur l'en\-tête.  Ensuite, elle prend en charge le tri de données sur plusieurs colonnes en même temps.  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCListCtrl` .  L'exemple montre comment créer un contrôle de liste, insérer des colonnes, insérer des éléments, définir le texte d'un élément, et définir la police du contrôle de liste.  Cet extrait de code fait partie d' [Exemple de démonstration de Visual Studio](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#25](../../mfc/codesnippet/CPP/cmfclistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#26](../../mfc/codesnippet/CPP/cmfclistctrl-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
## Configuration requise  
 **en\-tête :** afxlistctrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CListCtrl Class](../../mfc/reference/clistctrl-class.md)