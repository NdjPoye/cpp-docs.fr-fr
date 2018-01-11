---
title: "L’activation des info-bulles | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0555af785d75c9247eb365a03a51161441a4722a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="enabling-tool-tips"></a>Activation des info-bulles
Vous pouvez activer la prise en charge d’outils Conseil pour les contrôles enfants d’une fenêtre (par exemple, les contrôles sur une boîte de dialogue ou d’affichage formulaire).  
  
### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>Pour activer les info-bulles pour les contrôles enfants d’une fenêtre  
  
1.  Appelez `EnableToolTips` pour la fenêtre pour laquelle vous souhaitez fournir des info-bulles.  
  
2.  Fournissez une chaîne pour chaque contrôle dans votre [la notification TTN_NEEDTEXT](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) gestionnaire. Le gestionnaire se trouve dans la table des messages de la fenêtre qui contient les contrôles enfants (par exemple, la classe du formulaire). Ce gestionnaire doit appeler une fonction qui identifie le contrôle et définit **pszText** pour spécifier le texte utilisé par le contrôle info-bulle.  
  
## <a name="see-also"></a>Voir aussi  
 [Info-bulles dans les fenêtres non dérivées de CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

