---
title: À l’aide d’un contrôle Animation | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ecde11ddb55992032b2a8b052e2897a384293bc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="using-an-animation-control"></a>Utilisation d'un contrôle Animation
L’utilisation typique d’un contrôle animation suit le modèle suivant :  
  
-   Le contrôle est créé. Si le contrôle est spécifié dans un modèle de boîte de dialogue, la création est automatique lors de la création de la boîte de dialogue. (Vous devez disposer d’un [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) membre dans votre classe de boîte de dialogue qui correspond au contrôle de l’animation.) Vous pouvez également utiliser le [créer](../mfc/reference/canimatectrl-class.md#create) fonction membre pour créer le contrôle en tant que fenêtre enfant de n’importe quelle fenêtre.  
  
-   Charger un clip AVI dans le contrôle de l’animation en appelant le [ouvrir](../mfc/reference/canimatectrl-class.md#open) fonction membre. Si votre contrôle animation se trouve dans une boîte de dialogue, un bon emplacement pour ce faire est la classe de boîte de dialogue [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) (fonction).  
  
-   Lire l’élément en appelant le [lire](../mfc/reference/canimatectrl-class.md#play) fonction membre. Si votre contrôle animation se trouve dans une boîte de dialogue, un bon emplacement pour ce faire est la classe de boîte de dialogue **OnInitDialog** (fonction). Appel de **lire** n’est pas nécessaire si le contrôle de l’animation a la `ACS_AUTOPLAY` ensemble de style.  
  
-   Si vous souhaitez afficher des parties de l’élément ou le lire frame par frame, utilisez le `Seek` fonction membre. Pour arrêter un élément en cours de lecture, utilisez le `Stop` fonction membre.  
  
-   Si vous ne souhaitez pas détruire le contrôle immédiatement, supprimer l’élément de la mémoire en appelant le **fermer** fonction membre.  
  
-   Si le contrôle de l’animation est dans une boîte de dialogue, elle et `CAnimateCtrl` objet sera détruit automatiquement. Si pas, vous devez vous assurer que les deux le contrôle et la `CAnimateCtrl` objet sont détruits correctement. Destruction du contrôle automatiquement ferme le clip AVI.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CAnimateCtrl](../mfc/using-canimatectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

