---
title: OnIdle, fonction membre | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OnIdle
dev_langs:
- C++
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4dfbc0a1f20cb6cc01143ed6f07a63e84b53be6b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="onidle-member-function"></a>OnIdle, fonction membre
Lorsque les messages Windows sont en cours de traitement, le framework appelle la [CWinApp](../mfc/reference/cwinapp-class.md) fonction membre [OnIdle](../mfc/reference/cwinapp-class.md#onidle) (décrite dans la référence de bibliothèque MFC).  
  
 Substituer `OnIdle` pour effectuer des tâches en arrière-plan. La version par défaut met à jour l’état des objets d’interface utilisateur tels que les boutons de barre d’outils et effectue un nettoyage des objets temporaires créés par le framework au cours de ses opérations. L’exemple suivant illustre comment la boucle de messages appelle `OnIdle` lorsqu’il y a aucun message dans la file d’attente.  
  
 ![Processus en boucle de message](../mfc/media/vc387c1.gif "vc387c1")  
La boucle de messages  
  
 Pour plus d’informations sur ce que vous pouvez faire dans la boucle inactive, consultez [traitement de la boucle inactive](../mfc/idle-loop-processing.md).  
  
## <a name="see-also"></a>Voir aussi  
 [CWinApp : classe d’application](../mfc/cwinapp-the-application-class.md)
