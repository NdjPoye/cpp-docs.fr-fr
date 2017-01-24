---
title: "CReBar Class | Microsoft Docs"
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
  - "CReBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBar class"
  - "Internet Explorer 4.0 common controls"
  - "rebar controls, control bar"
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CReBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une barre de contrôles qui fournit la disposition, la persistance, et les informations d'état pour les rebar contrôles.  
  
## Syntaxe  
  
```  
  
class CReBar : public CControlBar  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CReBar::AddBar](../Topic/CReBar::AddBar.md)|Ajoute une bande à un rebar.|  
|[CReBar::Create](../Topic/CReBar::Create.md)|Crée le contrôle rebar et l'attache à l'objet d' `CReBar` .|  
|[CReBar::GetReBarCtrl](../Topic/CReBar::GetReBarCtrl.md)|Autorise l'accès direct au contrôle commun sous\-jacent.|  
  
## Notes  
 Un objet rebar peut contenir plusieurs fenêtres enfants, généralement d'autres contrôles, y compris les zones d'édition, des barres d'outils, les zones de liste.  Un objet rebar peut afficher ses fenêtres enfants sur une bitmap spécifiée.  Votre application peut automatiquement redimensionner le rebar, ou l'utilisateur peut redimensionner manuellement le rebar en cliquant sur ou en faisant glisser sa barre de pinces.  
  
 ![Exemple de RebarMenu](../../mfc/reference/media/vc4sc61.png "vc4SC61")  
  
## Contrôle rebar  
 Un objet rebar se comporte de la même façon à un objet barre d'outils.  Rebar utilise le mécanisme de clic\-et\- glisser\-déplacer de redimensionner ses bandes.  Un contrôle rebar peut contenir un ou plusieurs bandes, chaque bande ayant une combinaison d'une barre de pinces, d'une bitmap, d'une étiquette de texte, et d'une fenêtre enfant.  Toutefois, les bandes ne peuvent pas contenir plusieurs fenêtre enfant.  
  
 **CReBar** utilise la classe de [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) pour fournir son implémentation.  Vous pouvez accéder au contrôle rebar via [GetReBarCtrl](../Topic/CReBar::GetReBarCtrl.md) pour tirer parti des options de personnalisation du contrôle.  Pour plus d'informations sur les contrôles, rebar consultez l' `CReBarCtrl`.  Pour plus d'informations sur l'utilisation des contrôles, rebar consultez l' [Utilisation CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
> [!CAUTION]
>  Les objets de contrôle rebar rebar et ne prennent pas en charge l'ancrage de la barre de contrôle MFC.  Si **CRebar::EnableDocking** est appelé, votre application affirmera.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CReBar`  
  
## Configuration requise  
 **Header:** afxext.h  
  
## Voir aussi  
 [MFC exemple MFCIE](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)