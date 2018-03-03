---
title: "Allocation et libération de mémoire (fenêtre) | Documents Microsoft"
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
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 294de3c4d4ecdfcb31f6e8c227bd8a3c6764268d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="allocating-and-deallocating-window-memory"></a>Allocation et libération de la mémoire Windows
N’utilisez pas le C++ **supprimer** opérateur pour détruire une fenêtre frame ou une vue. Au lieu de cela, appelez le `CWnd` fonction membre `DestroyWindow`. Par conséquent, les fenêtres frame, doivent être allouées sur le tas avec l’opérateur **nouveau**. Soyez prudent lors de l’allocation de fenêtres frames sur le frame de pile ou globalement. Autres fenêtres doivent être alloués sur le frame de pile chaque fois que possible.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Que voulez-vous en savoir plus  
  
-   [Création de fenêtres](../mfc/creating-windows.md)  
  
-   [Séquence de destruction de fenêtres](../mfc/window-destruction-sequence.md)  
  
-   [Détachement d’un objet CWnd de son HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Destruction d’objets fenêtres](../mfc/destroying-window-objects.md)

