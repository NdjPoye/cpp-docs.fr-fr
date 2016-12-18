---
title: "Date and Time | Microsoft Docs"
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
  - "dates, MFC"
  - "MFC, date et heure"
  - "heure"
  - "heure, programmer MFC"
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Date and Time
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC prend en charge plusieurs manières d'utiliser des dates et des heures.  Ces niveaux sont les suivants :  
  
-   Classes à caractère général de temps.  Les classes de [CTime](../atl-mfc-shared/reference/ctime-class.md) et de [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md) encapsulent la plupart des fonctionnalités associée à la bibliothèque d'heure d'hiver, qui est déclarée dans TIME.H.  
  
-   Prise en charge de l'horloge système.  Avec la version 3,0 des MFC, la prise en charge a été ajouté à `CTime` pour Win32 `SYSTEMTIME` et des types de données d' `FILETIME` .  
  
-   Prise en charge de l'automation [type de données date](../atl-mfc-shared/date-type.md).  Prend en charge**DATE** de date, chronomètrent, et les valeur de date\/d'heure.  Les classes de [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) et de [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) encapsulent cette fonctionnalité.  Elles utilisent la classe de [COleVariant](../mfc/reference/colevariant-class.md) grâce à la prise en charge de l'automation.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Date et heure : classes à caractère général](../atl-mfc-shared/date-and-time-general-purpose-classes.md)  
  
-   [Date et heure : Prise en charge de SYSTEMTIME](../atl-mfc-shared/date-and-time-systemtime-support.md)  
  
-   [Date et heure : Prise en charge d'automation](../atl-mfc-shared/date-and-time-automation-support.md)  
  
-   [Date et heure : prise en charge des bases de données](../atl-mfc-shared/date-and-time-database-support.md)  
  
## Voir aussi  
 [Concepts](../mfc/mfc-concepts.md)   
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)