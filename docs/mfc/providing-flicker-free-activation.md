---
title: "En fournissant l’Activation sans scintillement | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f98cc77ecc11f2b3ea07352e48c1e6a096125300
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="providing-flicker-free-activation"></a>Mise à disposition de l'activation sans scintillement
Si votre contrôle se dessine lui-même de façon identique dans les états inactifs et actifs (et n’utilise pas l’activation sans fenêtre), vous pouvez éliminer les opérations de dessin et le scintillement accompagne normalement se produire lors d’une transition entre inactifs États et actif. Pour cela, incluez le **noFlickerActivate** indicateur dans le jeu d’indicateurs retourné par [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Exemple :  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]  
  
 Le code permettant d’inclure cet indicateur est automatiquement généré si vous sélectionnez le **activation sans scintillement** option sur le [paramètres de contrôle](../mfc/reference/control-settings-mfc-activex-control-wizard.md) page lors de la création de votre contrôle avec l’Assistant contrôle ActiveX MFC.  
  
 Si vous utilisez l’activation sans fenêtre, cette optimisation n’a aucun effet.  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôles ActiveX MFC : optimisation](../mfc/mfc-activex-controls-optimization.md)

