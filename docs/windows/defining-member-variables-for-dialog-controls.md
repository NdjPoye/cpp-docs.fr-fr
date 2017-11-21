---
title: "Définir des Variables membres pour les contrôles de boîte de dialogue | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog editor, defining member variables for controls
ms.assetid: 84347c63-c33c-4b04-91f5-6d008c45ba58
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f81b0d124db2a28b8d38c1a79d7569d8e46742b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="defining-member-variables-for-dialog-controls"></a>Définition de variables membres pour les contrôles de boîte de dialogue
Pour définir une variable membre pour un contrôle de boîte de dialogue à l'exception des boutons, vous pouvez utiliser la méthode suivante.  
  
> [!NOTE]
>  Cet article s'applique uniquement aux contrôles de boîte de dialogue dans un projet MFC. Projets ATL doivent utiliser la **nouveaux Messages Windows et gestionnaires d’événements** boîte de dialogue.  
  
### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>Pour définir une variable membre pour un contrôle de boîte de dialogue (à l'exception d'un bouton)  
  
1.  Dans le [éditeur de boîte de dialogue](../windows/dialog-editor.md), sélectionnez un contrôle.  
  
2.  Tout en maintenant la **CTRL** enfoncée, double-cliquez sur le contrôle de boîte de dialogue.  
  
     Le [Assistant Ajout de Variable membre](../ide/add-member-variable-wizard.md) s’affiche.  
  
3.  Tapez les informations appropriées dans le **ajouter une Variable membre** Assistant. Pour plus d’informations, consultez [Dialog Data Exchange](../mfc/dialog-data-exchange.md).  
  
4.  Cliquez sur **OK** pour revenir à l’éditeur de boîte de dialogue.  
  
    > [!TIP]
    >  Pour passer d'un contrôle de boîte de dialogue à son gestionnaire existant, double-cliquez sur le contrôle.  
  

  
 Vous pouvez également utiliser le **Variables membres** onglet **Assistant classe MFC** pour ajouter de nouvelles variables membres pour une classe spécifiée et afficher celles qui ont déjà été définis.  
  
 Spécifications  
  
 MFC  
  
## <a name="see-also"></a>Voir aussi  
 [Mappage des Messages à des fonctions](../mfc/reference/mapping-messages-to-functions.md)   
 [Ajout de fonctionnalités à l’aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Assistant classe MFC](../mfc/reference/mfc-class-wizard.md)   
 [Ajout d’une classe](../ide/adding-a-class-visual-cpp.md)   
 [Ajout d’une fonction membre](../ide/adding-a-member-function-visual-cpp.md)   
 [Ajout d’une Variable membre](../ide/adding-a-member-variable-visual-cpp.md)   
 [Une fonction virtuelle de substitution](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Gestionnaire de messages MFC](../mfc/reference/adding-an-mfc-message-handler.md)

