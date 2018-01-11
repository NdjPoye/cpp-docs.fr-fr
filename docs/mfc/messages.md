---
title: Messages | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d03eed129fd5a2a7c73f7c7948cb766813f63c34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="messages"></a>Messages
La boucle de messages dans la **exécuter** fonction membre de classe `CWinApp` récupère les messages générés par divers événements en file d’attente. Par exemple, lorsque l’utilisateur clique sur la souris, Windows envoie plusieurs messages liés à la souris, tels que `WM_LBUTTONDOWN` lorsque le bouton gauche de la souris est enfoncé et `WM_LBUTTONUP` lorsque le bouton gauche de la souris est relâché. Implémentation de l’infrastructure de la boucle de messages d’application distribue le message à la fenêtre appropriée.  
  
 Les principales catégories de messages sont décrits dans [catégories de messages](../mfc/message-categories.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Messages et commandes dans le Framework](../mfc/messages-and-commands-in-the-framework.md)

