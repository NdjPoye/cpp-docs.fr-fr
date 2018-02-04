---
title: "Ajout d’une Variable membre (Visual C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.classes.member.variable
dev_langs:
- C++
helpviewer_keywords:
- member variables, adding
- member variables
ms.assetid: 437783bd-8eb4-4508-8b73-7380116e9d71
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea3f5327568b1ad8380ce905987a570541e8f44f
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
# <a name="adding-a-member-variable--visual-c"></a>Ajout d'une variable membre (Visual C++)
Vous pouvez ajouter une variable membre à une classe à l’aide de la vue de la classe. Les variables membres peuvent être utilisées pour [échange de données et la validation des données](../mfc/dialog-data-exchange-and-validation.md), ou ils peuvent être génériques. L’Assistant de variable de membre de données est spécifiquement conçu pour prendre des informations pertinentes et l’utiliser pour insérer des éléments dans vos fichiers source aux emplacements appropriés. Vous pouvez ajouter une variable membre à partir de la [éditeur de boîte de dialogue](../windows/dialog-editor.md) dans [affichage des ressources](../windows/resource-view-window.md), ou à partir de [affichage de classes](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925).  
  
> [!NOTE]
>  Lorsque vous concevez et implémentez une boîte de dialogue, il peut s’avérer plus efficace d’utiliser la boîte de dialogue Éditeur pour ajouter les contrôles de boîte de dialogue, puis d’implémenter les variables membres de contrôles.  
  
### <a name="to-add-a-member-variable-for-a-dialog-control-in-resource-view-using-the-add-member-variable-wizard"></a>Pour ajouter une variable membre pour un contrôle de boîte de dialogue dans l’affichage des ressources à l’aide de l’Assistant Ajout de Variable membre  
  
1.  Dans l’affichage des ressources, développez le nœud du projet et le nœud de la boîte de dialogue pour afficher la liste des boîtes de dialogue du projet.  
  
2.  Double-cliquez sur la boîte de dialogue à laquelle vous souhaitez ajouter la variable membre pour l’ouvrir dans l’éditeur de boîte de dialogue.  
  
3.  Dans la boîte de dialogue affichée dans l’éditeur de boîte de dialogue, cliquez sur le contrôle auquel vous souhaitez ajouter la variable membre.  
  
4.  Dans le menu contextuel, cliquez sur **ajouter une Variable** pour afficher les [Assistant Ajout de Variable membre](../ide/add-member-variable-wizard.md).  
  
    > [!NOTE]
    >  Une valeur par défaut est déjà fournie dans **ID de contrôle**.  
  
5.  Fournissez les informations dans les zones appropriées de l’Assistant. Consultez [contrôles de boîte de dialogue et Types de variables](../ide/dialog-box-controls-and-variable-types.md) pour plus d’informations.  
  
6.  Cliquez sur **Terminer** pour ajouter le code de définition et l’implémentation au projet et fermer l’Assistant.  
  
### <a name="to-add-a-member-variable-from-class-view-using-the-add-member-variable-wizard"></a>Pour ajouter une variable membre à partir de l’affichage de classes à l’aide de l’Assistant Ajout de Variable membre  
  
1.  Dans [affichage de classes](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), développez le nœud de projet pour afficher les classes dans le projet.  
  
2.  Avec le bouton droit de la classe à laquelle vous souhaitez ajouter une variable.  
  
3.  Dans le menu contextuel, cliquez sur **ajouter**, puis cliquez sur **ajouter une Variable** pour afficher l’Assistant Ajout de Variable membre.  
  
4.  Fournissez les informations dans les zones appropriées de l’Assistant. Consultez [Assistant Ajout de Variable membre](../ide/add-member-variable-wizard.md) pour plus d’informations.  
  
5.  Cliquez sur **Terminer** pour ajouter le code de définition et l’implémentation au projet et fermer l’Assistant.  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout de fonctionnalités à l’aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d’une classe](../ide/adding-a-class-visual-cpp.md)   
 [Ajout d’une fonction membre](../ide/adding-a-member-function-visual-cpp.md)   
 [Gestionnaire de messages MFC](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigation dans la Structure de classe](../ide/navigating-the-class-structure-visual-cpp.md)