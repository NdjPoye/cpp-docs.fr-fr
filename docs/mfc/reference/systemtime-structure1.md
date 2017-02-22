---
title: "SYSTEMTIME Structure1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SYSTEMTIME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SYSTEMTIME (structure)"
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# SYSTEMTIME, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `SYSTEMTIME` représente une date et une heure qui utilise différents membres pour le mois, le jour, l'année, le jour de la semaine, l'heure, la minute, la seconde et la milliseconde.  
  
## Syntaxe  
  
```  
  
      typedef struct _SYSTEMTIME {  
   WORD wYear;  
   WORD wMonth;  
   WORD wDayOfWeek;  
   WORD wDay;  
   WORD wHour;  
   WORD wMinute;  
   WORD wSecond;  
   WORD wMilliseconds;  
} SYSTEMTIME;  
```  
  
#### Paramètres  
 *wYear*  
 Année en cours.  
  
 *wMonth*  
 Mois actuel. Janvier correspond à 1.  
  
 *wDayOfWeek*  
 Jour actuel de la semaine. Dimanche correspond à 0, lundi à 1, etc.  
  
 *wDay*  
 Jour du mois actuel.  
  
 *wHour*  
 Heure en cours.  
  
 *wMinute*  
 Minute en cours.  
  
 *wSecond*  
 Seconde en cours.  
  
 *wMillisecondes*  
 Milliseconde en cours.  
  
## Exemple  
 [!code-cpp[NVC_MFC_Utilities#39](../../mfc/codesnippet/CPP/systemtime-structure1_1.cpp)]  
  
## Configuration requise  
 **En\-tête :** winbase.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../Topic/CTime::CTime.md)