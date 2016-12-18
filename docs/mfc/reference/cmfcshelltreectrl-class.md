---
title: "CMFCShellTreeCtrl Class | Microsoft Docs"
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
  - "CMFCShellTreeCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCShellTreeCtrl class"
ms.assetid: 3d1da715-9554-4ed7-968c-055c48146267
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCShellTreeCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCShellTreeCtrl` étend les fonctionnalités de [CTreeCtrl Class](../../mfc/reference/ctreectrl-class.md) en affichant une hiérarchie des éléments du shell.  
  
## Syntaxe  
  
```  
class CMFCShellTreeCtrl : public CTreeCtrl  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCShellTreeCtrl::EnableShellContextMenu](../Topic/CMFCShellTreeCtrl::EnableShellContextMenu.md)|Active ou désactive le menu contextuel.|  
|[CMFCShellTreeCtrl::GetFlags](../Topic/CMFCShellTreeCtrl::GetFlags.md)|Retourne une combinaison des balises qui sont passées à [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066).|  
|[CMFCShellTreeCtrl::GetItemPath](../Topic/CMFCShellTreeCtrl::GetItemPath.md)|Récupère le chemin d'accès à un élément.|  
|[CMFCShellTreeCtrl::GetRelatedList](../Topic/CMFCShellTreeCtrl::GetRelatedList.md)|Retourne un pointeur vers l'objet de [CMFCShellListCtrl Class](../../mfc/reference/cmfcshelllistctrl-class.md) utilisé avec cet objet d' `CMFCShellTreeCtrl` pour créer une fenêtre comme un explorateur.|  
|[CMFCShellTreeCtrl::OnChildNotify](../Topic/CMFCShellTreeCtrl::OnChildNotify.md)|Cette fonction membre est appelée par la fenêtre parente de cette fenêtre lorsqu'il reçoit un message de notification qui s'applique à cette fenêtre.  \(Substitutions [CWnd::OnChildNotify](../Topic/CWnd::OnChildNotify.md).\)|  
|[CMFCShellTreeCtrl::OnGetItemIcon](../Topic/CMFCShellTreeCtrl::OnGetItemIcon.md)||  
|[CMFCShellTreeCtrl::OnGetItemText](../Topic/CMFCShellTreeCtrl::OnGetItemText.md)||  
|[CMFCShellTreeCtrl::Refresh](../Topic/CMFCShellTreeCtrl::Refresh.md)|Actualise et redessine l'objet actuel d' `CMFCShellTreeCtrl` .|  
|[CMFCShellTreeCtrl::SelectPath](../Topic/CMFCShellTreeCtrl::SelectPath.md)|Sélectionne l'élément de contrôle tree approprié selon un chemin d'accès fourni de PIDL ou de chaîne.|  
|[CMFCShellTreeCtrl::SetFlags](../Topic/CMFCShellTreeCtrl::SetFlags.md)|Indicateurs de jeux pour filtrer le contexte d'arborescence \(similaire aux balises utilisées par `IShellFolder::EnumObjects`\).|  
|[CMFCShellTreeCtrl::SetRelatedList](../Topic/CMFCShellTreeCtrl::SetRelatedList.md)|Définit une relation entre l'objet actuel d' `CMFCShellTreeCtrl` et un objet d' `CMFCShellListCtrl` .|  
  
## Notes  
 Cette classe étend la classe d' `CTreeCtrl` en permettant à votre programme pour inclure les éléments de shell Windows dans l'arborescence.  Cette classe peut être associée à un objet d' `CMFCShellListCtrl` pour créer une fenêtre complète de l'explorateur.  Ensuite, sélectionner un élément dans l'arborescence affiche une liste de shell Windows dans la liste associée.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CTreeCtrl](../../mfc/reference/ctreectrl-class.md)  
  
 [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)  
  
## Configuration requise  
 **en\-tête :** afxshelltreeCtrl.h  
  
## Exemple  
 L'exemple suivant montre comment créer un objet de la classe d' `CMFCShellTreeCtrl` .  Cet extrait de code fait partie d' [Exemple explorer](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/CPP/cmfcshelltreectrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/CPP/cmfcshelltreectrl-class_2.cpp)]  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CTreeCtrl Class](../../mfc/reference/ctreectrl-class.md)   
 [CMFCShellListCtrl Class](../../mfc/reference/cmfcshelllistctrl-class.md)