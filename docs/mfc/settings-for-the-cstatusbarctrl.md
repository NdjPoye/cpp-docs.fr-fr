---
title: "Paramètres de l’objet CStatusBarCtrl | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- status bar controls [MFC], settings
- CStatusBarCtrl class [MFC], settings
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 814c12b13333d589cb568c5c637f0fa34956847e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="settings-for-the-cstatusbarctrl"></a>Paramètres de l'objet CStatusBarCtrl
La position par défaut d’un [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) fenêtre d’état est au bas de la fenêtre parente, mais vous pouvez spécifier le `CCS_TOP` style pour qu’elle s’affiche en haut de la zone cliente de la fenêtre parente.  
  
 Vous pouvez spécifier le **SBARS_SIZEGRIP** style à inclure une poignée de dimensionnement à l’extrémité droite de la `CStatusBarCtrl` fenêtre d’état. Une poignée de dimensionnement est similaire à une bordure de redimensionnement ; Il s’agit d’une zone rectangulaire que l’utilisateur peut cliquer et faites glisser pour redimensionner la fenêtre parente.  
  
> [!NOTE]
>  Si vous combinez le `CCS_TOP` et **SBARS_SIZEGRIP** styles, la poignée de dimensionnement résultant ne fonctionne pas même si le système dessine dans la fenêtre d’état.  
  
 La procédure de fenêtre pour la fenêtre d’état définit automatiquement la taille initiale et la position de la fenêtre de contrôle. La largeur est identique à celle de la zone cliente de la fenêtre parente. La hauteur est basée sur les caractéristiques de la police actuellement sélectionnée dans le contexte de périphérique de la fenêtre d’état et de la largeur des bordures de la fenêtre.  
  
 La procédure de fenêtre ajuste automatiquement la taille de la fenêtre d’état chaque fois qu’il reçoit un `WM_SIZE` message. En règle générale, lorsque la taille de la fenêtre parente change, le parent envoie un `WM_SIZE` message dans la fenêtre d’état.  
  
 Vous pouvez définir la hauteur minimale de la zone de dessin d’une fenêtre d’état en appelant [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight), en spécifiant la hauteur minimale en pixels. La zone de dessin n’inclut pas les bordures de la fenêtre.  
  
 Récupération de la largeur des bordures d’une fenêtre d’état en appelant [GetBorders](../mfc/reference/cstatusbarctrl-class.md#getborders). Cette fonction membre inclut le pointeur vers un tableau de trois éléments qui reçoit la largeur de la bordure horizontale, la bordure verticale et la bordure entre les rectangles.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

