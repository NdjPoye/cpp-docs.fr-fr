---
title: "Current Time: General Purpose Classes | Microsoft Docs"
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
  - "heure actuelle, CTime object"
  - "initialiser des objets, with the current time"
  - "procédures, getting current time"
  - "heure, getting current"
  - "heure, setting current"
ms.assetid: c39e6775-6a92-4b27-95a7-5c86ed371d8a
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Current Time: General Purpose Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La procédure suivante montre comment créer un objet d' `CTime` et l'initialiser avec l'heure actuelle.  
  
#### Pour obtenir l'heure actuelle  
  
1.  Allouez un objet d' `CTime` , comme suit :  
  
     [!code-cpp[NVC_ATLMFC_Utilities#171](../atl-mfc-shared/codesnippet/CPP/current-time-general-purpose-classes_1.cpp)]  
  
    > [!NOTE]
    >  Les objets non initialisés d' `CTime` ne sont pas initialisés à une heure valide.  
  
2.  Appelez la fonction d' `CTime::GetCurrentTime` pour obtenir l'heure actuelle du système d'exploitation.  Cette fonction retourne un objet d' `CTime` qui peut être utilisé pour définir la valeur d' `CTime`, comme suit :  
  
     [!code-cpp[NVC_ATLMFC_Utilities#172](../atl-mfc-shared/codesnippet/CPP/current-time-general-purpose-classes_2.cpp)]  
  
     Étant donné qu' `GetCurrentTime` est une fonction membre statique de la classe d' `CTime` , vous devez qualifier son nom avec le nom de la classe et de l'opérateur de résolution de portée \(`::`\), `CTime::GetCurrentTime()`.  
  
 Naturellement, les deux étapes décrites les plan précédemment peuvent être combinées dans une instruction de programmation unique comme suit :  
  
 [!code-cpp[NVC_ATLMFC_Utilities#173](../atl-mfc-shared/codesnippet/CPP/current-time-general-purpose-classes_3.cpp)]  
  
## Voir aussi  
 [Date and Time: General\-Purpose Classes](../atl-mfc-shared/date-and-time-general-purpose-classes.md)