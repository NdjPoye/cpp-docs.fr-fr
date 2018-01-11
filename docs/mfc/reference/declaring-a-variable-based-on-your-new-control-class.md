---
title: "Déclaration d’une Variable basée sur votre nouvelle classe de contrôle | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.classes.control.variable
dev_langs: C++
helpviewer_keywords:
- variables [MFC], control classes
- control classes [MFC], variables
- classes [MFC], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5aa98f815d9f9322c11d4256c13c0c7a42b4ab66
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>Déclaration d'une variable basée sur votre nouvelle classe de contrôle
Une fois que vous avez créé une classe de contrôle MFC, vous pouvez déclarer une variable basée sur celui-ci. Pour fournir un contexte pour la nouvelle variable, vous devez ouvrir l’éditeur de boîte de dialogue et modifiez la boîte de dialogue dans laquelle vous souhaitez utiliser votre contrôle réutilisable. En outre, la boîte de dialogue doit avoir déjà associée à une classe. Pour plus d’informations sur l’utilisation de l’éditeur de boîte de dialogue, consultez [boîte de dialogue Éditeur](../../windows/dialog-editor.md).  
  
### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>Pour déclarer une variable en fonction de votre classe réutilisable  
  
1.  Lors de la modification de la boîte de dialogue, faites glisser un contrôle du même type que la classe de base de votre nouveau contrôle à partir de la barre d’outils de contrôle sur la boîte de dialogue.  
  
2.  Placez le pointeur de la souris sur le contrôle supprimé.  
  
3.  Tout en appuyant sur la touche CTRL ENFONCÉE, double-cliquez sur le contrôle.  
  
     Le [ajouter une Variable membre](../../ide/add-member-variable-wizard.md) boîte de dialogue s’affiche.  
  
4.  Dans le **accès** , sélectionnez l’accès correct pour votre contrôle.  
  
5.  Cliquez sur le **la variable de contrôle** case à cocher.  
  
6.  Dans le **nom de la Variable** , tapez un nom.  
  
7.  Sous **catégorie**, cliquez sur **contrôle**.  
  
8.  Dans le **ID de contrôle** liste, sélectionnez le contrôle que vous avez ajouté. Le **le type de Variable** liste affiche le type de variable correct et le **type de contrôle** zone doit afficher le type de contrôle correct.  
  
9. Dans le **commentaire** zone, ajouter des commentaires que vous souhaitez voir apparaître dans votre code.  
  
10. Cliquez sur **OK**.  
  
## <a name="see-also"></a>Voir aussi  
 [Mappage des Messages à des fonctions](../../mfc/reference/mapping-messages-to-functions.md)   
 [Ajout de fonctionnalités à l’aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d’une classe](../../ide/adding-a-class-visual-cpp.md)   
 [Ajout d’une fonction membre](../../ide/adding-a-member-function-visual-cpp.md)   
 [Ajout d’une Variable membre](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Une fonction virtuelle de substitution](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Gestionnaire de messages MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigation dans la Structure de classe](../../ide/navigating-the-class-structure-visual-cpp.md)
