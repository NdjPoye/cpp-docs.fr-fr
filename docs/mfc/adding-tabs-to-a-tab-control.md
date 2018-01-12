---
title: "Ajout d’onglets à un contrôle onglet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 46012a265c1ecefa7af63f829be22e6132e036cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-tabs-to-a-tab-control"></a>Ajout d'onglets à un contrôle Tab
Après la création du contrôle tab ([CTabCtrl](../mfc/reference/ctabctrl-class.md)), ajouter des onglets autant que nécessaire.  
  
### <a name="to-add-a-tab-item"></a>Pour ajouter un élément d’onglet  
  
1.  Préparer un [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) structure.  
  
2.  Appelez [CTabCtrl::InsertItem](../mfc/reference/ctabctrl-class.md#insertitem), en passant la structure.  
  
3.  Répétez les étapes 1 et 2 pour ajouter d’autres onglets.  
  
 Pour plus d’informations, consultez [création d’un contrôle onglet](http://msdn.microsoft.com/library/windows/desktop/bb760550) dans le Kit de développement logiciel Windows.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CTabCtrl](../mfc/using-ctabctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

