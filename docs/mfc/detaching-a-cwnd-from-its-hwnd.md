---
title: "Détachement d’un objet CWnd de son HWND | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CWnd
dev_langs: C++
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6aa24e0e9a0d9ee50a0c5c69e280ea7a727ca38b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Détachement d'un objet CWnd de son HWND
Si vous avez besoin de contourner l’objet -`HWND` relation, MFC fournit un autre `CWnd` fonction membre, [détachement](../mfc/reference/cwnd-class.md#detach), qui déconnecte l’objet fenêtre C++ à partir de la fenêtre Windows. Cela empêche le destructeur de détruire la fenêtre Windows quand l’objet est détruit.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Que voulez-vous en savoir plus  
  
-   [Création de fenêtres](../mfc/creating-windows.md)  
  
-   [Séquence de destruction de fenêtres](../mfc/window-destruction-sequence.md)  
  
-   [Allocation et libération de mémoire (fenêtre)](../mfc/allocating-and-deallocating-window-memory.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Objets fenêtre](../mfc/window-objects.md)

