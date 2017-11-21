---
title: "Création de votre classe de boîte de dialogue | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cd80d55df3ae9adc4a586d1cc5387ee6d1f53282
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-your-dialog-class"></a>Création de votre classe de boîte de dialogue
Pour chaque boîte de dialogue dans votre programme, créez une nouvelle classe de boîte de dialogue pour travailler avec la ressource de boîte de dialogue.  
  
 [Ajout d’une classe](../ide/adding-a-class-visual-cpp.md) explique comment créer une nouvelle classe de boîte de dialogue. Lorsque vous créez une classe de boîte de dialogue avec l’Assistant Ajouter une classe, il écrit les éléments suivants le. H et. Fichiers CPP que vous spécifiez :  
  
 Dans le. Fichier de H :  
  
-   Une déclaration de classe pour la classe de boîte de dialogue. La classe est dérivée de [CDialog](../mfc/reference/cdialog-class.md).  
  
 Dans le. Fichier CPP :  
  
-   Une table des messages pour la classe.  
  
-   Un constructeur standard pour la boîte de dialogue.  
  
-   Une substitution de la [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) fonction membre. Modifiez cette fonction. Il est utilisé pour les fonctions d’échange et validation de données de boîte de dialogue, comme décrit ultérieurement dans [échange de données de boîtes de dialogue et la validation](../mfc/dialog-data-exchange-and-validation.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Création d’une classe de boîte de dialogue des Assistants Code](../mfc/creating-a-dialog-class-with-code-wizards.md)   
 [Cycle de vie d’une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)

