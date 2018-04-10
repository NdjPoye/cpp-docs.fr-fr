---
title: Quand initialiser les objets CWnd | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- window objects [MFC], when to initialize CWnd
- initializing CWnd objects [MFC]
- initializing objects [MFC], CWnd
- CWnd objects [MFC], when HWND is attached
- HWND, when attached to CWnd object
- CWnd objects [MFC], when to initialize
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d1efceb4fa826d5cd2bf8dc900180eb36cea4de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="when-to-initialize-cwnd-objects"></a>Quand initialiser les objets CWnd
Vous ne peut pas créer votre propre enfant windows ou appeler des fonctions API Windows dans le constructeur d’un `CWnd`-objet dérivé. C’est parce que le `HWND` pour la `CWnd` objet n’a pas encore été créé. L’initialisation de Windows plus spécifiques, telles que l’ajout de fenêtres enfants, doit être effectuée dans un [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Gestionnaire de messages.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Que voulez-vous en savoir plus  
  
-   [Création de fenêtres frame de document](../mfc/creating-document-frame-windows.md)  
  
-   [La création de document/vue](../mfc/document-view-creation.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de fenêtres frame](../mfc/using-frame-windows.md)

