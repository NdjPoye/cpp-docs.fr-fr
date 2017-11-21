---
title: "Ajout d’éléments au contrôle Header | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 792c956d73808ef50308f8e14066f74021cc84b8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="adding-items-to-the-header-control"></a>Ajout d'éléments au contrôle Header
Après avoir créé votre contrôle header ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) dans sa fenêtre parente, ajoutez autant « éléments d’en-tête » dont vous avez besoin : généralement un par colonne.  
  
### <a name="to-add-a-header-item"></a>Pour ajouter un élément d’en-tête  
  
1.  Préparer un [structure HD_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) structure.  
  
2.  Appelez [CHeaderCtrl::InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem), en passant la structure.  
  
3.  Répétez les étapes 1 et 2 pour les éléments supplémentaires.  
  
 Pour plus d’informations, consultez [Ajout d’un élément à un contrôle Header](http://msdn.microsoft.com/library/windows/desktop/bb775238) dans le Kit de développement logiciel Windows.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

