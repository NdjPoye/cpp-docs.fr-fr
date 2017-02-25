---
title: "CPagerCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPagerCtrl class"
ms.assetid: 65ac58dd-4f5e-4b7e-b15c-e0d435a7e884
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CPagerCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CPagerCtrl` encapsule le contrôle pager windows, qui peut faire défiler dans l'affichage d'une fenêtre contenue qui ne rentre pas la fenêtre contenante.  
  
## Syntaxe  
  
```  
class CPagerCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPagerCtrl::CPagerCtrl](../Topic/CPagerCtrl::CPagerCtrl.md)|Construit un objet `CPagerCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPagerCtrl::Create](../Topic/CPagerCtrl::Create.md)|Crée un contrôle pager avec les styles spécifiés et l'attache à l'objet actuel d' `CPagerCtrl` .|  
|[CPagerCtrl::CreateEx](../Topic/CPagerCtrl::CreateEx.md)|Crée un contrôle pager avec les styles étendus spécifiés et l'attache à l'objet actuel d' `CPagerCtrl` .|  
|[CPagerCtrl::ForwardMouse](../Topic/CPagerCtrl::ForwardMouse.md)|Active ou désactive transférer des messages de [WM\_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) à la fenêtre qui est contenue dans le contrôle actuel du pagineur.|  
|[CPagerCtrl::GetBkColor](../Topic/CPagerCtrl::GetBkColor.md)|Extrait la couleur d'arrière\-plan du contrôle actuel du pagineur.|  
|[CPagerCtrl::GetBorder](../Topic/CPagerCtrl::GetBorder.md)|Extrait la taille de la bordure du contrôle actuel du pagineur.|  
|[CPagerCtrl::GetButtonSize](../Topic/CPagerCtrl::GetButtonSize.md)|Extrait la taille du bouton du contrôle actuel du pagineur.|  
|[CPagerCtrl::GetButtonState](../Topic/CPagerCtrl::GetButtonState.md)|Récupère l'état du bouton spécifié dans le contrôle actuel du pagineur.|  
|[CPagerCtrl::GetDropTarget](../Topic/CPagerCtrl::GetDropTarget.md)|Récupère l'interface d' [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) du contrôle actuel du pagineur.|  
|[CPagerCtrl::GetScrollPos](../Topic/CPagerCtrl::GetScrollPos.md)|Extrait la position de défilement du contrôle actuel du pagineur.|  
|[CPagerCtrl::IsButtonDepressed](../Topic/CPagerCtrl::IsButtonDepressed.md)|Indique si le bouton spécifié du contrôle actuel du pagineur dans l'état d' `pressed` .|  
|[CPagerCtrl::IsButtonGrayed](../Topic/CPagerCtrl::IsButtonGrayed.md)|Indique si le bouton spécifié du contrôle actuel du pagineur dans l'état d' `grayed` .|  
|[CPagerCtrl::IsButtonHot](../Topic/CPagerCtrl::IsButtonHot.md)|Indique si le bouton spécifié du contrôle actuel du pagineur dans l'état d' `hot` .|  
|[CPagerCtrl::IsButtonInvisible](../Topic/CPagerCtrl::IsButtonInvisible.md)|Indique si le bouton spécifié du contrôle actuel du pagineur dans l'état d' `invisible` .|  
|[CPagerCtrl::IsButtonNormal](../Topic/CPagerCtrl::IsButtonNormal.md)|Indique si le bouton spécifié du contrôle actuel du pagineur dans l'état d' `normal` .|  
|[CPagerCtrl::RecalcSize](../Topic/CPagerCtrl::RecalcSize.md)|Fait recalculer le contrôle actuel du pagineur la taille de la fenêtre contenue.|  
|[CPagerCtrl::SetBkColor](../Topic/CPagerCtrl::SetBkColor.md)|Définit la couleur d'arrière\-plan du contrôle actuel du pagineur.|  
|[CPagerCtrl::SetBorder](../Topic/CPagerCtrl::SetBorder.md)|Définit la taille de la bordure du contrôle actuel du pagineur.|  
|[CPagerCtrl::SetButtonSize](../Topic/CPagerCtrl::SetButtonSize.md)|Définit la taille du bouton du contrôle actuel du pagineur.|  
|[CPagerCtrl::SetChild](../Topic/CPagerCtrl::SetChild.md)|Définit la fenêtre contenue du contrôle actuel du pagineur.|  
|[CPagerCtrl::SetScrollPos](../Topic/CPagerCtrl::SetScrollPos.md)|Définit la position de défilement du contrôle actuel du pagineur.|  
  
## Notes  
 Un contrôle pager est une fenêtre qui contient une autre fenêtre qui est linéaire et plus grande que la fenêtre contenante, et vous permet de faire défiler la fenêtre contenue dans la vue.  Le contrôle pager affiche deux boutons de défilement qui disparaissent automatiquement lorsque la fenêtre est contenue vous faites jusqu'à son degré plus lointain, et réapparaissent sinon.  Vous pouvez créer un contrôle pager faisant défiler horizontalement ou verticalement.  
  
 Par exemple, si votre application possède une barre d'outils qui n'est pas assez large pour afficher tous ses éléments, vous pouvez assigner la barre d'outils à un contrôle pager et les utilisateurs pourront faire défiler la barre d'outils à gauche ou à droite pour accéder à tous les éléments.  La version 4,0 \(version 4,71 de Microsoft Internet Explorer de commctrl.dll\) présente le contrôle pager.  
  
 La classe d' `CPagerCtrl` est dérivée de la classe de [CWnd](../../mfc/reference/cwnd-class.md) .  Pour plus d'informations et pour obtenir une illustration d'un contrôle pager, consultez [Contrôle Pager](http://msdn.microsoft.com/library/windows/desktop/bb760855).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPagerCtrl`  
  
## Configuration requise  
 **en\-tête :** afxcmn.h  
  
## Voir aussi  
 [CPagerCtrl Class](../../mfc/reference/cpagerctrl-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Contrôle Pager](http://msdn.microsoft.com/library/windows/desktop/bb760855)