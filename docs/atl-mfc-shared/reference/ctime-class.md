---
title: "CTime Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CTime"
  - "CTime"
  - "ATL::CTime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTime class"
  - "shared classes, CTime"
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CTime Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une date et une heure absolue.  
  
## Syntaxe  
  
```  
class CTime  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CTime::CTime](../Topic/CTime::CTime.md)|Construit des objets d' `CTime` de plusieurs façons.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CTime::Format](../Topic/CTime::Format.md)|Convertit un objet d' `CTime` dans un basé sur une chaîne mise en forme du fuseau horaire local.|  
|[CTime::FormatGmt](../Topic/CTime::FormatGmt.md)|Convertit un objet d' `CTime` dans un basé sur une chaîne mise en forme sur l'heure UTC.|  
|[CTime::GetAsDBTIMESTAMP](../Topic/CTime::GetAsDBTIMESTAMP.md)|Convertit l'indication d'heure stockée dans l'objet d' `CTime` à une structure de Win32\-compatible <xref:System.Data.OleDb.OleDbType> .|  
|[CTime::GetAsSystemTime](../Topic/CTime::GetAsSystemTime.md)|Convertit l'indication d'heure stockée dans l'objet d' `CTime` à une structure de Win32\-compatible [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) .|  
|[CTime::GetCurrentTime](../Topic/CTime::GetCurrentTime.md)|Crée un objet d' `CTime` qui représente l'heure actuelle \(fonction membre statique\).|  
|[CTime::GetDay](../Topic/CTime::GetDay.md)|Retourne le jour représentent par l'objet d' `CTime` .|  
|[CTime::GetDayOfWeek](../Topic/CTime::GetDayOfWeek.md)|Retourne le jour de la semaine représentée par l'objet d' `CTime` .|  
|[CTime::GetGmtTm](../Topic/CTime::GetGmtTm.md)|Détaille un objet d' `CTime` en composants — en heure UTC.|  
|[CTime::GetHour](../Topic/CTime::GetHour.md)|Retourne l'heure représentée par l'objet d' `CTime` .|  
|[CTime::GetLocalTm](../Topic/CTime::GetLocalTm.md)|Détaille un objet d' `CTime` en composants \(selon le fuseau horaire local.|  
|[CTime::GetMinute](../Topic/CTime::GetMinute.md)|Retourne la minute représentée par l'objet d' `CTime` .|  
|[CTime::GetMonth](../Topic/CTime::GetMonth.md)|Retourne le mois représenté par l'objet d' `CTime` .|  
|[CTime::GetSecond](../Topic/CTime::GetSecond.md)|Retourne le deuxième représenté par l'objet d' `CTime` .|  
|[CTime::GetTime](../Topic/CTime::GetTime.md)|Retourne une valeur de **\_\_time64\_t** pour l'objet donné d' `CTime` .|  
|[CTime::GetYear](../Topic/CTime::GetYear.md)|Retourne l'année représentée par l'objet d' `CTime` .|  
|[CTime::Serialize64](../Topic/CTime::Serialize64.md)|Sérialise les données vers ou d'une archive.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \+ \)](../Topic/CTime::operator%20+,%20-.md)|Ces opérateurs d'ajout et soustraient `CTimeSpan` et les objets d' `CTime` .|  
|[opérateur \+, – \=](../Topic/CTime::operator%20+=,%20-=.md)|Ces opérateurs d'ajout et soustraient un objet d' `CTimeSpan` à partir de cet objet d' `CTime` .|  
|[opérateur \=](../Topic/CTime::operator%20=.md)|l'opérateur d'assignation.|  
|[\=\= d'opérateur, \<, etc..](../Topic/CTime%20Comparison%20Operators.md)|Opérateurs de comparaison.|  
  
## Notes  
 `CTime` n'a pas de classe de base.  
  
 Les valeurs d'`CTime` ont lieu selon le temps universel coordonné \(UTC\), qui équivaut au temps universel \(universal, universal time\).  Consultez [Gestion du temps](../../c-runtime-library/time-management.md) pour plus d'informations sur la façon dont le fuseau horaire est déterminé.  
  
 Lorsque vous créez un objet d' `CTime` , affectez au paramètre d' `nDST` à 0 pour indiquer que l'heure d'hiver est appliquée, ou une valeur supérieure à 0 pour indiquer que l'heure d'été est appliquée, ou une valeur inférieure de zéro pour que le calcul de code de la bibliothèque Runtime C si l'heure d'hiver ou l'heure d'été est appliquée.  `tm_isdst` est un champ obligatoire.  Si sa valeur, sa valeur est non définie et la valeur de retour de [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) est imprévisible.  Si les points d' `timeptr` à une structure de TM retourné par un appel précédent à [asctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), à [\_gmtime\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), ou à [localtime\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), le champ d' `tm_isdst` contient la valeur correcte.  
  
 Une classe auxiliaire, [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), représente un intervalle de temps.  
  
 Les classes d' `CTime` et d' `CTimeSpan` ne sont pas conçus pour la dérivation.  Étant donné qu'il n'y a aucune fonction virtuelle, la taille d' `CTime` et les objets d' `CTimeSpan` est exactement à 8 octets.  La plupart des fonctions membres sont inline.  
  
> [!NOTE]
>  La date limite supérieure est 12\/31\/3000.  La limite inférieure est 1\/1\/1970 12h00 : 0h du matin GMT.  
  
 Pour plus d'informations sur l'utilisation `CTime`, consultez les articles [date et heure](../../atl-mfc-shared/date-and-time.md), et le [Gestion de la durée](../../c-runtime-library/time-management.md) dans la référence de la bibliothèque Runtime.  
  
> [!NOTE]
>  `CTime` MFC modifié par structure MFC 7,1 à 8,0.  Si vous sérialisez une structure d' `CTime` à l'aide de `operator <<` sous MFC 8,0 ou une version ultérieure, le fichier résultant n'est pas accessible en lecture sur les versions antérieures MFC.  
  
## Configuration requise  
 **en\-tête :** atltime.h  
  
## Voir aussi  
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [CTimeSpan Class](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)