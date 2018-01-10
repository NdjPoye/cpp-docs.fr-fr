---
title: "Exécuter une fonction membre | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 90436e3b775cd547a67be49c120d1fb94b32a5dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="run-member-function"></a>Exécuter une fonction membre
Une application framework passe la majorité de son temps dans le [exécuter](../mfc/reference/cwinapp-class.md#run) fonction membre de classe [CWinApp](../mfc/reference/cwinapp-class.md). Après l’initialisation, `WinMain` appelle **exécuter** pour traiter la boucle de messages.  
  
 **Exécutez** parcourt une boucle de message, la vérification de la file d’attente de message pour les messages disponibles. Si un message est disponible, **exécuter** distribue pour l’action. Si aucun message n’est disponible, ce qui est souvent le cas, **exécuter** appelle `OnIdle` d’effectuer tout traitement de temps d’inactivité que vous ou le framework peut-être nécessiter terminé. S’il y a aucun message et aucun traitement inactif, l’application attend jusqu'à ce que quelque chose se produit. Lorsque l’application se termine, **exécuter** appelle `ExitInstance`. La figure dans [fonction membre OnIdle](../mfc/onidle-member-function.md) montre la séquence d’actions dans la boucle de messages.  
  
 La distribution des messages dépend du type de message. Pour plus d’informations, consultez [Messages et commandes de l’infrastructure](../mfc/messages-and-commands-in-the-framework.md).  
  
## <a name="see-also"></a>Voir aussi  
 [CWinApp : classe d’application](../mfc/cwinapp-the-application-class.md)
