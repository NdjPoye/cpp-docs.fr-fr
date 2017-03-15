---
title: "Mappage de Messages à des fonctions | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.mapping.msg.function
dev_langs:
- C++
helpviewer_keywords:
- Windows messages [C++], adding message handlers
- message maps [C++], mapping messages to functions
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 584cc8b1f59f94d88718add5c21046c487b8556f
ms.lasthandoff: 02/24/2017

---
# <a name="mapping-messages-to-functions"></a>Mappage de messages à des fonctions
La fenêtre Propriétés permet de lier des gestionnaires de messages (fonctions membres des classes d’interface utilisateur MFC) aux messages générés par les ressources de votre application. Ils utilisent [tables des messages MFC](../../mfc/messages-and-commands-in-the-framework.md) pour créer la liaison.  
  
 Lorsque vous utilisez l’affichage de classes pour créer une nouvelle classe dérivée d’une des classes du framework, elle automatiquement place un complets et fonctionnels fichiers de classes dans l’en-tête (.h) et l’implémentation (.cpp) que vous spécifiez.  
  
> [!NOTE]
>  Pour ajouter une nouvelle classe qui ne gère pas les messages, créer la classe directement dans l’éditeur de texte.  
  
### <a name="to-define-or-remove-a-message-handler-using-the-properties-window"></a>Pour définir ou supprimer un gestionnaire de messages à l’aide de la fenêtre Propriétés  
  
1.  Dans Affichage de classes, cliquez sur la classe.  
  
2.  Dans la fenêtre Propriétés, cliquez sur le **Messages** bouton.  
  
    > [!NOTE]
    >  Le **Messages** bouton est disponible lorsque vous sélectionnez le nom de classe dans l’affichage de classes ou lorsque vous cliquez dans la fenêtre source.  
  
     Si votre projet comporte un gestionnaire pour un message, le nom du gestionnaire s’affiche dans la colonne de droite en regard du message.  
  
3.  Si le message n’a aucun gestionnaire, puis cliquez sur la cellule dans la colonne de droite dans la fenêtre Propriétés pour afficher le nom proposé pour le gestionnaire en tant que \<ajouter >*HandlerName*. (Par exemple, le `WM_TIMER` Gestionnaire de messages \<ajouter >`OnTimer`).  
  
4.  Cliquez sur le nom suggéré pour ajouter le code stub pour la fonction.  
  
5.  Pour modifier un gestionnaire de messages, double-cliquez sur le message dans l’affichage de classes et modifiez le code dans la fenêtre source.  
  
 Pour supprimer un gestionnaire de messages, double-cliquez sur le gestionnaire dans la colonne de droite et sélectionnez \<supprimer >*HandlerName*. Le code de fonction est commenté.  
  
## <a name="see-also"></a>Voir aussi  
 [Gestionnaire de messages MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Ajout de fonctionnalités à l’aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d’une classe](../../ide/adding-a-class-visual-cpp.md)   
 [Ajout d’une fonction membre](../../ide/adding-a-member-function-visual-cpp.md)   
 [Ajout d’une Variable membre](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Substitution d’une fonction virtuelle](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Ajout de gestionnaires d’événements pour les contrôles de boîte de dialogue](../../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [Navigation dans la Structure de classe](../../ide/navigating-the-class-structure-visual-cpp.md)

