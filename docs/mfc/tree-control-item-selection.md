---
title: "Sélection d’éléments de contrôle d’arborescence | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b38761b27c21dcf0fe3118d5b73e104cbaaa673d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="tree-control-item-selection"></a>Sélection d’éléments de contrôle d’arborescence
Lorsque la sélection passe d’un élément à un autre, un contrôle d’arborescence ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) envoie [TVN_SELCHANGING](http://msdn.microsoft.com/library/windows/desktop/bb773547) et [TVN_SELCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb773544) messages de notification. Ces deux messages contiennent une valeur qui spécifie si la modification est le résultat d’un clic de souris ou une combinaison de touches. Les notifications concernent également plus d’informations sur l’élément qui est activé à la sélection et l’élément qui perd la sélection. Vous pouvez utiliser ces informations pour définir les attributs d’élément qui dépendent de l’état de sélection de l’élément. Retour de **TRUE** en réponse à **TVN_SELCHANGING** empêche la sélection à partir de la modification ; retour **FALSE** permet la modification.  
  
 Une application peut modifier la sélection en appelant le [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) fonction membre.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

