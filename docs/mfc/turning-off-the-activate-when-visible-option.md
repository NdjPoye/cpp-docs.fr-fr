---
title: "La désactivation de l’Option actif quand Visible | Documents Microsoft"
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
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 25521d75921b377730a7f9afac71f2a60c055216
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="turning-off-the-activate-when-visible-option"></a>Désactivation de l'option Actif quand il est visible
Un contrôle a deux états : active ou inactive. En règle générale, ces États correspondaient à la présence du contrôle ait ou non une fenêtre. Un contrôle actif avait une fenêtre ; un contrôle inactif n’ont pas. Avec l’introduction de l’activation sans fenêtre, cette distinction n’est plus universelle, mais s’applique toujours à de nombreux contrôles.  
  
 Comparaison avec le reste de l’initialisation généralement effectuée par un contrôle ActiveX, la création d’une fenêtre est une opération très coûteuse. Dans l’idéal, un contrôle doit retarder créer sa fenêtre jusqu'à ce que c’est absolument nécessaire.  
  
 De nombreux contrôles n’est pas nécessaire d’active l’heure ensemble qu’ils sont visibles dans un conteneur. Souvent, un contrôle peut rester dans un état inactif jusqu'à ce que l’utilisateur effectue une opération qui requiert qu’il devienne actif (par exemple, en cliquant avec la souris ou en appuyant sur la touche TAB). Pour qu’un contrôle reste inactif jusqu'à ce que le conteneur doit l’activer, supprimez le **OLEMISC_ACTIVATEWHENVISIBLE** indicateur à partir des indicateurs de divers du contrôle :  
  
 [!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]  
  
 Le **OLEMISC_ACTIVATEWHENVISIBLE** indicateur est omis automatiquement si vous désactivez le **activer quand il est Visible** option dans le [paramètres de contrôle](../mfc/reference/control-settings-mfc-activex-control-wizard.md) page du ActiveX MFC Contrôle l’Assistant lorsque vous créez votre contrôle.  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôles ActiveX MFC : optimisation](../mfc/mfc-activex-controls-optimization.md)

