---
title: "Contrôles RichEdit | Documents Microsoft"
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
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f8a92b180ed44937c29cd880dea7439e0cfe20b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="bottomless-rich-edit-controls"></a>Contrôles RichEdit sans marge inférieure
Votre application peut redimensionner un contrôle RichEdit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) en fonction des besoins afin qu’il soit toujours la même taille que son contenu. Un contrôle RichEdit prend en charge cette fonctionnalité dite de « sans fin » en envoyant à sa fenêtre parente un [EN_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787983) message de notification chaque fois que la taille de son contenu change.  
  
 Lors du traitement de la **EN_REQUESTRESIZE** message de notification, une application doit redimensionner le contrôle aux dimensions spécifié [REQRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787950) structure. Une application peut également déplacer une information à proximité du contrôle pour prendre en charge la modification du contrôle de la hauteur. Pour redimensionner le contrôle, vous pouvez utiliser la `CWnd` fonction [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos).  
  
 Vous pouvez forcer un contrôle RichEdit pour envoyer un **EN_REQUESTRESIZE** message de notification à l’aide de la [fonction membre RequestResize](../mfc/reference/cricheditctrl-class.md#requestresize) fonction membre. Ce message peut être utile dans les [OnSize](../mfc/reference/cwnd-class.md#onsize) gestionnaire.  
  
 Pour recevoir des **EN_REQUESTRESIZE** messages de notification, vous devez activer la notification à l’aide de la `SetEventMask` fonction membre.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

