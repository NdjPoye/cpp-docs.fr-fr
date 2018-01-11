---
title: "Fermeture de la boîte de dialogue | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e4c311a8d09ac3e1329b495fc321028e9f674993
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="closing-the-dialog-box"></a>Fermeture de la boîte de dialogue
Boîte de dialogue modale se ferme lorsque l’utilisateur choisit un de ses boutons, généralement le bouton OK ou annuler. En choisissant le bouton OK ou sur Annuler provoque Windows envoyer l’objet de la boîte de dialogue un **BN_CLICKED** message de notification de contrôle avec le bouton ID de l’élément, soit **IDOK** ou **IDCANCEL**. `CDialog`Fournit des fonctions de gestionnaire par défaut pour ces messages : `OnOK` et `OnCancel`. Les gestionnaires par défaut appellent la `EndDialog` fonction membre pour fermer la boîte de dialogue. Vous pouvez également appeler `EndDialog` à partir de votre propre code. Pour plus d’informations, consultez la [EndDialog](../mfc/reference/cdialog-class.md#enddialog) fonction membre de classe `CDialog` dans les *référence MFC*.  
  
 Pour réorganiser pour la fermeture et la suppression d’une boîte de dialogue non modale, vous devez substituer `PostNcDestroy` et appeler le **supprimer** opérateur sur le **cela** pointeur. [Destruction de la boîte de dialogue](../mfc/destroying-the-dialog-box.md) explique les étapes suivantes.  
  
## <a name="see-also"></a>Voir aussi  
 [Cycle de vie d’une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)

