---
title: "Date and Time: General-Purpose Classes | Microsoft Docs"
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
  - "date and time classes"
  - "time classes"
ms.assetid: b8115d7f-428a-4c41-9970-18502f2caca2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Date and Time: General-Purpose Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment tirer parti des services à caractère général de bibliothèque de classes connexes jusqu'à présent et de la gestion de la durée.  Les procédures décrites incluent :  
  
-   [Obtention du temps actuellement](../atl-mfc-shared/current-time-general-purpose-classes.md)  
  
-   [Temps écoulé](../atl-mfc-shared/elapsed-time-general-purpose-classes.md)  
  
-   [Mise en forme d'une représentation sous forme de chaîne d'une date\/heure](../atl-mfc-shared/formatting-time-values-general-purpose-classes.md)  
  
 La classe d' `CTime` permet de représenter des informations d'horodatage facilement.  La classe d' `CTimeSpan` représente le temps écoulé, telles que la différence entre deux objets d' `CTime` .  
  
> [!NOTE]
>  Les objets de CTime peuvent être utilisés pour représenter des dates entre le le 1er janvier 1970, et le 18 janvier 2038.  Les objets d'`CTime` ont une résolution de 1 secondes.  `CTime` est basé sur le type de données d' `time_t` , défini dans *la référence de la bibliothèque Runtime*.  
  
## Voir aussi  
 [Date and Time](../atl-mfc-shared/date-and-time.md)