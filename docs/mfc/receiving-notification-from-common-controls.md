---
title: "Réception des notifications de contrôles communs | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ON_NOTIFY
- WM_NOTIFY
dev_langs:
- C++
helpviewer_keywords:
- OnNotify method [MFC]
- common controls [MFC], notifications
- ON_NOTIFY macro [MFC]
- controls [MFC], notifications
- receiving notifications from common controls
- notifications [MFC], common controls
- Windows common controls [MFC], notifications
- WM_NOTIFY message
ms.assetid: 50194592-d60d-44d0-8ab3-338a2a2c63e7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 58131874ed039378a312acaaa238388f335f8e71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="receiving-notification-from-common-controls"></a>Réception des notifications de contrôles communs
Contrôles communs sont des fenêtres enfants qui envoient des messages de notification à la fenêtre parente lorsque des événements, tels que les entrées de l’utilisateur, se produisent dans le contrôle.  
  
 L’application s’appuie sur ces messages de notification pour déterminer quelle action l’utilisateur souhaite effectuer. Contrôles communs plus envoient des messages de notification en tant que **WM_NOTIFY** messages. Contrôles Windows envoient la plupart des messages de notification en tant que **WM_COMMAND** messages. [CWnd::OnNotify](../mfc/reference/cwnd-class.md#onnotify) est le gestionnaire pour le **WM_NOTIFY** message. Comme avec `CWnd::OnCommand`, l’implémentation de `OnNotify` distribue le message de notification à `OnCmdMsg` pour une gestion dans les tables des messages. L’entrée de table des messages pour la gestion des notifications est `ON_NOTIFY`. Pour plus d’informations, consultez [Technical Note 61 : Messages ON_NOTIFY et WM_NOTIFY](../mfc/tn061-on-notify-and-wm-notify-messages.md).  
  
 Ou bien, une classe dérivée peut gérer ses propres messages de notification à l’aide de « réflexion de message ». Pour plus d’informations, consultez [Technical Note 62 : Message Reflection for Windows Controls](../mfc/tn062-message-reflection-for-windows-controls.md).  
  
## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>La récupération de la Position du curseur dans un Message de Notification  
 Parfois, il est utile déterminer la position actuelle du curseur lorsque certains messages de notification sont reçus par un contrôle commun. Par exemple, il serait utile de déterminer l’emplacement du curseur lorsqu’un contrôle commun reçoit un **NM_RCLICK** message de notification.  
  
 Il existe un moyen simple pour y parvenir en appelant `CWnd::GetCurrentMessage`. Toutefois, cette méthode extrait uniquement la position du curseur au moment où que le message a été envoyé. Étant donné que le curseur a peut-être été déplacé, car le message a été envoyé, vous devez appeler **CWnd::GetCursorPos** pour obtenir la position actuelle du curseur.  
  
> [!NOTE]
>  `CWnd::GetCurrentMessage`doit uniquement être appelée dans un gestionnaire de messages.  
  
 Ajoutez le code suivant au corps du Gestionnaire de messages de notification (dans cet exemple, **NM_RCLICK**) :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]  
  
 À ce stade, l’emplacement du curseur de la souris est stocké dans le `cursorPos` objet.  
  
## <a name="see-also"></a>Voir aussi  
 [Création et utilisation de contrôles](../mfc/making-and-using-controls.md)   
 [Contrôles](../mfc/controls-mfc.md)

