---
title: "Définition d’une clé à chaud | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d0e801e19329b712feeeff945d382beb6025b2d2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="setting-a-hot-key"></a>Définition d'une touche d'accès rapide
Votre application peut utiliser les informations fournies par une touche d’accès rapide ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) contrôle de deux manières :  
  
-   Définir une touche d’accès rapide pour activer une fenêtre non-enfant en envoyant un [message WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) message dans la fenêtre d’être activées.  
  
-   Définissez une touche d’accès rapide spécifiques aux threads en appelant la fonction Windows [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)
