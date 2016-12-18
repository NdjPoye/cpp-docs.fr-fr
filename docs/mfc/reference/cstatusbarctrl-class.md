---
title: "CStatusBarCtrl Class | Microsoft Docs"
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
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl class"
  - "status bar controls"
  - "Windows common controls [C++], CStatusBarCtrl"
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStatusBarCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités du contrôle commun de barre d'état windows.  
  
## Syntaxe  
  
```  
class CStatusBarCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CStatusBarCtrl::CStatusBarCtrl](../Topic/CStatusBarCtrl::CStatusBarCtrl.md)|Construit un objet `CStatusBarCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CStatusBarCtrl::Create](../Topic/CStatusBarCtrl::Create.md)|Crée un contrôle de barre d'état et l'attache à un objet d' `CStatusBarCtrl` .|  
|[CStatusBarCtrl::CreateEx](../Topic/CStatusBarCtrl::CreateEx.md)|Crée un contrôle de barre d'état et les styles étendus par windows spécifiées et l'attache à un objet d' `CStatusBarCtrl` .|  
|[CStatusBarCtrl::DrawItem](../Topic/CStatusBarCtrl::DrawItem.md)|Appelé lorsqu'un aspect visuel s'aligne d'un contrôle de barre d'état owner draw.|  
|[CStatusBarCtrl::GetBorders](../Topic/CStatusBarCtrl::GetBorders.md)|Récupère les largeurs actuelles des zones horizontaux et verticaux d'un contrôle de barre d'état.|  
|[CStatusBarCtrl::GetIcon](../Topic/CStatusBarCtrl::GetIcon.md)|Récupère l'icône pour une partie \(également appelé un volet\) dans le contrôle actuel de barre d'état.|  
|[CStatusBarCtrl::GetParts](../Topic/CStatusBarCtrl::GetParts.md)|Récupère un nombre des parties dans un contrôle de barre d'état.|  
|[CStatusBarCtrl::GetRect](../Topic/CStatusBarCtrl::GetRect.md)|Récupère le rectangle englobant d'une partie dans un contrôle de barre d'état.|  
|[CStatusBarCtrl::GetText](../Topic/CStatusBarCtrl::GetText.md)|Extrait le texte de la partie donnée d'un contrôle de barre d'état.|  
|[CStatusBarCtrl::GetTextLength](../Topic/CStatusBarCtrl::GetTextLength.md)|Récupérez la longueur, en caractères, du texte de la partie donnée d'un contrôle de barre d'état.|  
|[CStatusBarCtrl::GetTipText](../Topic/CStatusBarCtrl::GetTipText.md)|Extrait le texte d'info\-bulle pour un volet d'une barre d'état.|  
|[CStatusBarCtrl::IsSimple](../Topic/CStatusBarCtrl::IsSimple.md)|Un contrôle de fenêtre d'état pour déterminer s'il est en mode simple.|  
|[CStatusBarCtrl::SetBkColor](../Topic/CStatusBarCtrl::SetBkColor.md)|Définit la couleur d'arrière\-plan dans une barre d'état.|  
|[CStatusBarCtrl::SetIcon](../Topic/CStatusBarCtrl::SetIcon.md)|Définit l'icône d'un volet d'une barre d'état.|  
|[CStatusBarCtrl::SetMinHeight](../Topic/CStatusBarCtrl::SetMinHeight.md)|Définit la hauteur minimales de la zone de dessin d'un contrôle de barre d'état.|  
|[CStatusBarCtrl::SetParts](../Topic/CStatusBarCtrl::SetParts.md)|Définit le nombre d'éléments dans un contrôle de barre d'état et la coordonnée du bord droit de chaque partie.|  
|[CStatusBarCtrl::SetSimple](../Topic/CStatusBarCtrl::SetSimple.md)|Spécifie si un contrôle de barre d'état affiche le texte simple ou affiche toutes les parties commande définies par un appel précédent à `SetParts`.|  
|[CStatusBarCtrl::SetText](../Topic/CStatusBarCtrl::SetText.md)|Définit le texte à la partie donnée d'un contrôle de barre d'état.|  
|[CStatusBarCtrl::SetTipText](../Topic/CStatusBarCtrl::SetTipText.md)|Définit le texte d'info\-bulle pour un volet d'une barre d'état.|  
  
## Notes  
 Un « contrôle de barre d'état » est une fenêtre horizontale, qui s'affiche en bas d'une fenêtre parente, dans laquelle une application peut afficher différents types d'informations d'état.  Le contrôle de barre d'état peut être divisé en parties pour afficher plusieurs types d'informations.  
  
 Ce contrôle \(et par conséquent la classe d' `CStatusBarCtrl` \) est disponible uniquement aux programmes s'exécutant sous la version 3,51 de Windows 95\/98 et Windows NT et versions ultérieures.  
  
 Pour plus d'informations sur l'utilisation `CStatusBarCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et l' [Utilisation CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatusBarCtrl`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl Class](../../mfc/reference/ctoolbarctrl-class.md)