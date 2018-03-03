---
title: "Paramètres du contrôle Progress | Documents Microsoft"
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
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1ad62f3a60c8fe4fcd7efdde7f69f5c5e9450d14
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="settings-for-the-progress-control"></a>Paramètres du contrôle Progress
Les paramètres de base du contrôle progress ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)) sont la plage et la position actuelle. La plage représente l’ensemble de la durée de l’opération. La position actuelle représente l’avancement de votre application vers la réalisation de l’opération. Toute modification de la plage ou la position provoque le contrôle de progression à redessiner.  
  
 Par défaut, la plage est définie à 0 - 100 et la position initiale est définie sur 0. Pour récupérer les paramètres actuels de la plage pour le contrôle de progression, utilisez la [GetRange](../mfc/reference/cprogressctrl-class.md#getrange) fonction membre. Pour modifier la plage, utilisez la [SetRange](../mfc/reference/cprogressctrl-class.md#setrange) fonction membre.  
  
 Pour définir la position, utilisez [fonction membre SetPos](../mfc/reference/cprogressctrl-class.md#setpos). Pour récupérer la position actuelle sans spécifier une nouvelle valeur, utilisez [GetPos](../mfc/reference/cprogressctrl-class.md#getpos). Par exemple, vous souhaiterez simplement interroger l’état de l’opération en cours.  
  
 Pour parcourir la position actuelle du contrôle de progression, utilisez [StepIt](../mfc/reference/cprogressctrl-class.md#stepit). Pour définir la quantité de chaque étape, utilisez [SetStep](../mfc/reference/cprogressctrl-class.md#setstep)  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CProgressCtrl](../mfc/using-cprogressctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

