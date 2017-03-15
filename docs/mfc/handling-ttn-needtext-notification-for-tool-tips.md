---
title: "Gestion de la notification TTN_NEEDTEXT pour les info-bulles | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TTN_NEEDTEXT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "notifications, info-bulles"
  - "info-bulles (C++), notifications"
  - "TTN_NEEDTEXT (message)"
ms.assetid: d0370a65-21ba-4676-bcc5-8cf851bbb15c
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Gestion de la notification TTN_NEEDTEXT pour les info-bulles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans le cadre de [activer les info\-bulles](../mfc/enabling-tool-tips.md), vous traitez le message de **TTN\_NEEDTEXT** lorsque vous ajoutez l'entrée suivante à la table des messages de la fenêtre propriétaire :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/CPP/handling-ttn-needtext-notification-for-tool-tips_1.cpp)]  
  
 `memberFxn`  
 La fonction membre à appeler lorsque le texte est nécessaire pour ce bouton.  
  
 Notez que l'ID d'une info\-bulle est toujours à 0.  
  
 Déclarez votre fonction gestionnaire dans la définition de classe comme suit:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#53](../mfc/codesnippet/CPP/handling-ttn-needtext-notification-for-tool-tips_2.h)]  
  
 où les paramètres en italique sont :  
  
 `id`  
 Identificateur du contrôle qui envoie la notification.  Non utilisé.  L'ID de contrôle provient de la structure de **NMHDR**.  
  
 `pNMHDR`  
 Le pointeur vers la structure [NMTTDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760258) .  Cette structure est également décrite plus loin dans [La structure de TOOLTIPTEXT](../mfc/tooltiptext-structure.md).  
  
 `pResult`  
 Un pointeur vers qui résulte le code que vous pouvez définir avant de le retourner.  Les gestionnaires de**TTN\_NEEDTEXT** peuvent ignorer le paramètre de `pResult`.  
  
 Comme exemple d'une gestion de notification en forme de visionnage :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#54](../mfc/codesnippet/CPP/handling-ttn-needtext-notification-for-tool-tips_3.cpp)]  
  
 Appelle `EnableToolTips` \(ce fragment est pris en `OnInitDialog`\) :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#55](../mfc/codesnippet/CPP/handling-ttn-needtext-notification-for-tool-tips_4.cpp)]  
  
## Voir aussi  
 [Info\-bulles dans les fenêtres non dérivées de CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)