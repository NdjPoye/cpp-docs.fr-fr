---
title: "Notifications envoyées par les contrôles d’Animation | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9f26078ce389de09b38d0e69f8e90e2096bc3efd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="notifications-sent-by-animation-controls"></a>Notifications envoyées par les contrôles d'animation
Un contrôle animation ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) envoie les deux types de messages de notification. Les notifications sont envoyées sous la forme de [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) messages.  
  
 Le [message ACN_START](http://msdn.microsoft.com/library/windows/desktop/bb761891) message est envoyé lorsque le contrôle animation a commencé la lecture d’un élément. Le [message ACN_STOP](http://msdn.microsoft.com/library/windows/desktop/bb761893) message est envoyé lorsque le contrôle animation a fini ou arrêté la lecture d’un élément.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CAnimateCtrl](../mfc/using-canimatectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

