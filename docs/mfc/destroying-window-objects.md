---
title: "Destruction d’objets fenêtres | Documents Microsoft"
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
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8e7b8b2cf605e0f53418755b65151fd9eb2cff5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="destroying-window-objects"></a>Destruction d’objets fenêtres
Être vigilant avec vos propres fenêtres enfants pour détruire l’objet fenêtre C++ quand l’utilisateur a terminé avec la fenêtre. Si ces objets ne sont pas détruits, votre application ne récupère pas leur mémoire. Heureusement, le framework gère la destruction des fenêtres, ainsi que la création de boîtes de dialogue, des vues et fenêtres frame. Si vous créez des fenêtres supplémentaires, vous êtes responsable de leur destruction.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Que voulez-vous en savoir plus  
  
-   [Séquence de destruction de fenêtres](../mfc/window-destruction-sequence.md)  
  
-   [Allocation et libération de mémoire (fenêtre)](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Détachement d’un objet CWnd de son HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [Séquence de création d’une fenêtre générale](../mfc/general-window-creation-sequence.md)  
  
-   [Détruire des fenêtres frame](../mfc/destroying-frame-windows.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Objets fenêtre](../mfc/window-objects.md)

