---
title: "Destruction de la boîte de dialogue | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog boxes [MFC], deleting
- destruction, dialog box
- dialog boxes [MFC], destroying
- dialog boxes [MFC], removing
- modeless dialog boxes [MFC], destroying
- MFC dialog boxes [MFC], destroying
- modal dialog boxes [MFC], destroying
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0b1b6c94c4c7efe3bc3300d6c8c5c34fbe890fb4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="destroying-the-dialog-box"></a>Destruction de la boîte de dialogue
Boîtes de dialogue modales sont normalement créés sur le frame de pile et détruits à la fin de la fonction qui les a créés. Destructeur de l’objet de la boîte de dialogue est appelé lorsque l’objet est hors de portée.  
  
 Boîtes de dialogue non modales sont généralement créés et détenus par une fenêtre d’affichage ou le frame parent : fenêtre frame principale de l’application ou une fenêtre frame de document. La valeur par défaut [OnClose](../mfc/reference/cwnd-class.md#onclose) appels du Gestionnaire de [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow), qui détruit la fenêtre de la boîte de dialogue. Si la boîte de dialogue est autonome, aucun pointeur ou autres sémantiques d’appartenance particulières, vous devez substituer [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) pour détruire l’objet de la boîte de dialogue C++. Vous devez également substituer [OnCancel](../mfc/reference/cdialog-class.md#oncancel) et appelez `DestroyWindow` à partir de qu’il contient. Si ce n’est pas le cas, le propriétaire de la boîte de dialogue doit détruire l’objet C++ lorsqu’il n’est plus nécessaire.  
  
## <a name="see-also"></a>Voir aussi  
 [Cycle de vie d’une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)

