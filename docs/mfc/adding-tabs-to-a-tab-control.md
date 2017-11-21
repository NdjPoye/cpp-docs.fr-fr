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
ms.openlocfilehash: 72201c20c2cc57705a96cdee2ec41dd3d63caac6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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

