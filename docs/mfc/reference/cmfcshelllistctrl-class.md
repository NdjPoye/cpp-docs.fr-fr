---
title: "CMFCShellListCtrl Class | Microsoft Docs"
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
  - "CMFCShellListCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCShellListCtrl class"
ms.assetid: ad472958-5586-4c50-aadf-1844c30bf6e7
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCShellListCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCShellListCtrl` fournit des fonctionnalités de contrôle de liste windows et développe l'en incluant la possibilité d'afficher une liste de shell.  
  
## Syntaxe  
  
```  
class CMFCShellListCtrl : public CMFCListCtrl  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCShellListCtrl::DisplayFolder](../Topic/CMFCShellListCtrl::DisplayFolder.md)|Affiche une liste d'éléments contenus dans un dossier fourni.|  
|[CMFCShellListCtrl::DisplayParentFolder](../Topic/CMFCShellListCtrl::DisplayParentFolder.md)|Affiche une liste d'éléments contenus dans le dossier qui est le parent du dossier actuellement affiché.|  
|[CMFCShellListCtrl::EnableShellContextMenu](../Topic/CMFCShellListCtrl::EnableShellContextMenu.md)|Active ou désactive le menu contextuel.|  
|[CMFCShellListCtrl::GetCurrentFolder](../Topic/CMFCShellListCtrl::GetCurrentFolder.md)|Récupère le chemin d'accès du dossier actif.|  
|[CMFCShellListCtrl::GetCurrentFolderName](../Topic/CMFCShellListCtrl::GetCurrentFolderName.md)|Extrait le nom du dossier actif.|  
|[CMFCShellListCtrl::GetCurrentItemIdList](../Topic/CMFCShellListCtrl::GetCurrentItemIdList.md)|Retourne le PIDL de l'élément actuel de contrôle liste.|  
|[CMFCShellListCtrl::GetCurrentShellFolder](../Topic/CMFCShellListCtrl::GetCurrentShellFolder.md)|Retourne un pointeur vers le dossier actif du shell.|  
|[CMFCShellListCtrl::GetItemPath](../Topic/CMFCShellListCtrl::GetItemPath.md)|Retourne le chemin textuel d'un élément.|  
|[CMFCShellListCtrl::GetItemTypes](../Topic/CMFCShellListCtrl::GetItemTypes.md)|Types d'éléments de shell de retour qui sont affichés par le contrôle de liste.|  
|[CMFCShellListCtrl::IsDesktop](../Topic/CMFCShellListCtrl::IsDesktop.md)|Contrôle si l'heure actuelle le dossier sélectionné est le répertoire de bureau.|  
|[CMFCShellListCtrl::OnCompareItems](../Topic/CMFCShellListCtrl::OnCompareItems.md)|L'infrastructure appelle cette méthode lorsqu'elle compare deux éléments.  \(Substitutions [CMFCListCtrl::OnCompareItems](../Topic/CMFCListCtrl::OnCompareItems.md).\)|  
|[CMFCShellListCtrl::OnFormatFileDate](../Topic/CMFCShellListCtrl::OnFormatFileDate.md)|Appelé lorsque l'infrastructure récupère la date de fichier affichée par le contrôle de liste.|  
|[CMFCShellListCtrl::OnFormatFileSize](../Topic/CMFCShellListCtrl::OnFormatFileSize.md)|Appelé lorsque l'infrastructure convertit la taille d'un contrôle de liste.|  
|[CMFCShellListCtrl::OnGetItemIcon](../Topic/CMFCShellListCtrl::OnGetItemIcon.md)|Appelé lorsque l'infrastructure extrait l'icône d'un élément de contrôle liste.|  
|[CMFCShellListCtrl::OnGetItemText](../Topic/CMFCShellListCtrl::OnGetItemText.md)|Appelé lorsque l'infrastructure convertit le texte d'un élément de contrôle liste.|  
|[CMFCShellListCtrl::OnSetColumns](../Topic/CMFCShellListCtrl::OnSetColumns.md)|Appelé par l'infrastructure lorsqu'il définit les noms des colonnes.|  
|[CMFCShellListCtrl::Refresh](../Topic/CMFCShellListCtrl::Refresh.md)|Actualise et redessine le contrôle de liste.|  
|[CMFCShellListCtrl::SetItemTypes](../Topic/CMFCShellListCtrl::SetItemTypes.md)|Définit le type d'éléments affichés par le contrôle de liste.|  
  
## Notes  
 La classe d' `CMFCShellListCtrl` étend les fonctionnalités de [CMFCListCtrl Class](../../mfc/reference/cmfclistctrl-class.md) en permettant à votre programme de répertorier les éléments de shell Windows.  Le format d'affichage qui est utilisé est semblable à celui d'une vue Liste pour une fenêtre d'explorateur.  
  
 Un objet de [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) peut être associé à un objet d' `CMFCShellListCtrl` pour créer une fenêtre complète de l'explorateur.  Ensuite, sélectionner un élément dans `CMFCShellTreeCtrl` répertorier fera l'objet d' `CMFCShellListCtrl` le contenu de l'élément sélectionné.  
  
## Exemple  
 L'exemple suivant montre comment créer un objet de la classe d' `CMFCShellListCtrl` et comment afficher le dossier parent du dossier actuellement affiché.  Cet extrait de code fait partie d' [Exemple explorer](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#1](../../mfc/reference/codesnippet/CPP/cmfcshelllistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer#2](../../mfc/reference/codesnippet/CPP/cmfcshelllistctrl-class_2.cpp)]  
[!code-cpp[NVC_MFC_Explorer#3](../../mfc/reference/codesnippet/CPP/cmfcshelllistctrl-class_3.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)  
  
## Configuration requise  
 **en\-tête :** afxshelllistCtrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCListCtrl Class](../../mfc/reference/cmfclistctrl-class.md)   
 [CMFCShellTreeCtrl Class](../../mfc/reference/cmfcshelltreectrl-class.md)