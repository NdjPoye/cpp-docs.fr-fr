---
title: OnCmdMsg (gestionnaire) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OnCmdMsg
dev_langs: C++
helpviewer_keywords:
- messages, routing
- handlers [MFC]
- command routing [MFC], OnCmdMsg handler
- handlers, OnCmdMessage [MFC]
- OnCmdMessage method [MFC]
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 173741ef73cd4bf6426787ef56e8334f504d7c0e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="oncmdmsg-handler"></a>OnCmdMsg, gestionnaire
Pour effectuer le routage des commandes, chaque cible de la commande appelle la `OnCmdMsg` fonction membre de la cible de la commande suivante dans la séquence. Utilisation de cibles de commandes `OnCmdMsg` pour déterminer si elles peuvent gérer une commande et pour le router vers une autre cible de commande si elles ne peuvent pas le gérer.  
  
 Chaque classe cible de commande peut remplacer le `OnCmdMsg` fonction membre. Les remplacements permettent à chaque classe router les commandes vers une cible suivante particulière. Une fenêtre frame, par exemple, route toujours les commandes à sa fenêtre enfant Active ou une vue, comme indiqué dans le tableau [routage des commandes Standard](../mfc/command-routing.md).  
  
 La valeur par défaut `CCmdTarget` implémentation de `OnCmdMsg` utilise la table des messages de la classe cible de commande pour rechercher une fonction gestionnaire pour chaque message de commande reçu, de la même façon que les messages standard sont recherchés. S’il trouve une correspondance, il appelle le gestionnaire. Recherche de la table des messages est expliquée dans [comment le Framework recherche les tables des messages](../mfc/how-the-framework-searches-message-maps.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode d’appel d’un gestionnaire par le Framework](../mfc/how-the-framework-calls-a-handler.md)

