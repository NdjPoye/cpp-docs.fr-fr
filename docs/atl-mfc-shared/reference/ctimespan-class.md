---
title: "CTimeSpan Class | Microsoft Docs"
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
  - "ATL.CTimeSpan"
  - "CTimeSpan"
  - "timespan"
  - "ATL::CTimeSpan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTimeSpan class"
  - "temps écoulé, CTimeSpan object"
  - "shared classes, CTimeSpan"
  - "time span"
  - "heure, elapsed"
  - "timespan"
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
caps.latest.revision: 17
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTimeSpan Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une durée, en interne stockée en tant que nombre de secondes dans l'intervalle.  
  
## Syntaxe  
  
```  
class CTimeSpan  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CTimeSpan::CTimeSpan](../Topic/CTimeSpan::CTimeSpan.md)|Construit des objets d' `CTimeSpan` de plusieurs façons.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CTimeSpan::Format](../Topic/CTimeSpan::Format.md)|Convertit `CTimeSpan` dans une chaîne mise en forme.|  
|[CTimeSpan::GetDays](../Topic/CTimeSpan::GetDays.md)|Retourne une valeur qui représente le nombre de jours complets dans cet `CTimeSpan`.|  
|[CTimeSpan::GetHours](../Topic/CTimeSpan::GetHours.md)|Retourne une valeur qui représente le nombre d'heures dans le jour actuel \(– 23 à 23\).|  
|[CTimeSpan::GetMinutes](../Topic/CTimeSpan::GetMinutes.md)|Retourne une valeur qui représente le nombre de minutes dans l'heure actuelle \(– 59 à 59\).|  
|[CTimeSpan::GetSeconds](../Topic/CTimeSpan::GetSeconds.md)|Retourne une valeur qui représente le nombre de secondes dans la minute actuelle \(– 59 à 59\).|  
|[CTimeSpan::GetTimeSpan](../Topic/CTimeSpan::GetTimeSpan.md)|Retourne la valeur de l'objet `CTimeSpan`.|  
|[CTimeSpan::GetTotalHours](../Topic/CTimeSpan::GetTotalHours.md)|Retourne une valeur qui représente le nombre total d'heures complètes dans cet `CTimeSpan`.|  
|[CTimeSpan::GetTotalMinutes](../Topic/CTimeSpan::GetTotalMinutes.md)|Retourne une valeur qui représente le nombre de minutes complètes dans cet `CTimeSpan`.|  
|[CTimeSpan::GetTotalSeconds](../Topic/CTimeSpan::GetTotalSeconds.md)|Retourne une valeur qui représente le nombre de secondes complètes dans cet `CTimeSpan`.|  
|[CTimeSpan::Serialize64](../Topic/CTimeSpan::Serialize64.md)|Sérialise les données vers ou d'une archive.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \+ \)](../Topic/CTimeSpan::operator%20+,%20-.md)|Ajoute et soustrait des objets d' `CTimeSpan` .|  
|[opérateur \+\= – \=](../Topic/CTimeSpan::operator%20+=,%20-=.md)|Ajoute et soustrait un objet d' `CTimeSpan` à partir de cet `CTimeSpan`.|  
|[\=\= d'opérateur \< etc..](../Topic/CTimeSpan%20Comparison%20Operators.md)|Compare deux valeurs d'heure connexes.|  
  
## Notes  
 `CTimeSpan` n'a pas de classe de base.  
  
 Les fonctions d'`CTimeSpan` convertissent des secondes à différentes combinaisons de jours, les heures, les minutes, et les secondes.  
  
 L'objet d' `CTimeSpan` est stocké dans une structure de **\_\_time64\_t** , qui est de 8 octets.  
  
 Une classe auxiliaire, [CTime](../../atl-mfc-shared/reference/ctime-class.md), représente une heure absolue.  
  
 Les classes d' `CTime` et d' `CTimeSpan` ne sont pas conçus pour la dérivation.  Étant donné qu'il n'y a aucune fonction virtuelle, la taille des deux objets d' `CTime` et d' `CTimeSpan` est exactement à 8 octets.  La plupart des fonctions membres sont inline.  
  
 Pour plus d'informations sur l'utilisation `CTimeSpan`, consultez les articles [date et heure](../../atl-mfc-shared/date-and-time.md), et le [Gestion de la durée](../../c-runtime-library/time-management.md) dans *la référence de la bibliothèque Runtime*.  
  
## Configuration requise  
 **Header:** atltime.h  
  
## Voir aussi  
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)