---
title: "À l’aide des boutons de liste déroulante dans un contrôle de barre d’outils | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TBN_DROPDOWN
- TBSTYLE_EX_DRAWDDARROWS
dev_langs:
- C++
helpviewer_keywords:
- CToolBarCtrl class [MFC], drop-down buttons
- toolbars [MFC], drop-down buttons
- drop-down buttons in toolbars
- TBSTYLE_EX_DRAWDDARROWS
- TBN_DROPDOWN notification [MFC]
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 01c09cb2bec4b466928557434767ce49948f46ae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>Utilisation de boutons de liste déroulante dans un contrôle ToolBar
En plus des boutons de commande standards, une barre d’outils peut également comporter des boutons de liste déroulante. Un bouton de liste déroulante est généralement indiqué par la présence d’une flèche bas attachée.  
  
> [!NOTE]
>  La flèche bas attachée s’affiche uniquement si le `TBSTYLE_EX_DRAWDDARROWS` style étendu a été définie.  
  
 Lorsque l’utilisateur clique sur cette flèche (ou le bouton si aucune flèche n’est présente), un `TBN_DROPDOWN` message de notification est envoyé au parent du contrôle de barre d’outils. Vous pouvez ensuite gérer cette notification et afficher un menu contextuel. semblable au comportement d’Internet Explorer.  
  
 La procédure suivante illustre comment implémenter un bouton de barre d’outils de la liste déroulante avec un menu contextuel :  
  
### <a name="to-implement-a-drop-down-button"></a>Pour implémenter un bouton de liste déroulante  
  
1.  Une fois votre `CToolBarCtrl` objet a été créé, définissez le `TBSTYLE_EX_DRAWDDARROWS` style, en utilisant le code suivant :  
  
     [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]  
  
2.  Définir le `TBSTYLE_DROPDOWN` style pour tout nouveau ([InsertButton](../mfc/reference/ctoolbarctrl-class.md#insertbutton) ou [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)) ou existante ([SetButtonInfo](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)) boutons qui seront les boutons de liste déroulante. L’exemple suivant illustre la modification d’un bouton existant dans un `CToolBarCtrl` objet :  
  
     [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]  
  
3.  Ajouter un `TBN_DROPDOWN` gestionnaire à la classe parente de l’objet de barre d’outils.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]  
  
4.  Dans le nouveau gestionnaire, afficher le menu contextuel approprié. Le code suivant illustre une méthode :  
  
     [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

