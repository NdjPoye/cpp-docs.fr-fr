---
title: "Utilisation de contrôles Slider | Documents Microsoft"
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
- CSliderCtrl class [MFC], using
- slider controls
- slider controls [MFC], using
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4fdab6a7fae25845da81ee7263e045e50951f557
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-slider-controls"></a>Utilisation de contrôles Slider
L’utilisation typique d’un contrôle slider suit le modèle suivant :  
  
-   Le contrôle est créé. Si le contrôle est spécifié dans un modèle de boîte de dialogue, la création est automatique lors de la création de la boîte de dialogue. (Vous devez disposer d’un [CSliderCtrl](../mfc/reference/csliderctrl-class.md) membre dans votre classe de boîte de dialogue qui correspond au contrôle de curseur.) Vous pouvez également utiliser le [créer](../mfc/reference/csliderctrl-class.md#create) fonction membre pour créer le contrôle en tant que fenêtre enfant de n’importe quelle fenêtre.  
  
-   Appelez les diverses fonctions de jeu de membres pour définir des valeurs pour le contrôle. Les modifications que vous pouvez apporter incluent définissant les positions minimales et maximales pour le curseur, dessin des graduations, définir une plage de sélection et le repositionnement du curseur. Pour les contrôles dans une boîte de dialogue, judicieux de procéder est dans la boîte de dialogue [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) (fonction).  
  
-   Lorsque l’utilisateur interagit avec le contrôle, il envoie différents messages de notification. Vous pouvez extraire la valeur du curseur à partir du contrôle en appelant le [GetPos](../mfc/reference/csliderctrl-class.md#getpos) fonction membre.  
  
-   Lorsque vous avez terminé avec le contrôle, vous devez vous assurer qu’il est correctement détruit. Si le contrôle de curseur se trouve dans une boîte de dialogue, elle et `CSliderCtrl` objet sera détruit automatiquement. Si pas, vous devez vous assurer que les deux le contrôle et la `CSliderCtrl` objet sont détruits correctement.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

