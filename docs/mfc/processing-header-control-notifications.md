---
title: "Traitement des Notifications de contrôle Header | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a356b665800b8930c42b6ba58036e73f1142b011
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="processing-header-control-notifications"></a>Traitement des notifications de contrôle Header
Dans votre classe d’affichage ou de la boîte de dialogue, utilisez la fenêtre Propriétés pour créer un [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) fonction de gestionnaire avec une instruction switch pour n’importe quel contrôle header ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) vous souhaitez des messages de notification gérer (consultez [mappage de Messages à des fonctions](../mfc/reference/mapping-messages-to-functions.md)). Les notifications sont envoyées à la fenêtre parente lorsque l’utilisateur clique ou double-clique sur un élément d’en-tête, fait glisser un séparateur entre les éléments et ainsi de suite.  
  
 Les messages de notification associés à un contrôle header sont répertoriés dans [référence de contrôle d’en-tête](http://msdn.microsoft.com/library/windows/desktop/bb775239) dans le Kit de développement logiciel Windows.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

