---
title: "Validation des données de boîtes de dialogue | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- validating data [MFC], message boxes
- data validation [MFC], dialog boxes
- dialog boxes [MFC], validating data
- validating data [MFC], dialog box data entry
- DDV (dialog data validation) [MFC]
- data validation [MFC], message boxes
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 01766dd741ed87d9ac11b8858221a1bd09b0cf31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-data-validation"></a>Validation de données de boîtes de dialogue
Vous pouvez spécifier la validation en plus de l’échange de données en appelant les fonctions DDV, comme indiqué dans l’exemple de [Dialog Data Exchange](../mfc/dialog-data-exchange.md). Le `DDV_MaxChars` appel dans l’exemple vérifie que la chaîne d’entrée dans le contrôle de zone de texte n’est pas plue de 20 caractères. La fonction DDV avertit en général, l’utilisateur avec une boîte de message si la validation échoue et place le focus sur le contrôle qui posent problème afin de l’utilisateur peut entrer à nouveau les données. Une fonction DDV pour un contrôle donné doit être appelée immédiatement après la fonction DDX pour le même contrôle.  
  
 Vous pouvez également définir vos propres routines DDX et DDV personnalisées. Pour plus d’informations sur cela et d’autres aspects de DDX et DDV, consultez [MFC Technical Note 26](../mfc/tn026-ddx-and-ddv-routines.md).  
  
 Le [Assistant Ajout de Variable membre](../ide/add-member-variable-wizard.md) écrit tous le DDX et DDV appelle dans le mappage de données pour vous.  
  
## <a name="see-also"></a>Voir aussi  
 [Données de la boîte de dialogue échange et Validation](../mfc/dialog-data-exchange-and-validation.md)   
 [Cycle de vie d’une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)   
 [Échange de données de boîtes de dialogue](../mfc/dialog-data-exchange.md)

