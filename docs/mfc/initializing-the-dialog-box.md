---
title: "Initialisation de la boîte de dialogue | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6568c9bd9002df880a5501dd68e7050a4dc14706
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="initializing-the-dialog-box"></a>Initialisation de la boîte de dialogue
Une fois la boîte de dialogue zone et tous ses contrôles sont créés mais juste avant la boîte de dialogue boîte (de quelque type) s’affiche sur l’écran, l’objet de la boîte de dialogue [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) fonction membre est appelée. Pour une boîte de dialogue modale, cela se produit pendant la `DoModal` appeler. Pour une boîte de dialogue non modales `OnInitDialog` est appelée lorsque **créer** est appelée. En règle générale, vous substituez `OnInitDialog` pour initialiser les contrôles de la boîte de dialogue, par exemple définir le texte initial d’une zone d’édition. Vous devez appeler la `OnInitDialog` fonction membre de la classe de base `CDialog`, à partir de votre `OnInitDialog` remplacer.  
  
 Si vous souhaitez définir la couleur d’arrière-plan de votre boîte de dialogue (et que tous les autres boîtes de dialogue dans votre application), consultez [définissant la couleur d’arrière-plan de la boîte de dialogue](../mfc/setting-the-dialog-boxs-background-color.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Cycle de vie d’une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)

