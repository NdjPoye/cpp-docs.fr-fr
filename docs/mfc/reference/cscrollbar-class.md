---
title: "CScrollBar Class | Microsoft Docs"
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
  - "CScrollBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "controls [MFC], barre de défilement"
  - "CScrollBar class"
  - "barres de défilement"
  - "SCROLLBAR window class"
  - "Windows common controls [C++], CScrollBar"
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CScrollBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités d'un contrôle de barre de défilement de windows.  
  
## Syntaxe  
  
```  
class CScrollBar : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CScrollBar::CScrollBar](../Topic/CScrollBar::CScrollBar.md)|Construit un objet `CScrollBar`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CScrollBar::Create](../Topic/CScrollBar::Create.md)|Crée la barre de défilement de fenêtres et la attaché à l'objet d' `CScrollBar` .|  
|[CScrollBar::EnableScrollBar](../Topic/CScrollBar::EnableScrollBar.md)|Active ou désactive une ou les deux flèches d'une barre de défilement.|  
|[CScrollBar::GetScrollBarInfo](../Topic/CScrollBar::GetScrollBarInfo.md)|Récupère des informations sur la barre de défilement à l'aide d'une structure d' `SCROLLBARINFO` .|  
|[CScrollBar::GetScrollInfo](../Topic/CScrollBar::GetScrollInfo.md)|Récupère des informations sur la barre de défilement.|  
|[CScrollBar::GetScrollLimit](../Topic/CScrollBar::GetScrollLimit.md)|Extrait la limite de la barre de défilement|  
|[CScrollBar::GetScrollPos](../Topic/CScrollBar::GetScrollPos.md)|Extrait la position actuelle d'une case de défilement.|  
|[CScrollBar::GetScrollRange](../Topic/CScrollBar::GetScrollRange.md)|Récupère les positions actuelles minimales et de barre de défilement de maximale de la barre de défilement donnée.|  
|[CScrollBar::SetScrollInfo](../Topic/CScrollBar::SetScrollInfo.md)|Définit des informations sur la barre de défilement.|  
|[CScrollBar::SetScrollPos](../Topic/CScrollBar::SetScrollPos.md)|Définit la position actuelle d'une case de défilement.|  
|[CScrollBar::SetScrollRange](../Topic/CScrollBar::SetScrollRange.md)|Définit les valeurs minimales et maximales de position de la barre de défilement donnée.|  
|[CScrollBar::ShowScrollBar](../Topic/CScrollBar::ShowScrollBar.md)|Affiche ou masque un barre de défilement.|  
  
## Notes  
 Vous créez un contrôle de barre de défilement en deux étapes.  D'abord, appelez le constructeur `CScrollBar` pour construire l'objet d' `CScrollBar` , puis appelez la fonction membre de [Create](../Topic/CScrollBar::Create.md) pour créer le contrôle de barre de défilement windows et le lier à l'objet d' `CScrollBar` .  
  
 Si vous créez un objet d' `CScrollBar` dans une boîte de dialogue \(via une ressource de boîte de dialogue\), `CScrollBar` est automatiquement détruit lorsque l'utilisateur ferme la boîte de dialogue.  
  
 Si vous créez un objet d' `CScrollBar` dans une fenêtre, vous devrez peut\-être également la destruction.  
  
 Si vous créez l'objet d' `CScrollBar` sur la pile, elle est perdue automatiquement.  Si vous créez l'objet d' `CScrollBar` sur le tas à l'aide de la fonction de **nouveau** , vous devez appeler **supprimer** sur l'objet pour le détruire lorsque l'utilisateur a terminé la barre de défilement de windows.  
  
 Si vous allouez une mémoire de l'objet d' `CScrollBar` , remplacez le destructeur d' `CScrollBar` pour disposer les allocations.  
  
 Pour plus d'informations sur l'utilisation `CScrollBar`, consultez [contrôles](../../mfc/controls-mfc.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CScrollBar`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [CStatic Class](../../mfc/reference/cstatic-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)