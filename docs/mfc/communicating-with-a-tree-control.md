---
title: "Communication avec un contrôle d’arborescence | Documents Microsoft"
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
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ef1188c9519e57c8132a2b20fc3b272d6c0ac51
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="communicating-with-a-tree-control"></a>Communication avec un contrôle d’arborescence
Vous utilisez différentes méthodes pour appeler des fonctions membres dans un [CTreeCtrl](../mfc/reference/ctreectrl-class.md) objet selon la façon dont l’objet a été créé :  
  
-   Si le contrôle d’arborescence est dans une boîte de dialogue, utilisez une variable membre de type `CTreeCtrl` que vous créez dans la classe de boîte de dialogue.  
  
-   Si le contrôle d’arborescence est une fenêtre enfant, utilisez la `CTreeCtrl` objet (ou pointeur) que vous avez utilisé pour construire l’objet.  
  
-   Si vous utilisez un `CTreeView` de l’objet, utilisez la fonction [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) pour obtenir une référence au contrôle d’arborescence. Vous pouvez initialiser une autre référence avec cette valeur ou assigner l’adresse de la référence à un `CTreeCtrl` pointeur.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

