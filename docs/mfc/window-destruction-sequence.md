---
title: "Séquence de Destruction de fenêtres | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- destruction, windows
- destroying windows
- sequence [MFC], window destruction
- CWnd objects [MFC], destruction sequence
- sequence [MFC]
- windows [MFC], destroying
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a2b435c76fba179f17978f7cf2b7b981903182a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="window-destruction-sequence"></a>Séquence de destruction de fenêtres
Dans l’infrastructure MFC, lorsque l’utilisateur ferme la fenêtre frame, la valeur par défaut de la fenêtre [OnClose](../mfc/reference/cwnd-class.md#onclose) appels du Gestionnaire de [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). La dernière fonction membre appelée lorsque la fenêtre Windows est détruite est [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), qui procède au nettoyage, appelle le [par défaut](../mfc/reference/cwnd-class.md#default) membre de la fonction pour effectuer un nettoyage de Windows et enfin appelle la fonction membre virtuelle [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). Le [CFrameWnd](../mfc/reference/cframewnd-class.md) implémentation de `PostNcDestroy` supprime l’objet fenêtre C++.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Que voulez-vous en savoir plus  
  
-   [Allocation et libération de mémoire (fenêtre)](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Détachement d’un objet CWnd de son HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Destruction d’objets fenêtres](../mfc/destroying-window-objects.md)

