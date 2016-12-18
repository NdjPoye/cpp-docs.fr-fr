---
title: "CDateTimeCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDateTimeCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDateTimeCtrl class"
  - "date-picking functionality"
  - "DateTimePicker control [MFC]"
  - "DateTimePicker control [MFC], CDateTimeCtrl class"
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
caps.latest.revision: 23
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDateTimeCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule les fonctionnalités d'un contrôle Date aller\-retour Picker.  
  
## Syntaxe  
  
```  
class CDateTimeCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDateTimeCtrl::CDateTimeCtrl](../Topic/CDateTimeCtrl::CDateTimeCtrl.md)|Construit un objet `CDateTimeCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDateTimeCtrl::CloseMonthCal](../Topic/CDateTimeCtrl::CloseMonthCal.md)|Ferme le contrôle Picker aller\-retour Date actuelle.|  
|[CDateTimeCtrl::Create](../Topic/CDateTimeCtrl::Create.md)|Crée le contrôle Date aller\-retour Picker et l'attache à l'objet d' `CDateTimeCtrl` .|  
|[CDateTimeCtrl::GetDateTimePickerInfo](../Topic/CDateTimeCtrl::GetDateTimePickerInfo.md)|Récupère des informations sur le contrôle Picker aller\-retour Date actuelle.|  
|[CDateTimeCtrl::GetIdealSize](../Topic/CDateTimeCtrl::GetIdealSize.md)|Retourne la taille idéale du contrôle Date aller\-retour Picker requis pour afficher la date du jour ou l'heure.|  
|[CDateTimeCtrl::GetMonthCalColor](../Topic/CDateTimeCtrl::GetMonthCalColor.md)|Extrait la couleur pour une partie donnée du calendrier mensuel dans le contrôle Date aller\-retour Picker.|  
|[CDateTimeCtrl::GetMonthCalCtrl](../Topic/CDateTimeCtrl::GetMonthCalCtrl.md)|Récupère l'objet d' `CMonthCalCtrl` associé au contrôle Date aller\-retour Picker.|  
|[CDateTimeCtrl::GetMonthCalFont](../Topic/CDateTimeCtrl::GetMonthCalFont.md)|Extrait la police actuellement utilisée par le contrôle month calendar enfant du contrôle Date aller\-retour Picker.|  
|[CDateTimeCtrl::GetMonthCalStyle](../Topic/CDateTimeCtrl::GetMonthCalStyle.md)|Obtient le style du contrôle Picker aller\-retour Date actuelle.|  
|[CDateTimeCtrl::GetRange](../Topic/CDateTimeCtrl::GetRange.md)|Récupère le minimum actuel et les heures système données par maximale pour un contrôle Date aller\-retour Picker.|  
|[CDateTimeCtrl::GetTime](../Topic/CDateTimeCtrl::GetTime.md)|Récupère le temps actuellement sélectionné d'un contrôle Picker aller\-retour Date et le place dans une structure spécifiée d' `SYSTEMTIME` .|  
|[CDateTimeCtrl::SetFormat](../Topic/CDateTimeCtrl::SetFormat.md)|Définit l'affichage d'un contrôle Date aller\-retour Picker conformément à une chaîne de format donné.|  
|[CDateTimeCtrl::SetMonthCalColor](../Topic/CDateTimeCtrl::SetMonthCalColor.md)|Définit la couleur pour une partie donnée du calendrier mensuel dans un contrôle Date aller\-retour Picker.|  
|[CDateTimeCtrl::SetMonthCalFont](../Topic/CDateTimeCtrl::SetMonthCalFont.md)|Définit la police que le contrôle month calendar enfant du contrôle Date aller\-retour Picker utilisera.|  
|[CDateTimeCtrl::SetMonthCalStyle](../Topic/CDateTimeCtrl::SetMonthCalStyle.md)|Définit le style du contrôle Picker aller\-retour Date actuelle.|  
|[CDateTimeCtrl::SetRange](../Topic/CDateTimeCtrl::SetRange.md)|Définit le minimum et les heures système données par maximale pour un contrôle Date aller\-retour Picker.|  
|[CDateTimeCtrl::SetTime](../Topic/CDateTimeCtrl::SetTime.md)|Définit l'heure d'un contrôle Date aller\-retour Picker.|  
  
## Notes  
 Le contrôle Date aller\-retour Picker \(contrôle de DTP\) fournit une interface simple pour échanger des informations d'horodatage à un utilisateur.  Cette interface contient des champs, qui affiche une partie des informations d'horodatage stockées dans le contrôle.  L'utilisateur peut modifier les informations stockées dans le contrôle en modifiant le contenu de la chaîne dans un champ donné.  L'utilisateur peut déplacer du champ au champ à l'aide de la souris ou du clavier.  
  
 Vous pouvez personnaliser le contrôle Date aller\-retour Picker en appliquant divers styles à l'objet lors de sa création.  Consultez [Styles de contrôle Picker Date aller\-retour](http://msdn.microsoft.com/library/windows/desktop/bb761728) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d'informations sur les styles spécifiques au contrôle Date aller\-retour Picker.  Vous pouvez définir le format d'affichage du contrôle de DTP à l'aide de styles de format.  Ces styles de format sont décrits dans « styles de format » dans la rubrique [Styles de contrôle Picker Date aller\-retour](http://msdn.microsoft.com/library/windows/desktop/bb761728)d' [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] .  
  
 Le contrôle Date aller\-retour Picker utilise également les notifications et les rappels, décrites dans [Utilisation CDateTimeCtrl](../../mfc/using-cdatetimectrl.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDateTimeCtrl`  
  
## Configuration requise  
 **Header:** afxdtctl.h  
  
## Voir aussi  
 [MFC exemple CMNCTRL1](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CMonthCalCtrl Class](../../mfc/reference/cmonthcalctrl-class.md)