---
title: "Coupure des mots dans les contrôles RichEdit | Documents Microsoft"
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
- CRichEditCtrl class [MFC], word breaks in
- word breaks
- breaking words in CRichEditCtrl
- rich edit controls [MFC], word breaks in
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 12ae5d682515a6f266b7e41a2ff89148ea98c0b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="word-breaks-in-rich-edit-controls"></a>Coupure des mots dans les contrôles RichEdit
Un contrôle RichEdit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) appelle une fonction appelée « procédure word saut » pour trouver des coupures entre les mots et déterminer où il peut passer des lignes. Le contrôle utilise ces informations lorsque vous effectuez des opérations de retour et lors du traitement des combinaisons de touches CTRL + gauche et CTRL + droite. Une application peut envoyer des messages à un contrôle RichEdit pour remplacer la procédure à la césure par défaut, pour récupérer les informations de césure de mots et de déterminer quelle ligne un caractère donné tombe.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

