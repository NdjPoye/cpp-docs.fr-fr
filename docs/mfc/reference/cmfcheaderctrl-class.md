---
title: "CMFCHeaderCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCHeaderCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCHeaderCtrl class"
ms.assetid: 2f5fbf7b-5c75-42db-9216-640b1628f777
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CMFCHeaderCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCHeaderCtrl` prend en charge plusieurs colonnes de tri dans un contrôle header.  
  
## Syntaxe  
  
```  
class CMFCHeaderCtrl : public CHeaderCtrl  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCHeaderCtrl::CMFCHeaderCtrl](../Topic/CMFCHeaderCtrl::CMFCHeaderCtrl.md)|Construit un objet `CMFCHeaderCtrl`.|  
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCHeaderCtrl::EnableMultipleSort](../Topic/CMFCHeaderCtrl::EnableMultipleSort.md)|Active ou désactive plusieurs mode *de tri de colonne* du contrôle header actuel.|  
|[CMFCHeaderCtrl::GetColumnState](../Topic/CMFCHeaderCtrl::GetColumnState.md)|Indique si une colonne n'est pas triée, ou est triée dans l'ordre croissant ou décroissant.|  
|[CMFCHeaderCtrl::GetSortColumn](../Topic/CMFCHeaderCtrl::GetSortColumn.md)|Extrait l'index de base zéro de la première colonne triée dans le contrôle header.|  
|`CMFCHeaderCtrl::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCHeaderCtrl::IsAscending](../Topic/CMFCHeaderCtrl::IsAscending.md)|Indique si une colonne dans le contrôle header est triée dans l'ordre croissant.|  
|[CMFCHeaderCtrl::IsDialogControl](../Topic/CMFCHeaderCtrl::IsDialogControl.md)|Indique si la fenêtre parente du contrôle header actuel est une boîte de dialogue.|  
|[CMFCHeaderCtrl::IsMultipleSort](../Topic/CMFCHeaderCtrl::IsMultipleSort.md)|Indique si le contrôle header actuel se trouve dans plusieurs mode *de tri de colonne* .|  
|[CMFCHeaderCtrl::RemoveSortColumn](../Topic/CMFCHeaderCtrl::RemoveSortColumn.md)|Supprime la colonne spécifiée de la liste des colonnes de tri.|  
|[CMFCHeaderCtrl::SetSortColumn](../Topic/CMFCHeaderCtrl::SetSortColumn.md)|Définit l'ordre de tri d'une colonne spécifiée dans un contrôle header.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCHeaderCtrl::OnDrawItem](../Topic/CMFCHeaderCtrl::OnDrawItem.md)|Appelé par l'infrastructure pour dessiner une colonne de contrôle header.|  
|[CMFCHeaderCtrl::OnDrawSortArrow](../Topic/CMFCHeaderCtrl::OnDrawSortArrow.md)|Appelé par l'infrastructure pour dessiner la flèche de tri.|  
|[CMFCHeaderCtrl::OnFillBackground](../Topic/CMFCHeaderCtrl::OnFillBackground.md)|Appelé par l'infrastructure pour remplir l'arrière\-plan d'une colonne de contrôle header.|  
  
## Exemple  
 L'exemple suivant montre comment construire un objet avec de la classe d' `CMFCHeaderCtrl` , et comment activer plusieurs mode *de tri de colonne* du contrôle header actuel.  
  
 [!code-cpp[NVC_MFC_RibbonApp#24](../../mfc/reference/codesnippet/CPP/cmfcheaderctrl-class_1.cpp)]  
  
## Notes  
 La classe d' `CMFCHeaderCtrl` dessine une flèche de tri sur une colonne de contrôle header pour indiquer que la colonne est triée.  Utilisez plusieurs mode *de tri de colonne* si un ensemble de colonnes dans le contrôle de liste parent \([CMFCListCtrl Class](../../mfc/reference/cmfclistctrl-class.md)\) peut être triées en même temps.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)  
  
 [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)  
  
## Configuration requise  
 **en\-tête :** afxheaderctrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCListCtrl Class](../../mfc/reference/cmfclistctrl-class.md)