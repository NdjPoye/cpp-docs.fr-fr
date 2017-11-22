---
title: "Contrôle header et contrôle List | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CListCtrl class [MFC], with CHeaderCtrl
- CListCtrl class [MFC], header controls
- CHeaderCtrl class [MFC], with CListCtrl
- controls [MFC], header
- header controls [MFC]
- header controls [MFC], list controls used with
ms.assetid: b20194b1-1a6b-4e2f-b890-1b3cca6650bc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a3491ce0b61880d3dfa1969a38fb3b351c2a8903
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="header-control-and-list-control"></a>Contrôle Header et contrôle List
Dans la plupart des cas, vous allez utiliser le contrôle header est incorporé dans un [CListCtrl](../mfc/reference/clistctrl-class.md) ou [CListView](../mfc/reference/clistview-class.md) objet. Toutefois, il existe des cas où un objet de contrôle d’en-tête distinct est souhaitable, telles que la manipulation de données, organisées en colonnes ou lignes, dans un [CView](../mfc/reference/cview-class.md)-objet dérivé. Dans ce cas, vous devez mieux contrôler l’apparence et le comportement par défaut d’un contrôle header incorporé.  
  
 Dans le cas courant que vous souhaitez un contrôle header doit présenter un standard, comportement par défaut, vous pouvez utiliser [CListCtrl](../mfc/reference/clistctrl-class.md) ou [CListView](../mfc/reference/clistview-class.md) à la place. Utilisez `CListCtrl` lorsque vous souhaitez les fonctionnalités d’un contrôle d’en-tête par défaut, incorporé dans un contrôle commun de vue de liste. Utilisez [CListView](../mfc/reference/clistview-class.md) lorsque vous souhaitez que les fonctionnalités d’un contrôle d’en-tête par défaut, incorporé dans un objet de vue.  
  
> [!NOTE]
>  Ces contrôles comprennent uniquement un contrôle header intégrée si le contrôle list view est créé à l’aide de la `LVS_REPORT` style.  
  
 Dans la plupart des cas, l’apparence du contrôle header incorporé modifiables en modifiant les styles du contrôle list view conteneur. En outre, plus d’informations sur le contrôle header peuvent être obtenues via les fonctions membres de contrôle list view parent. Toutefois, pour bénéficier d’un contrôle et l’accès, les attributs et les styles du contrôle header incorporé, il est recommandé qu’un pointeur vers l’objet de contrôle header être obtenues.  
  
 L’objet de contrôle header incorporé est accessible à partir de le **CListCtrl** ou `CListView` avec un appel à la classe respective `GetHeaderCtrl` fonction membre. Le code suivant illustre cela :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/cpp/header-control-and-list-control_1.cpp)]  
  
## <a name="what-do-you-want-to-know-more-about"></a>Que voulez-vous en savoir plus  
  
-   [À l’aide d’image répertorie avec des contrôles header](../mfc/using-image-lists-with-header-controls.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)
