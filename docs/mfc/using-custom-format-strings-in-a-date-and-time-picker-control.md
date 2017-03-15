---
title: "Utilisation de cha&#238;nes de format personnalis&#233;es dans un contr&#244;le de s&#233;lecteur de date et heure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDateTimeCtrl (classe), styles d'affichage"
  - "DateTimePicker (contrôle) (MFC)"
  - "DateTimePicker (contrôle) (MFC), styles d'affichage"
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Utilisation de cha&#238;nes de format personnalis&#233;es dans un contr&#244;le de s&#233;lecteur de date et heure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Par défaut, les contrôles Date et Time Picker fournissent trois types de format \(chaque format correspondant à un seul style\) pour afficher la date ou l'heure actuelles :  
  
-   **DTS\_LONGDATEFORMAT** affiche la date sous forme longue, ce qui donne la sortie comme « mercredi 3 janvier 2000 ».  
  
-   **DTS\_SHORTDATEFORMAT** affiche la date sous forme abrégée, ce qui donne la sortie comme « 3\/1\/00 ".  
  
-   **DTS\_TIMEFORMAT** affiche l'heure sous forme longue, ce qui donne la sortie comme « 5:31:42. ».  
  
 Toutefois, vous pouvez personnaliser l'apparence de la date ou l'heure à l'aide d'une chaîne de format personnalisée.  Cette chaîne personnalisée comporte des caractères de format existant, des caractères hors format, ou une combinaison des deux.  Une fois la chaîne personnalisée est établie, effectuez un appel à [CDateTimeCtrl::SetFormat](../Topic/CDateTimeCtrl::SetFormat.md) en passant la chaîne personnalisée.  Le contrôle Date Time Picker affiche la valeur actuelle en utilisant votre chaîne de format personnalisée.  
  
 Le code exemple suivant \(où `m_dtPicker` est l'objet `CDateTimeCtrl` \) montre une solution possible :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/CPP/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]  
  
 Outre les chaînes de format personnalisées, les contrôles Date Time Picker prennent également en charge les [champs de rappel](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
## Voir aussi  
 [Utilisation de CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)