---
title: Substitution d’une fonction virtuelle (Visual C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.virtualfunc.override
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, overriding
- base classes, overriding virtual functions defined in
- Properties window, overriding virtual functions in
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8580d27442b0cae7e343a568beaa9aeae500461
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="overriding-a-virtual-function-visual-c"></a>Substitution d'une fonction virtuelle (Visual C++)
Vous pouvez substituer des fonctions virtuelles définies dans une classe de base à partir de Visual Studio [fenêtre Propriétés](/visualstudio/ide/reference/properties-window).  
  
### <a name="to-override-a-virtual-function-in-the-properties-window"></a>Pour remplacer une fonction virtuelle dans la fenêtre Propriétés  
  
1.  Dans l’affichage de classes, cliquez sur la classe.  
  
2.  Dans la fenêtre Propriétés, cliquez sur le **substitue** bouton.  
  
    > [!NOTE]
    >  Le **substitue** bouton est disponible lorsque vous sélectionnez le nom de classe dans l’affichage de classes ou lorsque vous cliquez sur dans la fenêtre source.  
  
     La colonne de gauche répertorie les fonctions virtuelles. Si le nom d’une fonction virtuelle apparaît également dans la colonne de droite, puis un remplacement a déjà été implémenté.  
  
3.  Si la fonction n’a aucune substitution, puis cliquez sur la cellule dans la colonne de droite dans la fenêtre Propriétés pour afficher le nom proposé de la fonction remplacer en tant que \<Ajouter >*FuncName*.  
  
4.  Cliquez sur le nom suggéré pour ajouter un code stub pour la fonction.  
  
5.  Pour modifier une fonction de substitution, double-cliquez sur le nom de la fonction dans l’affichage de classes et modifiez le code dans la fenêtre source.  
  
 Pour supprimer un remplacement, cliquez sur le nom de fonction de remplacement dans la colonne de droite et sélectionnez \<Supprimer >*FuncName*. Le code de fonction est commenté.  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout de fonctionnalités à l’aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d’une classe](../ide/adding-a-class-visual-cpp.md)   
 [Ajout d’une fonction membre](../ide/adding-a-member-function-visual-cpp.md)   
 [Ajout d’une Variable membre](../ide/adding-a-member-variable-visual-cpp.md)   
 [Gestionnaire de messages MFC](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigation dans la Structure de classe](../ide/navigating-the-class-structure-visual-cpp.md)