---
title: "CTabCtrl Class | Microsoft Docs"
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
  - "CTabCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabCtrl class"
  - "CTabCtrl class, contrôles communs"
  - "contrôles onglet"
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTabCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités du contrôle onglet communs windows.  
  
## Syntaxe  
  
```  
class CTabCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CTabCtrl::CTabCtrl](../Topic/CTabCtrl::CTabCtrl.md)|Construit un objet `CTabCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CTabCtrl::AdjustRect](../Topic/CTabCtrl::AdjustRect.md)|Calcule la zone d'affichage d'un contrôle onglet donnée un rectangle de fenêtre, ou calcule le rectangle de fenêtre qui correspondrait à une zone d'affichage donnée.|  
|[CTabCtrl::Create](../Topic/CTabCtrl::Create.md)|Crée un contrôle onglet et l'attache à une instance d'un objet d' `CTabCtrl` .|  
|[CTabCtrl::CreateEx](../Topic/CTabCtrl::CreateEx.md)|Crée un contrôle onglet avec les styles étendus par windows spécifiées et l'attache à une instance d'un objet d' `CTabCtrl` .|  
|[CTabCtrl::DeleteAllItems](../Topic/CTabCtrl::DeleteAllItems.md)|Supprime tous les éléments d'un contrôle onglet.|  
|[CTabCtrl::DeleteItem](../Topic/CTabCtrl::DeleteItem.md)|Supprime un élément d'un contrôle onglet.|  
|[CTabCtrl::DeselectAll](../Topic/CTabCtrl::DeselectAll.md)|En réinitialise des éléments dans un contrôle onglet, la suppression qui ont été appuyés.|  
|[CTabCtrl::DrawItem](../Topic/CTabCtrl::DrawItem.md)|Dessine un élément spécifié d'un contrôle onglet.|  
|[CTabCtrl::GetCurFocus](../Topic/CTabCtrl::GetCurFocus.md)|Récupère l'onglet avec le focus actuel d'un contrôle onglet.|  
|[CTabCtrl::GetCurSel](../Topic/CTabCtrl::GetCurSel.md)|Détermine l'onglet sélectionné dans un contrôle onglet.|  
|[CTabCtrl::GetExtendedStyle](../Topic/CTabCtrl::GetExtendedStyle.md)|Récupère les styles étendus qui sont actuellement utilisées pour le contrôle onglet.|  
|[CTabCtrl::GetImageList](../Topic/CTabCtrl::GetImageList.md)|Récupère la liste d'images associée à un contrôle onglet.|  
|[CTabCtrl::GetItem](../Topic/CTabCtrl::GetItem.md)|Récupère des informations sur un onglet dans un contrôle onglet.|  
|[CTabCtrl::GetItemCount](../Topic/CTabCtrl::GetItemCount.md)|Récupère le nombre d'onglets dans le contrôle onglet.|  
|[CTabCtrl::GetItemRect](../Topic/CTabCtrl::GetItemRect.md)|Récupère le rectangle englobant d'un onglet dans un contrôle onglet.|  
|[CTabCtrl::GetItemState](../Topic/CTabCtrl::GetItemState.md)|Récupère l'état de l'élément désigné de contrôle tab.|  
|[CTabCtrl::GetRowCount](../Topic/CTabCtrl::GetRowCount.md)|Récupère le nombre de lignes actuel d'onglets dans un contrôle onglet.|  
|[CTabCtrl::GetToolTips](../Topic/CTabCtrl::GetToolTips.md)|Récupère le handle du contrôle d'info\-bulle associé à un contrôle onglet.|  
|[CTabCtrl::HighlightItem](../Topic/CTabCtrl::HighlightItem.md)|Définit l'état de mise en surbrillance d'un élément d'onglet.|  
|[CTabCtrl::HitTest](../Topic/CTabCtrl::HitTest.md)|Détermine quel onglet, le cas échéant, est à une position spécifiée d'écran.|  
|[CTabCtrl::InsertItem](../Topic/CTabCtrl::InsertItem.md)|Insère un nouvel onglet dans un contrôle onglet.|  
|[CTabCtrl::RemoveImage](../Topic/CTabCtrl::RemoveImage.md)|Supprime une image de la liste d'images d'un contrôle onglet.|  
|[CTabCtrl::SetCurFocus](../Topic/CTabCtrl::SetCurFocus.md)|Définit le focus sur un onglet spécifié dans un contrôle onglet.|  
|[CTabCtrl::SetCurSel](../Topic/CTabCtrl::SetCurSel.md)|Sélectionne un onglet dans un contrôle onglet.|  
|[CTabCtrl::SetExtendedStyle](../Topic/CTabCtrl::SetExtendedStyle.md)|Définit les styles étendus pour un contrôle onglet.|  
|[CTabCtrl::SetImageList](../Topic/CTabCtrl::SetImageList.md)|Assigne une liste d'images à un contrôle onglet.|  
|[CTabCtrl::SetItem](../Topic/CTabCtrl::SetItem.md)|Définit une partie ou l'ensemble des attributs d'un onglet.|  
|[CTabCtrl::SetItemExtra](../Topic/CTabCtrl::SetItemExtra.md)|Définit le nombre d'octets par onglet réservé pour les données définies par l'application dans un contrôle onglet.|  
|[CTabCtrl::SetItemSize](../Topic/CTabCtrl::SetItemSize.md)|Définit la largeur et la hauteur d'un élément.|  
|[CTabCtrl::SetItemState](../Topic/CTabCtrl::SetItemState.md)|Définit l'état de l'élément désigné de contrôle tab.|  
|[CTabCtrl::SetMinTabWidth](../Topic/CTabCtrl::SetMinTabWidth.md)|Définit la largeur minimale des éléments dans un contrôle onglet.|  
|[CTabCtrl::SetPadding](../Topic/CTabCtrl::SetPadding.md)|Définit la quantité d'espace \(padding\) autour de l'icône et de l'étiquette de chaque onglet dans un contrôle onglet.|  
|[CTabCtrl::SetToolTips](../Topic/CTabCtrl::SetToolTips.md)|Assigne un contrôle d'info\-bulle à un contrôle onglet.|  
  
## Notes  
 Un « contrôle tab » est analogue à des séparateurs dans un livre ou aux étiquettes dans un classeur.  En utilisant un contrôle onglet, une application peut définir plusieurs pages pour la même zone d'une fenêtre ou boîte de dialogue.  Chaque page se compose d'un jeu d'informations ou d'un groupe de contrôles que l'application affiche lorsque l'utilisateur sélectionne la table correspondante.  Un type particulier de contrôle onglet affiche les onglets qui ressemblent aux boutons.  Cliquez sur un bouton doit immédiatement exécuter une commande au lieu d'afficher une page.  
  
 Ce contrôle \(et par conséquent la classe d' `CTabCtrl` \) est disponible uniquement aux programmes s'exécutant sous la version 3,51 de Windows 95\/98 et Windows NT et versions ultérieures.  
  
 Pour plus d'informations sur l'utilisation `CTabCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et l' [Utilisation CTabCtrl](../../mfc/using-ctabctrl.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTabCtrl`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CHeaderCtrl Class](../../mfc/reference/cheaderctrl-class.md)   
 [CListCtrl Class](../../mfc/reference/clistctrl-class.md)