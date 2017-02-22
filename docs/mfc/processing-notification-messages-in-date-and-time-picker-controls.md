---
title: "Traitement des messages de notification dans les contr&#244;les de s&#233;lecteur de date et heure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DTN_CLOSEUP"
  - "DTN_DATETIMECHANGE"
  - "DTN_DROPDOWN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDateTimeCtrl (classe), gérer les notifications"
  - "DateTimePicker (contrôle) (MFC)"
  - "DateTimePicker (contrôle) (MFC), gérer les notifications"
  - "DTN_CLOSEUP (notification)"
  - "DTN_DATETIMECHANGE (notification)"
  - "DTN_DROPDOWN (notification)"
  - "DTN_FORMAT (notification)"
ms.assetid: ffbe29ab-ff80-4609-89f7-260b404439c4
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Traitement des messages de notification dans les contr&#244;les de s&#233;lecteur de date et heure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque les utilisateurs interagissent avec contrôle Date Time Picker, le contrôle \(`CDateTimeCtrl`\) envoie des messages de notification dans la fenêtre parente, généralement un objet vue ou boîte de dialogue.  Traitez ces messages si vous souhaitez effectuer quelque chose en réponse.  Par exemple, lorsque l'utilisateur ouvre le sélecteur de date et d'heure pour afficher le contrôle calendrier month incorporé, la notification de **DTN\_DROPDOWN** est envoyée.  
  
 Utilisez la fenêtre Propriétés pour ajouter des gestionnaires de notification de la classe parente pour les messages que vous souhaitez implémenter.  
  
 La liste suivante décrit les différentes notifications envoyées par le contrôle Date Time Picker.  
  
-   **DTN\_DROPDOWN** notifie le parent que le contrôle calendrier month incorporé est sur le point d'être affiché.  Cette notification est envoyée uniquement lorsque le style de **DTS\_UPDOWN** n'a pas été défini.  Pour plus d'informations sur cette notification, consultez [Accès au contrôle calendrier incorporé month](../mfc/accessing-the-embedded-month-calendar-control.md).  
  
-   **DTN\_CLOSEUP** notifie le parent que le contrôle calendrier month incorporé va être fermé.  Cette notification est envoyée uniquement lorsque le style **DTS\_UPDOWN** n'a pas été défini.  
  
-   **DTN\_DATETIMECHANGE** notifie le parent qu'une modification a été apportée dans le contrôle.  
  
-   **DTN\_FORMAT** notifie le parent que le texte est nécessaire pour être affiché dans un domaine de rappel.  Pour plus d'informations sur les champs de notification et de rappel, consultez [Utilisation des champs de rappel dans un contrôle Date Time Picker](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   **DTN\_FORMATQUERY** invite le parent à assurer la taille maximale autorisée de la chaîne qui sera affichée dans un domaine de rappel.  Gérer cette notification autorise le contrôle à afficher correctement l'affichage de sortie à tout moment, ce qui réduit le scintillement dans l'affichage du contrôle.  Pour plus d'informations sur cette notification, consultez [Utilisation des champs de rappel dans un contrôle Date Time Picker](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   **DTN\_USERSTRING** notifie le parent que l'utilisateur a fini de modifier le contenu du contrôle Date Time Picker.  Cette notification est envoyée uniquement lorsque le style **DTS\_APPCANPARSE** n'a pas été défini.  
  
-   **DTN\_WMKEYDOWN** notifie le parent lorsque l'utilisateur tape du texte dans un champ de rappel.  Traitez cette notification pour émuler le même résultat de réponse clavier pour les champs sans rappel dans un contrôle Date Time Picker.  Pour plus d'informations sur cette notification, consultez [Champs de rappel de prise en charge dans un contrôle de DTP](http://msdn.microsoft.com/library/windows/desktop/bb761726) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Voir aussi  
 [Utilisation de CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)