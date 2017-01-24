---
title: "COleDateTime Class | Microsoft Docs"
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
  - "COleDateTime"
  - "ATL.COleDateTime"
  - "ATL::COleDateTime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDateTime class"
  - "Date (type de données), MFC encapsulation of"
  - "dates, handling in MFC"
  - "shared classes, COleDateTime"
  - "heure, handling in MFC"
  - "time-only values"
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
caps.latest.revision: 34
caps.handback.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDateTime Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule le type de données d' `DATE` utilisé dans OLE automation.  
  
## Syntaxe  
  
```  
class COleDateTime  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDateTime::COleDateTime](../Topic/COleDateTime::COleDateTime.md)|Construit un objet `COleDateTime`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDateTime::Format](../Topic/COleDateTime::Format.md)|Génère une représentation sous forme de chaîne mise en forme d'un objet d' `COleDateTime` .|  
|[COleDateTime::GetAsDBTIMESTAMP](../Topic/COleDateTime::GetAsDBTIMESTAMP.md)|Appelez cette méthode pour obtenir l'heure de l'objet d' `COleDateTime` une structure de données de **DBTIMESTAMP** .|  
|[COleDateTime::GetAsSystemTime](../Topic/COleDateTime::GetAsSystemTime.md)|Appelez cette méthode pour obtenir l'heure de l'objet d' `COleDateTime` une structure de données de [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) .|  
|[COleDateTime::GetAsUDATE](../Topic/COleDateTime::GetAsUDATE.md)|Appelez cette méthode pour obtenir l'heure dans `COleDateTime` une structure de données d' **UDATE** .|  
|[COleDateTime::GetCurrentTime](../Topic/COleDateTime::GetCurrentTime.md)|Crée un objet d' `COleDateTime` qui représente l'heure actuelle \(fonction membre statique\).|  
|[COleDateTime::GetDay](../Topic/COleDateTime::GetDay.md)|Retourne le jour dans lequel cet objet d' `COleDateTime` représente \(1 à 31\).|  
|[COleDateTime::GetDayOfWeek](../Topic/COleDateTime::GetDayOfWeek.md)|Retourne le jour de la semaine dans lequel cet objet d' `COleDateTime` représente \(dimanche \= 1\).|  
|[COleDateTime::GetDayOfYear](../Topic/COleDateTime::GetDayOfYear.md)|Retourne le jour de l'année où cet objet d' `COleDateTime` représente \(1er janvier \= 1\).|  
|[COleDateTime::GetHour](../Topic/COleDateTime::GetHour.md)|Retourne l'heure de cet objet d' `COleDateTime` représente \(0 à 23\).|  
|[COleDateTime::GetMinute](../Topic/COleDateTime::GetMinute.md)|Retourne la minute où cet objet d' `COleDateTime` représente \(0 à 59\).|  
|[COleDateTime::GetMonth](../Topic/COleDateTime::GetMonth.md)|Retourne le mois dans lequel cet objet d' `COleDateTime` représente \(1 à 12\).|  
|[COleDateTime::GetSecond](../Topic/COleDateTime::GetSecond.md)|Retourne le deuxième cet objet d' `COleDateTime` représente \(0 à 59\).|  
|[COleDateTime::GetStatus](../Topic/COleDateTime::GetStatus.md)|Obtient l'état \(validité\) de cet objet d' `COleDateTime` .|  
|[COleDateTime::GetYear](../Topic/COleDateTime::GetYear.md)|Retourne l'année où cet objet d' `COleDateTime` représente.|  
|[COleDateTime::ParseDateTime](../Topic/COleDateTime::ParseDateTime.md)|Lit une valeur de date\/heure d'une chaîne et définit la valeur d' `COleDateTime`.|  
|[COleDateTime::SetDate](../Topic/COleDateTime::SetDate.md)|Définit la valeur de cet objet d' `COleDateTime` à la valeur réservée à la date.|  
|[COleDateTime::SetDateTime](../Topic/COleDateTime::SetDateTime.md)|Définit la valeur de cet objet d' `COleDateTime` au valeur de date\/d'heure spécifié.|  
|[COleDateTime::SetStatus](../Topic/COleDateTime::SetStatus.md)|Définit l'état \(validité\) de cet objet d' `COleDateTime` .|  
|[COleDateTime::SetTime](../Topic/COleDateTime::SetTime.md)|Définit la valeur de cet objet d' `COleDateTime` à la valeur réservée à la fois spécifiée.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[\=\= De COleDateTime::operator, COleDateTime::operator \<, etc..](../Topic/COleDateTime%20Relational%20Operators.md)|Compare deux valeurs d' `COleDateTime` .|  
|[COleDateTime::operator \+, \- COleDateTime::operator](../Topic/COleDateTime::operator%20+,%20-.md)|Ajoutez et soustrayez les valeurs d' `COleDateTime` .|  
|[COleDateTime::operator \+\=, COleDateTime::operator \- \=](../Topic/COleDateTime::operator%20+=,%20-=.md)|Ajoutez et soustraire une valeur d' `COleDateTime` de cet objet d' `COleDateTime` .|  
|[COleDateTime::operator \=](../Topic/COleDateTime::operator%20=.md)|Copie une valeur d' `COleDateTime` .|  
|[DATE de COleDateTime::operator, COleDateTime::operator Date\*](../Topic/COleDateTime::operator%20DATE.md)|Convertit une valeur d' `COleDateTime` dans `DATE` ou `DATE*`.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDateTime::m\_dt](../Topic/COleDateTime::m_dt.md)|Contient **DATE** sous\-jacent pour cet objet d' `COleDateTime` .|  
|[COleDateTime::m\_status](../Topic/COleDateTime::m_status.md)|Contient l'état de cet objet d' `COleDateTime` .|  
  
## Notes  
 `COleDateTime` n'a pas de classe de base.  
  
 Elle est l'un des types possibles pour le type de données Variant OLE automation de.  Une valeur d' `COleDateTime` représente une valeur absolue de date et d'heure.  
  
 Le type d' `DATE` est implémenté comme une valeur à virgule flottante.  Les jours sont mesurés depuis le 30 décembre 1899, à minuit.  Le tableau suivant présente des dates et leurs valeurs associées :  
  
|Date|Valeur|  
|----------|------------|  
|29 décembre 1899, Minuit|\-1.0|  
|29 décembre 1899, 6 Du matin|\-1.25|  
|30 décembre 1899, Minuit|0.0|  
|31 décembre 1899, Minuit|1.0|  
|1er janvier 1900, 6h du matin..|2.25|  
  
> [!CAUTION]
>  Remarque dans le tableau au\-dessus de ce même si les valeurs du jour sont négatives avant minuit le 30 décembre 1899, les valeurs d'heure ne stocke pas.  Par exemple, le 6h00 du matin est toujours représenté par une valeur fractionnaire 0,25 que l'entier représentant le niveau est positif \(après le 30 décembre 1899\) ou négatif \(avant le 30 décembre 1899\).  Cela signifie qu'une comparaison simple de virgule flottante trierait à tort `COleDateTime` représentant le 6h00 du matin sur 12\/29\/1899 comme **later** qu'un 7h00 du matin de performances le même niveau.  
  
 La classe d' `COleDateTime` gère des dates, depuis le 1er janvier 100, jusqu'au 31 décembre, 9999.  La classe d' `COleDateTime` utilise le calendrier grégorien ; elle ne prend pas en charge les dates julien.  `COleDateTime` ignore l'heure d'été.  \(Consultez [date et heure : Prise en charge d'automation](../../atl-mfc-shared/date-and-time-automation-support.md).\)  
  
> [!NOTE]
>  Vous pouvez utiliser le format d' `%y` pour récupérer une année sur deux chiffres uniquement pour les dates commençant par 1900.  Si vous utilisez le format d' `%y` une date avant 1900, le code génère une erreur ASSERT.  
  
 Ce type est également utilisé pour représenter des valeurs réservées à la date ou uniquement à la fois.  Par convention, la date 0 \(30 décembre 1899\) est utilisée pour les valeurs réservées à la fois et le 0h00 de temps \(minuit\) est utilisée pour les valeurs réservées à la date.  
  
 Si vous créez un objet d' `COleDateTime` en utilisant une date moins de 100, la date est reçue, mais les appels suivants à `GetYear`, `GetMonth`, `GetDay`, `GetHour`, `GetMinute`, et l'échec et retourner \-1 d' `GetSecond` .  Précédemment, vous pouvez utiliser les dates à deux chiffres, mais les dates soient 100 ou plus importantes dans MFC 4,2 et versions ultérieures.  
  
 Pour éviter les problèmes, spécifiez une date à quatre chiffres.  Par exemple :  
  
 [!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/CPP/coledatetime-class_1.cpp)]  
  
 Les opérations arithmétiques de base pour les valeurs d' `COleDateTime` utilisent la classe [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)auxiliaires.  Les valeurs d'`COleDateTimeSpan` définissent un intervalle de temps.  La relation entre ces classes est similaire à celle entre [CTime](../../atl-mfc-shared/reference/ctime-class.md) et [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 Pour plus d'informations sur les classes d' `COleDateTime` et d' `COleDateTimeSpan` , consultez l'article [date et heure : Prise en charge d'automation](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## Configuration requise  
 **en\-tête :** ATLComTime.h  
  
## Voir aussi  
 [COleVariant Class](../../mfc/reference/colevariant-class.md)   
 [CTime Class](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan Class](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)