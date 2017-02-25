---
title: "CHeaderCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHeaderCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeaderCtrl class"
  - "header controls, CHeaderCtrl class"
  - "Windows common controls [C++], CHeaderCtrl"
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CHeaderCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités du contrôle header communs windows.  
  
## Syntaxe  
  
```  
class CHeaderCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CHeaderCtrl::CHeaderCtrl](../Topic/CHeaderCtrl::CHeaderCtrl.md)|Construit un objet `CHeaderCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CHeaderCtrl::ClearAllFilters](../Topic/CHeaderCtrl::ClearAllFilters.md)|Efface tous les filtres pour un contrôle header.|  
|[CHeaderCtrl::ClearFilter](../Topic/CHeaderCtrl::ClearFilter.md)|Efface le filtre pour un contrôle header.|  
|[CHeaderCtrl::Create](../Topic/CHeaderCtrl::Create.md)|Crée un contrôle header et l'attache à un objet d' `CHeaderCtrl` .|  
|[CHeaderCtrl::CreateDragImage](../Topic/CHeaderCtrl::CreateDragImage.md)|Crée une version transparente de l'image d'un élément dans un contrôle header.|  
|[CHeaderCtrl::CreateEx](../Topic/CHeaderCtrl::CreateEx.md)|Crée un contrôle header avec les styles étendus par windows spécifiées et l'attache à un objet d' `CListCtrl` .|  
|[CHeaderCtrl::DeleteItem](../Topic/CHeaderCtrl::DeleteItem.md)|Supprime un élément d'un contrôle header.|  
|[CHeaderCtrl::DrawItem](../Topic/CHeaderCtrl::DrawItem.md)|Dessine l'élément spécifié d'un contrôle header.|  
|[CHeaderCtrl::EditFilter](../Topic/CHeaderCtrl::EditFilter.md)|Démarre modifiant le filtre spécifié d'un contrôle header.|  
|[CHeaderCtrl::GetBitmapMargin](../Topic/CHeaderCtrl::GetBitmapMargin.md)|Extrait la largeur de la marge d'une bitmap dans un contrôle header.|  
|[CHeaderCtrl::GetFocusedItem](../Topic/CHeaderCtrl::GetFocusedItem.md)|Obtient l'identificateur de l'élément dans le contrôle header actuel qui a le focus.|  
|[CHeaderCtrl::GetImageList](../Topic/CHeaderCtrl::GetImageList.md)|Récupère le handle d'une liste d'images utilisée pour dessiner des éléments d'en\-tête dans un contrôle header.|  
|[CHeaderCtrl::GetItem](../Topic/CHeaderCtrl::GetItem.md)|Récupère des informations sur un élément dans un contrôle header.|  
|[CHeaderCtrl::GetItemCount](../Topic/CHeaderCtrl::GetItemCount.md)|Récupère un nombre d'éléments dans un contrôle header.|  
|[CHeaderCtrl::GetItemDropDownRect](../Topic/CHeaderCtrl::GetItemDropDownRect.md)|Obtient les informations du rectangle englobant du bouton déroulant spécifié dans un contrôle header.|  
|[CHeaderCtrl::GetItemRect](../Topic/CHeaderCtrl::GetItemRect.md)|Récupère le rectangle englobant d'un élément donné dans un contrôle header.|  
|[CHeaderCtrl::GetOrderArray](../Topic/CHeaderCtrl::GetOrderArray.md)|Extrait la commande de gauche à droite d'éléments dans un contrôle header.|  
|[CHeaderCtrl::GetOverflowRect](../Topic/CHeaderCtrl::GetOverflowRect.md)|Obtient le rectangle englobant du bouton de dépassement pour le contrôle header actuel.|  
|[CHeaderCtrl::HitTest](../Topic/CHeaderCtrl::HitTest.md)|Détermine que l'élément d'en\-tête, le cas échéant, se trouve à un point spécifié.|  
|[CHeaderCtrl::InsertItem](../Topic/CHeaderCtrl::InsertItem.md)|Insère un nouvel élément dans un contrôle header.|  
|[CHeaderCtrl::Layout](../Topic/CHeaderCtrl::Layout.md)|Extrait la taille et la position d'un contrôle header dans un rectangle donné.|  
|[CHeaderCtrl::OrderToIndex](../Topic/CHeaderCtrl::OrderToIndex.md)|Extrait la valeur d'index d'un élément selon sa commande dans le contrôle header.|  
|[CHeaderCtrl::SetBitmapMargin](../Topic/CHeaderCtrl::SetBitmapMargin.md)|Définit la largeur de la marge d'une bitmap dans un contrôle header.|  
|[CHeaderCtrl::SetFilterChangeTimeout](../Topic/CHeaderCtrl::SetFilterChangeTimeout.md)|Définit l'intervalle de délai d'attente entre le moment où une modification se produit dans les attributs de filtre et l'propose d'une notification d' `HDN_FILTERCHANGE` .|  
|[CHeaderCtrl::SetFocusedItem](../Topic/CHeaderCtrl::SetFocusedItem.md)|Place le focus à un élément d'en\-tête spécifié dans le contrôle header actuel.|  
|[CHeaderCtrl::SetHotDivider](../Topic/CHeaderCtrl::SetHotDivider.md)|Modifie le séparateur entre des éléments d'en\-tête pour indiquer un glisser\-déplacer manuel d'un élément d'en\-tête.|  
|[CHeaderCtrl::SetImageList](../Topic/CHeaderCtrl::SetImageList.md)|Assigne une liste d'images à un contrôle header.|  
|[CHeaderCtrl::SetItem](../Topic/CHeaderCtrl::SetItem.md)|Définit les attributs de l'élément spécifié dans un contrôle header.|  
|[CHeaderCtrl::SetOrderArray](../Topic/CHeaderCtrl::SetOrderArray.md)|Définit la commande de gauche à droite d'éléments dans un contrôle header.|  
  
## Notes  
 Un contrôle header est une fenêtre qui est généralement positionnée au\-dessus d'un ensemble de colonnes de texte ou compte.  Il contient un titre pour chaque colonne, et il peut être divisé en parties.  L'utilisateur peut faire glisser les séparateurs qui séparent les parties pour définir la largeur de chaque colonne.  Pour obtenir une illustration d'un contrôle header, consultez [Contrôles header](http://msdn.microsoft.com/library/windows/desktop/bb775238).  
  
 Ce contrôle \(et par conséquent la classe d' `CHeaderCtrl` \) est disponible uniquement aux programmes qui s'exécutent sous la version 3,51 de Windows 95\/98 et Windows NT et versions ultérieures.  
  
 La fonctionnalité ajoutée pour les contrôles communs Windows 95 ou Internet Explorer 4.0 inclut les éléments suivants :  
  
-   Le classement de personnalisé d'élément d'en\-tête.  
  
-   Glisser\-déplacer d'élément d'en\-tête, pour réorganiser les éléments d'en\-tête.  Utilisez le style d' `HDS_DRAGDROP` lorsque vous créez l'objet d' `CHeaderCtrl` .  
  
-   Texte de colonne d'en\-tête constamment affichable lors de le redimensionnement de colonne.  Utilisez le style d' `HDS_FULLDRAG` lorsque vous créez un objet d' `CHeaderCtrl` .  
  
-   Sélection réactive d'en\-tête, qui met en surbrillance l'élément d'en\-tête lorsque le pointeur de la souris passe sur lui.  Utilisez le style d' `HDS_HOTTRACK` lorsque vous créez l'objet d' `CHeaderCtrl` .  
  
-   Prise en charge de la liste d'images.  Les éléments d'en\-tête peuvent contenir des images stockées dans un objet d' `CImageList` ou texte.  
  
 Pour plus d'informations sur l'utilisation `CHeaderCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et l' [Utilisation CHeaderCtrl](../../mfc/using-cheaderctrl.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHeaderCtrl`  
  
## Configuration requise  
 **en\-tête :** afxcmn.h  
  
## Voir aussi  
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CTabCtrl Class](../../mfc/reference/ctabctrl-class.md)   
 [CListCtrl Class](../../mfc/reference/clistctrl-class.md)   
 [CImageList Class](../../mfc/reference/cimagelist-class.md)