---
title: "CMonthCalCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMonthCalCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMonthCalCtrl class"
  - "contrôles communs, Internet Explorer 4.0"
  - "Internet Explorer 4.0 common controls"
  - "month calendar controls"
  - "month calendar controls, CMonthCalCtrl class"
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CMonthCalCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule les fonctionnalités d'un contrôle month calendar.  
  
## Syntaxe  
  
```  
class CMonthCalCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMonthCalCtrl::CMonthCalCtrl](../Topic/CMonthCalCtrl::CMonthCalCtrl.md)|Construit un objet `CMonthCalCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMonthCalCtrl::Create](../Topic/CMonthCalCtrl::Create.md)|Crée un contrôle month calendar et l'attache à l'objet d' `CMonthCalCtrl` .|  
|[CMonthCalCtrl::GetCalendarBorder](../Topic/CMonthCalCtrl::GetCalendarBorder.md)|Extrait la largeur de la bordure du contrôle month calendar actuel.|  
|[CMonthCalCtrl::GetCalendarCount](../Topic/CMonthCalCtrl::GetCalendarCount.md)|Récupère le nombre de calendriers affichés dans le contrôle month calendar actuel.|  
|[CMonthCalCtrl::GetCalendarGridInfo](../Topic/CMonthCalCtrl::GetCalendarGridInfo.md)|Récupère des informations sur le contrôle month calendar actuel.|  
|[CMonthCalCtrl::GetCalID](../Topic/CMonthCalCtrl::GetCalID.md)|Récupère l'identificateur de calendrier pour le contrôle month calendar actuel.|  
|[CMonthCalCtrl::GetColor](../Topic/CMonthCalCtrl::GetColor.md)|Obtient la couleur d'un champ spécifié d'un contrôle month calendar.|  
|[CMonthCalCtrl::GetCurrentView](../Topic/CMonthCalCtrl::GetCurrentView.md)|Extrait la vue qui est affichée par le contrôle month calendar actuel.|  
|[CMonthCalCtrl::GetCurSel](../Topic/CMonthCalCtrl::GetCurSel.md)|Récupère l'heure système comme indiqué à la date actuellement sélectionnée.|  
|[CMonthCalCtrl::GetFirstDayOfWeek](../Topic/CMonthCalCtrl::GetFirstDayOfWeek.md)|Obtient le premier jour de la semaine pour être affiché dans la colonne la plus à gauche du calendrier.|  
|[CMonthCalCtrl::GetMaxSelCount](../Topic/CMonthCalCtrl::GetMaxSelCount.md)|Récupère le nombre maximal actuel de jours qui peuvent être sélectionnés dans un contrôle month calendar.|  
|[CMonthCalCtrl::GetMaxTodayWidth](../Topic/CMonthCalCtrl::GetMaxTodayWidth.md)|Extrait la largeur maximale de « today chaîne » pour le contrôle month calendar actuel.|  
|[CMonthCalCtrl::GetMinReqRect](../Topic/CMonthCalCtrl::GetMinReqRect.md)|Extrait la taille minimale requise afficher un mois complet dans un contrôle month calendar.|  
|[CMonthCalCtrl::GetMonthDelta](../Topic/CMonthCalCtrl::GetMonthDelta.md)|Extrait la vitesse de défilement pour un contrôle month calendar.|  
|[CMonthCalCtrl::GetMonthRange](../Topic/CMonthCalCtrl::GetMonthRange.md)|Récupère des informations de date qui représente les limites de ciel et monde de l'affichage d'un contrôle month calendar.|  
|[CMonthCalCtrl::GetRange](../Topic/CMonthCalCtrl::GetRange.md)|Récupère le minimum actuel et les dates maximales fixés dans un contrôle month calendar.|  
|[CMonthCalCtrl::GetSelRange](../Topic/CMonthCalCtrl::GetSelRange.md)|Récupère des informations de date qui représente les limites supérieures et inférieures de la plage de dates sélectionnée par l'utilisateur.|  
|[CMonthCalCtrl::GetToday](../Topic/CMonthCalCtrl::GetToday.md)|Récupère des informations de date pour la date en tant que « today » pour un contrôle month calendar.|  
|[CMonthCalCtrl::HitTest](../Topic/CMonthCalCtrl::HitTest.md)|Détermine laquelle la section d'un contrôle month calendar correspond à un point donné sur l'écran.|  
|[CMonthCalCtrl::IsCenturyView](../Topic/CMonthCalCtrl::IsCenturyView.md)|Indique si l'affichage actuel du contrôle month calendar en cours est la vue de siècle.|  
|[CMonthCalCtrl::IsDecadeView](../Topic/CMonthCalCtrl::IsDecadeView.md)|Indique si l'affichage actuel du contrôle month calendar en cours est la vue décennie.|  
|[CMonthCalCtrl::IsMonthView](../Topic/CMonthCalCtrl::IsMonthView.md)|Indique si l'affichage actuel du contrôle month calendar en cours est la vue du mois.|  
|[CMonthCalCtrl::IsYearView](../Topic/CMonthCalCtrl::IsYearView.md)|Indique si l'affichage actuel du contrôle month calendar en cours est la vue d'année.|  
|[CMonthCalCtrl::SetCalendarBorder](../Topic/CMonthCalCtrl::SetCalendarBorder.md)|Définit la largeur de la bordure du contrôle month calendar actuel.|  
|[CMonthCalCtrl::SetCalendarBorderDefault](../Topic/CMonthCalCtrl::SetCalendarBorderDefault.md)|Définit la largeur par défaut de la bordure du contrôle month calendar actuel.|  
|[CMonthCalCtrl::SetCalID](../Topic/CMonthCalCtrl::SetCalID.md)|Définit l'identificateur de calendrier pour le contrôle month calendar actuel.|  
|[CMonthCalCtrl::SetCenturyView](../Topic/CMonthCalCtrl::SetCenturyView.md)|Définit le contrôle month calendar actuel pour afficher la vue de siècle.|  
|[CMonthCalCtrl::SetColor](../Topic/CMonthCalCtrl::SetColor.md)|Définit la couleur d'un champ spécifié d'un contrôle month calendar.|  
|[CMonthCalCtrl::SetCurrentView](../Topic/CMonthCalCtrl::SetCurrentView.md)|Définit le contrôle month calendar actuel pour afficher la vue spécifiée.|  
|[CMonthCalCtrl::SetCurSel](../Topic/CMonthCalCtrl::SetCurSel.md)|Définit la date sélectionnée pour un contrôle month calendar.|  
|[CMonthCalCtrl::SetDayState](../Topic/CMonthCalCtrl::SetDayState.md)|Définit l'affichage pour les jours dans un contrôle month calendar.|  
|[CMonthCalCtrl::SetDecadeView](../Topic/CMonthCalCtrl::SetDecadeView.md)|Définit le contrôle month calendar actuel en mode décennie.|  
|[CMonthCalCtrl::SetFirstDayOfWeek](../Topic/CMonthCalCtrl::SetFirstDayOfWeek.md)|Définit le jour de la semaine à afficher dans la colonne la plus à gauche du calendrier.|  
|[CMonthCalCtrl::SetMaxSelCount](../Topic/CMonthCalCtrl::SetMaxSelCount.md)|Définit le nombre de jours qui peuvent être sélectionnés dans un contrôle month calendar.|  
|[CMonthCalCtrl::SetMonthDelta](../Topic/CMonthCalCtrl::SetMonthDelta.md)|Définit la vitesse de défilement pour un contrôle month calendar.|  
|[CMonthCalCtrl::SetMonthView](../Topic/CMonthCalCtrl::SetMonthView.md)|Définit le contrôle month calendar actuel pour afficher la vue du mois.|  
|[CMonthCalCtrl::SetRange](../Topic/CMonthCalCtrl::SetRange.md)|Définit le minimum et le maximum autorisé date pour un contrôle month calendar.|  
|[CMonthCalCtrl::SetSelRange](../Topic/CMonthCalCtrl::SetSelRange.md)|Définit la sélection d'un contrôle month calendar à une plage de dates donnée.|  
|[CMonthCalCtrl::SetToday](../Topic/CMonthCalCtrl::SetToday.md)|Définit le contrôle calendar pour le jour actuel.|  
|[CMonthCalCtrl::SetYearView](../Topic/CMonthCalCtrl::SetYearView.md)|Définit le contrôle month calendar actuel en mode d'année.|  
|[CMonthCalCtrl::SizeMinReq](../Topic/CMonthCalCtrl::SizeMinReq.md)|Redessine le contrôle month calendar à son minimum, taille d'un mois.|  
|[CMonthCalCtrl::SizeRectToMin](../Topic/CMonthCalCtrl::SizeRectToMin.md)|Pour le contrôle month calendar actuel, calcule le plus petit rectangle qui peut contenir tous les calendriers qui correspondent dans un rectangle spécifié.|  
  
## Notes  
 Le contrôle month calendar fournit à l'utilisateur une interface simple de calendrier, de laquelle l'utilisateur peut sélectionner une date.  L'utilisateur peut modifier l'affichage par :  
  
-   Défilement arrière et effectuent le suivi, de mois en mois.  
  
-   En cliquant sur aujourd'hui texte à afficher le jour actuel \(si le style de **MCS\_NOTODAY** n'est pas utilisé\).  
  
-   Choisir un mois ou une année d'un menu contextuel.  
  
 Vous pouvez personnaliser le contrôle month calendar en appliquant divers styles à l'objet lors de sa création.  Ces styles sont décrits dans [styles de contrôle month calendar](http://msdn.microsoft.com/library/windows/desktop/bb760919) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Le contrôle month calendar peut afficher plusieurs mois, elle peut indiquer les jours spéciaux \(tels que les jours fériés\) en gras par la date.  
  
 Pour plus d'informations sur l'utilisation du contrôle month calendar, consultez l' [Utilisation CMonthCalCtrl](../../mfc/using-cmonthcalctrl.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CMonthCalCtrl`  
  
## Configuration requise  
 **Header:** afxdtctl.h  
  
## Voir aussi  
 [MFC exemple CMNCTRL1](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDateTimeCtrl Class](../../mfc/reference/cdatetimectrl-class.md)