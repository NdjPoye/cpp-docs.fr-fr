---
title: "Gestion de l’affichage actuel | Documents Microsoft"
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
- views [MFC], and OnActivateView method [MFC]
- views [MFC], deactivating
- views [MFC], activating
- frame windows [MFC], current view
- OnActivateView method [MFC]
- views [MFC], current
- deactivating views [MFC]
- current view in frame window [MFC]
ms.assetid: 0a1cc22d-d646-4536-9ad2-3cb6d7092e4a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e1510b005f452174acfe8ad65ae3f66cf8aafaa2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="managing-the-current-view"></a>Gestion de l'affichage actuel
Dans le cadre de l’implémentation par défaut des fenêtres frame, une fenêtre frame effectue le suivi d’une vue actuellement active. Si la fenêtre frame contient plusieurs vues, comme par exemple dans une fenêtre fractionnée, la vue actuelle est la vue la plus récente en cours d’utilisation. La vue active est indépendante de la fenêtre active de Windows ou le focus d’entrée actuel.  
  
 Lorsque la vue active change, le framework informe l’affichage actuel en appelant son [OnActivateView](../mfc/reference/cview-class.md#onactivateview) fonction membre. Vous pouvez indiquer si la vue est activée ou désactivée en examinant `OnActivateView`de `bActivate` paramètre. Par défaut, `OnActivateView` définit le focus sur l’affichage actuel sur l’activation. Vous pouvez substituer `OnActivateView` pour effectuer un traitement spécial lors de la vue est activée ou désactivée. Par exemple, vous souhaiterez fournissent des signaux visuels spéciaux pour distinguer la vue active à partir d’autres vues.  
  
 Une fenêtre frame transfère des commandes pour son affichage actuel (actif), comme décrit dans [routage des commandes](../mfc/command-routing.md), en tant que partie du routage des commandes standard.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de fenêtres frame](../mfc/using-frame-windows.md)

