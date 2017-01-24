---
title: "Date and Time: Automation Support | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "adding dates"
  - "Automation, date and time support"
  - "calculating dates and times"
  - "calculs, date et heure"
  - "COleDateTime class, Automation date/time support"
  - "COleDateTimeSpan class, Automation date/time support"
  - "dates, Automation support"
  - "temps écoulé, calculating in Automation"
  - "mettre en forme (Visual Studio), dates"
  - "mettre en forme (Visual Studio), heure"
  - "heure (Visual Studio), Automation support"
ms.assetid: 6eee94c4-943d-4ffc-bf7c-bdda89337ab0
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Date and Time: Automation Support
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment tirer parti des services de bibliothèque de classes connexes jusqu'à présent et de la gestion de la durée.  Les procédures décrites incluent :  
  
-   [Obtention du temps actuellement](../atl-mfc-shared/current-time-automation-classes.md)  
  
-   [Temps écoulé](../atl-mfc-shared/elapsed-time-automation-classes.md)  
  
-   [Mise en forme d'une représentation sous forme de chaîne d'une date\/heure](../atl-mfc-shared/formatting-time-automation-classes.md)  
  
 La classe de [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) permet de représenter des informations d'horodatage.  Il fournit une granularité plus fine et une plage supérieur à la classe de [CTime](../atl-mfc-shared/reference/ctime-class.md) .  La classe de [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) représente le temps écoulé, telles que la différence entre deux objets d' `COleDateTime` .  
  
 Les classes d' `COleDateTime` et d' `COleDateTimeSpan` sont conçues pour être utilisées avec la classe d' `COleVariant` utilisée dans l'automation.  `COleDateTime` et `COleDateTimeSpan` sont également utiles en programmation de bases de données MFC, mais elles peuvent être utilisées chaque fois que vous souhaitez manipuler les valeurs de date et d'heure.  Bien que la classe d' `COleDateTime` a une plage de valeurs supérieures et la granularité plus fine que la classe d' `CTime` , il requiert plus de mémoire pour chaque objet qu' `CTime`.  Il existe également des considérations spéciales lorsque vous utilisez le type sous\-jacent de **DATE** .  Consultez [Le type de DATE](../atl-mfc-shared/date-type.md) pour plus d'informations sur l'implémentation de **DATE**.  
  
 Les objets d'`COleDateTime` peuvent être utilisés pour représenter des dates entre le le 1er janvier, 100, et le 31 décembre, 9999.  Les objets d'`COleDateTime` sont des valeurs à virgule flottante, avec une résolution approximative de 1 millisecondes.  `COleDateTime` est basé sur le type de données de **DATE** , défini dans la documentation MFC sous [DATE de COleDateTime::operator](../Topic/COleDateTime::operator%20DATE.md).  L'implémentation réelle de **DATE** étend au delà de ces limites l'.  L'implémentation d' `COleDateTime` applique ces limites pour faciliter l'utilisation de la classe.  
  
 `COleDateTime` ne prend pas en charge les dates julien.  Il est supposé que le calendrier grégorien étend en arrière dans le temps au 1er janvier, 100.  
  
 `COleDateTime` ignore l'heure d'été \(DST\).  L'exemple de code suivant compare deux méthodes de calculer un intervalle de temps qui traverse la date de basculement de Desktop prise en charge Technician : un à l'aide de le CRT, et l'autre à l'aide de `COleDateTime`.  Commutateurs de Desktop prise en charge Technician plus de, dans la plupart des paramètres régionaux, dans la deuxième semaine en avril et le troisième en octobre.  
  
 La première méthode définit deux objets d' `CTime` , *time1* et *time2*, le 5 avril et au 6 avril respectivement, en utilisant les structures **tm** et `time_t`C de standard.  Le code affiche *time1* et *time2* et l'intervalle entre eux.  
  
 La deuxième méthode crée deux objets, `oletime1` et `oletime2`d' `COleDateTime` , et les place les mêmes dates que *time1* et *time2*.  Elle affiche `oletime1` et `oletime2` et l'intervalle entre eux.  
  
 Le CRT calcule correctement une différence de 23 heures.  `COleDateTimeSpan` calcule la différence de 24 heures.  
  
 Notez qu'une solution de contournement est utilisée à l'approche de la fin de l'exemple pour afficher la date correctement à `COleDateTime::Format`.  Consultez l'article de la Base de connaissances « INTRODUIRE DES ERREURS POUR TESTS : Mettez en forme \(« %D »\) échoue pour `COleDateTime` et `COleDateTimeSpan` » \(Q167338\).  
  
 [!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/CPP/date-and-time-automation-support_1.cpp)]  
  
## Voir aussi  
 [Date and Time](../atl-mfc-shared/date-and-time.md)