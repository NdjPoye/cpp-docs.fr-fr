---
title: Gestionnaires de messages | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- message handlers [MFC]
- command handling [MFC], message handlers
- handlers [MFC]
- message handling [MFC], message handler functions
- handlers [MFC], command
- handlers [MFC], message
ms.assetid: 51bc4e76-dbe3-4cc2-b026-3199d56b2fa9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d1b906a49d7da7ed8505252a1759d7ea00fcda1f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="message-handlers"></a>Gestionnaires de messages
Dans les MFC, dédiée *gestionnaire* fonction traite chaque message séparément. Les fonctions de gestionnaire de messages sont des fonctions de membre d’une classe. Cette documentation utilise les termes du contrat *fonction membre de gestionnaire de messages*, *fonction gestionnaire de messages*, *le Gestionnaire de messages*, et *gestionnaire*indifféremment. Certains types de gestionnaires de messages sont également appelés « gestionnaires de commandes ».  
  
 L’écriture de gestionnaires de messages représente une grande partie de votre travail de l’écriture d’une application framework. Cette série d’articles explique comment fonctionne le mécanisme de traitement des messages.  
  
 Ce que fait le gestionnaire pour un message qu’il ne fait tout ce que vous souhaitez faire en réponse à ce message. Vous pouvez créer des gestionnaires à l’aide de la fenêtre Propriétés de la classe et puis entrez le code du gestionnaire à l’aide de l’éditeur de code source.  
  
 Vous pouvez utiliser toutes les fonctionnalités de Microsoft Visual C++ et MFC pour écrire des gestionnaires. Pour obtenir la liste de toutes les classes, consultez [vue d’ensemble de la bibliothèque de classes](../mfc/class-library-overview.md) dans les *référence MFC*.  
  
## <a name="see-also"></a>Voir aussi  
 [Messages et commandes dans le Framework](../mfc/messages-and-commands-in-the-framework.md)

