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
ms.openlocfilehash: bf874dc0d5b2ec8d814bd59a0cfd7fedab3370c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="run-member-function"></a>Exécuter une fonction membre
Une application framework passe la majorité de son temps dans le [exécuter](../mfc/reference/cwinapp-class.md#run) fonction membre de classe [CWinApp](../mfc/reference/cwinapp-class.md). Après l’initialisation, `WinMain` appelle **exécuter** pour traiter la boucle de messages.  
  
 **Exécutez** parcourt une boucle de message, la vérification de la file d’attente de message pour les messages disponibles. Si un message est disponible, **exécuter** distribue pour l’action. Si aucun message n’est disponible, ce qui est souvent le cas, **exécuter** appelle `OnIdle` d’effectuer tout traitement de temps d’inactivité que vous ou le framework peut-être nécessiter terminé. S’il y a aucun message et aucun traitement inactif, l’application attend jusqu'à ce que quelque chose se produit. Lorsque l’application se termine, **exécuter** appelle `ExitInstance`. La figure dans [fonction membre OnIdle](../mfc/onidle-member-function.md) montre la séquence d’actions dans la boucle de messages.  
  
 La distribution des messages dépend du type de message. Pour plus d’informations, consultez [Messages et commandes de l’infrastructure](../mfc/messages-and-commands-in-the-framework.md).  
  
## <a name="see-also"></a>Voir aussi  
 [CWinApp : classe d’application](../mfc/cwinapp-the-application-class.md)
