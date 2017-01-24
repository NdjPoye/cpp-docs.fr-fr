---
title: "Traitement des messages de notification dans les contr&#244;les de calendrier mensuel | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMonthCalCtrl (classe), états du jour"
  - "CMonthCalCtrl (classe), notifications"
  - "calendrier mensuel (contrôles), messages de notification"
  - "notifications, pour CMonthCalCtrl"
  - "notifications, month calendar (contrôle)"
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Traitement des messages de notification dans les contr&#244;les de calendrier mensuel
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque les utilisateurs interagissent avec le contrôle calendrier \(month sélectionnant des dates et\/ou d'un mois différents\), le contrôle \(`CMonthCalCtrl`\) envoie des messages de notification dans la fenêtre parente, généralement une vue ou objet du dialogue.  Traitez ces messages si vous souhaitez effectuer quelque chose en réponse.  Par exemple, lorsque l'utilisateur sélectionne un nouveau mois à afficher, vous pouvez fournir un jeu de dates qui doivent être soulignées.  
  
 Utilisez la fenêtre Propriétés pour ajouter des gestionnaires de notification de la classe parente pour les messages que vous souhaitez implémenter.  
  
 La liste suivante décrit les différentes notifications envoyées par le contrôle calendrier par mois.  
  
-   **MCN\_GETDAYSTATE** demande des informations sur les jours doivent être affichées en gras.  Pour plus d'informations sur la gestion de cette notification, consultez [Définir l'état de jour d'un contrôle calendrier par mois](../mfc/setting-the-day-state-of-a-month-calendar-control.md).  
  
-   **MCN\_SELCHANGE** notifie le parent à la date ou la plage sélectionnée de la date a changé.  
  
-   **MCN\_SELECT** notifie le parent qu'une sélection explicite de dates a été effectuée.  
  
## Voir aussi  
 [Utilisation de CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)