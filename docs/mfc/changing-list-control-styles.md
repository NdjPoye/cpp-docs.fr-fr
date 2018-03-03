---
title: "Modification des Styles de contrôle de liste | Documents Microsoft"
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
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6758cce9ab42c0dea490dd8ac9803588edceac5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="changing-list-control-styles"></a>Modification des styles de contrôle de liste
Vous pouvez modifier le style d’un contrôle de liste ([CListCtrl](../mfc/reference/clistctrl-class.md)) à tout moment après l’avoir créée. En modifiant le style de fenêtre, vous modifiez le type d’affichage, que le contrôle utilise. Par exemple, pour émuler l’Explorateur, vous pouvez fournir des éléments de menu ou des boutons de barre d’outils pour basculer le contrôle entre différents affichages : mode icône, vue de liste et ainsi de suite.  
  
 Par exemple, lorsque l’utilisateur sélectionne l’élément de menu, vous pouvez effectuer un appel à [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) pour extraire le style actuel du contrôle, puis appelez [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) pour réinitialiser le style. Pour plus d’informations, consultez [à l’aide des contrôles List View](http://msdn.microsoft.com/library/windows/desktop/bb774736) dans le Kit de développement logiciel Windows.  
  
 Les styles disponibles sont répertoriés dans [créer](../mfc/reference/clistctrl-class.md#create). Les styles `LVS_ICON`, `LVS_SMALLICON`, `LVS_LIST`, et `LVS_REPORT` désignent les affichages de contrôle de liste de quatre.  
  
## <a name="extended-styles"></a>Styles étendus  
 Outre les styles standards pour un contrôle de liste, il existe un autre jeu de styles étendus. Ces styles, décrits dans [Styles étendus de la vue liste](http://msdn.microsoft.com/library/windows/desktop/bb774732) dans le Kit de développement, fournissent des fonctionnalités utiles qui personnalisent le comportement de votre contrôle de liste. Pour implémenter le comportement d’un style spécifique (par exemple, la sélection), effectuez un appel à [CListCtrl::SetExtendedStyle](../mfc/reference/clistctrl-class.md#setextendedstyle), en passant le style voulu. L’exemple suivant illustre l’appel de fonction :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]  
  
> [!NOTE]
>  Pour que la sélection fonctionner, vous devez également avoir **activé LVS_EX_ONECLICKACTIVATE** ou **LVS_EX_TWOCLICKACTIVATE** sous tension.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

