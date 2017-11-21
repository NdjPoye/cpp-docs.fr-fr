---
title: "Comment les Messages noncommand parviennent à leurs gestionnaires | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0e6a6f30597ddb5ea68b3a5a00c35e27024fb9b0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>Comment les messages noncommand parviennent à leurs gestionnaires
Contrairement aux commandes, les messages Windows standard ne sont pas acheminés via une chaîne de cibles de commandes, mais sont généralement gérées par la fenêtre à laquelle Windows envoie le message. La fenêtre peut être une fenêtre frame principale, une fenêtre enfant MDI, un contrôle standard, une boîte de dialogue, une vue ou un autre type de fenêtre enfant.  
  
 Au moment de l’exécution, chaque fenêtre Windows est attaché à un objet fenêtre (dérivé directement ou indirectement de `CWnd`) qui a ses propres fonctions de mappage et le Gestionnaire de message associé. L’infrastructure utilise la table des messages, comme pour une commande — pour mapper les messages entrants aux gestionnaires.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode d’appel d’un gestionnaire par le Framework](../mfc/how-the-framework-calls-a-handler.md)

