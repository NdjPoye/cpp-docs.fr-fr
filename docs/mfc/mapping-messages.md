---
title: Mappage des Messages | Documents Microsoft
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
- message maps [MFC], about message maps
- mappings [MFC], commands
- commands [MFC], mapping
- command mapping [MFC]
- message handling [MFC], connecting to handler functions
- commands [MFC], connecting to handler functions
- mappings [MFC], messages
- messages [MFC], mapping
ms.assetid: 996f0652-0698-4b8c-b893-cdaa836d9d0f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c415b12b22c19a5e1f2d19fd9c808a98485eb7ae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="mapping-messages"></a>Mappage des messages
Chaque classe de framework qui peut recevoir des messages ou des commandes possède sa propre « table des messages ». L’infrastructure utilise les tables des messages pour connecter des messages et commandes aux fonctions gestionnaires. Toute classe dérivée de la classe `CCmdTarget` peut avoir une table des messages. Autres articles expliquent les tables des messages en détail et décrivent comment les utiliser.  
  
 En dépit du nom « table des messages, » message maps gèrent deux messages et les commandes, les trois catégories de messages répertoriées dans [catégories de messages](../mfc/message-categories.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Messages et commandes dans le Framework](../mfc/messages-and-commands-in-the-framework.md)

