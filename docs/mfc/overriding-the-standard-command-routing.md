---
title: Substitution du routage des commandes Standard | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7168236ea315d42961f984a3c4f94845cd8398df
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="overriding-the-standard-command-routing"></a>Substitution du routage des commandes standard
Dans de rares cas où vous devez implémenter une variation de la gamme de framework standard, vous pouvez la remplacer. Il est possible de modifier le routage dans une ou plusieurs classes en remplaçant `OnCmdMsg` dans ces classes. Pour ce faire :  
  
-   Dans la classe qui interrompt la commande à passer à un objet par défaut.  
  
-   Dans le nouvel objet par défaut ou dans les cibles de la commande qu’il peut à son tour transmettre les commandes.  
  
 Si vous insérez un nouvel objet dans le routage, sa classe doit être une classe cible de la commande. Dans les versions de substitution de `OnCmdMsg`, veillez à appeler la version que vous remplacez. Consultez le [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg) fonction membre de classe `CCmdTarget` dans les *référence MFC* et les versions de classes telles que `CView` et **CDocument** dans le code source fourni pour obtenir des exemples.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode d’appel d’un gestionnaire par le Framework](../mfc/how-the-framework-calls-a-handler.md)

