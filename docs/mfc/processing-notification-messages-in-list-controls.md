---
title: "Le traitement des Messages de Notification dans les contrôles de liste | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2c4a900b6fe0741de852c15afca37a974fc3e989
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="processing-notification-messages-in-list-controls"></a>Traitement des messages de notification dans les contrôles de liste
Lorsque les utilisateurs sur les en-têtes de colonne, faites glisser les icônes, modifier des étiquettes et ainsi de suite, le contrôle de liste ([CListCtrl](../mfc/reference/clistctrl-class.md)) envoie des messages de notification à sa fenêtre parente. Vous devez gérer ces messages si vous voulez faire quelque chose en réponse. Par exemple, lorsque l’utilisateur clique sur un en-tête de colonne, vous pouvez souhaiter trier les éléments en fonction du contenu de cette colonne, comme dans Microsoft Outlook.  
  
 Processus **WM_NOTIFY** messages du contrôle de liste dans votre classe d’affichage ou de la boîte de dialogue. Utilisez la fenêtre Propriétés pour créer un [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) fonction de gestionnaire avec une instruction switch basée sur le message de notification est traité.  
  
 Pour obtenir la liste des notifications d’un contrôle de liste peut envoyer à sa fenêtre parente, consultez [référence de contrôle de la vue liste](http://msdn.microsoft.com/library/windows/desktop/bb774737) dans le Kit de développement logiciel Windows.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

