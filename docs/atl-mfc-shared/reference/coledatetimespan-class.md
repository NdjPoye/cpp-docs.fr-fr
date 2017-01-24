---
title: "COleDateTimeSpan Class | Microsoft Docs"
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
  - "ATL.COleDateTimeSpan"
  - "COleDateTimeSpan"
  - "ATL::COleDateTimeSpan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDateTimeSpan class"
  - "Date (type de données), MFC encapsulation of"
  - "shared classes, COleDateTimeSpan"
  - "time span"
  - "timespan"
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
caps.latest.revision: 19
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDateTimeSpan Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente un temps relatif, un intervalle de temps.  
  
## Syntaxe  
  
```  
class COleDateTimeSpan  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDateTimeSpan::COleDateTimeSpan](../Topic/COleDateTimeSpan::COleDateTimeSpan.md)|Construit un objet `COleDateTimeSpan`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDateTimeSpan::Format](../Topic/COleDateTimeSpan::Format.md)|Génère une représentation sous forme de chaîne mise en forme d'un objet d' `COleDateTimeSpan` .|  
|[COleDateTimeSpan::GetDays](../Topic/COleDateTimeSpan::GetDays.md)|Retourne la partie du jour de l'étendue que cet objet d' `COleDateTimeSpan` représente.|  
|[COleDateTimeSpan::GetHours](../Topic/COleDateTimeSpan::GetHours.md)|Retourne la partie de l'heure de l'étendue que cet objet d' `COleDateTimeSpan` représente.|  
|[COleDateTimeSpan::GetMinutes](../Topic/COleDateTimeSpan::GetMinutes.md)|Retourne la partie minutieuse de l'étendue que cet objet d' `COleDateTimeSpan` représente.|  
|[COleDateTimeSpan::GetSeconds](../Topic/COleDateTimeSpan::GetSeconds.md)|Retourne la deuxième partie de l'étendue que cet objet d' `COleDateTimeSpan` représente.|  
|[COleDateTimeSpan::GetStatus](../Topic/COleDateTimeSpan::GetStatus.md)|Obtient l'état \(validité\) de cet objet d' `COleDateTimeSpan` .|  
|[COleDateTimeSpan::GetTotalDays](../Topic/COleDateTimeSpan::GetTotalDays.md)|Retourne le nombre de jours que cet objet d' `COleDateTimeSpan` représente.|  
|[COleDateTimeSpan::GetTotalHours](../Topic/COleDateTimeSpan::GetTotalHours.md)|Retourne le nombre d'heures où cet objet d' `COleDateTimeSpan` représente.|  
|[COleDateTimeSpan::GetTotalMinutes](../Topic/COleDateTimeSpan::GetTotalMinutes.md)|Retourne le nombre de minutes où cet objet d' `COleDateTimeSpan` représente.|  
|[COleDateTimeSpan::GetTotalSeconds](../Topic/COleDateTimeSpan::GetTotalSeconds.md)|Retourne le nombre de secondes cet objet d' `COleDateTimeSpan` représente.|  
|[COleDateTimeSpan::SetDateTimeSpan](../Topic/COleDateTimeSpan::SetDateTimeSpan.md)|Définit la valeur de cet objet d' `COleDateTimeSpan` .|  
|[COleDateTimeSpan::SetStatus](../Topic/COleDateTimeSpan::SetStatus.md)|Définit l'état \(validité\) de cet objet d' `COleDateTimeSpan` .|  
  
### Opérateurs publics  
  
|||  
|-|-|  
|[opérateur \+, \-](../Topic/COleDateTimeSpan::operator%20+,%20-.md)|Ajoutez, soustrayez, puis modifiez le signe pour les valeurs d' `COleDateTimeSpan` .|  
|[opérateur \+, \- \=](../Topic/COleDateTimeSpan::operator%20+=,%20-=.md)|Ajoutez et soustraire une valeur d' `COleDateTimeSpan` de cette valeur d' `COleDateTimeSpan` .|  
|[opérateur \=](../Topic/COleDateTimeSpan::operator%20=.md)|Copie une valeur d' `COleDateTimeSpan` .|  
|[\=\= d'opérateur, \<, \<\=](../Topic/COleDateTimeSpan%20Relational%20Operators.md)|Compare deux valeurs d' `COleDateTimeSpan` .|  
|[double d'opérateur](../Topic/COleDateTimeSpan::operator%20double.md)|Convertit la valeur d' `COleDateTimeSpan` à **double**.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDateTimeSpan::m\_span](../Topic/COleDateTimeSpan::m_span.md)|Contient **double** sous\-jacent pour cet objet d' `COleDateTimeSpan` .|  
|[COleDateTimeSpan::m\_status](../Topic/COleDateTimeSpan::m_status.md)|Contient l'état de cet objet d' `COleDateTimeSpan` .|  
  
## Notes  
 `COleDateTimeSpan` n'a pas de classe de base.  
  
 `COleDateTimeSpan` conserve le temps en jours.  
  
 `COleDateTimeSpan` est utilisé avec sa classe [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)auxiliaires.  `COleDateTime` encapsule le type de données de **DATE** OLE automation de.  `COleDateTime` représente des valeurs d'heure absolues.  Tous les calculs d' `COleDateTime` comportent des valeurs d' `COleDateTimeSpan` .  La relation entre ces classes est analogue à celle entre [CTime](../../atl-mfc-shared/reference/ctime-class.md) et [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 Pour plus d'informations sur les classes d' `COleDateTime` et d' `COleDateTimeSpan` , consultez l'article [date et heure : Prise en charge d'automation](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## Configuration requise  
 **Header:** ATLComTime.h  
  
## Voir aussi  
 [COleDateTime Class](../../atl-mfc-shared/reference/coledatetime-class.md)   
 [CTime Class](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan Class](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)