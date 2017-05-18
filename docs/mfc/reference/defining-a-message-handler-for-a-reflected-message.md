---
title: "Définition d’un gestionnaire de messages pour un Message réfléchi | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.defining.msg.msghandler
dev_langs:
- C++
helpviewer_keywords:
- messages, reflected
- message handling, reflected messages
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0033c75d351aa201a0c18e81395d764b9d45761b
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>Définition d'un gestionnaire de messages pour un message réfléchi
Une fois que vous avez créé une nouvelle classe de contrôle MFC, vous pouvez définir des gestionnaires de messages pour celle-ci. Gestionnaires de messages réfléchis permettent à votre classe de contrôle gérer ses propres messages avant que le message est reçu par le parent. Vous pouvez utiliser la bibliothèque MFC [CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) fonction pour envoyer des messages à partir de votre contrôle à une fenêtre parente.  
  
 Cette fonctionnalité, vous pouvez, par exemple, créer une zone de liste qui se redessine elle-même, plutôt que de compter sur la fenêtre parente pour effectuer l’opération (owner drawn). Pour plus d’informations sur les messages réfléchis, consultez [gestion des Messages](../../mfc/handling-reflected-messages.md).  
  
 Pour créer un [contrôle ActiveX](../../mfc/activex-controls-on-the-internet.md) avec la même fonctionnalité, vous devez créer un projet pour le contrôle ActiveX.  
  
> [!NOTE]
>  Vous ne pouvez pas ajouter de message réfléchi (OCM_*Message*) pour un ActiveX contrôler à l’aide de la fenêtre Propriétés, comme décrit ci-dessous. Vous devez ajouter manuellement ces messages.  
  
### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-properties-window"></a>Pour définir un gestionnaire de messages pour un message réfléchi à partir de la fenêtre Propriétés  
  
1.  Ajouter un contrôle, telles qu’une liste, un contrôle rebar, une barre d’outils ou un contrôle d’arborescence, à votre projet MFC.  
  
2.  Dans l’affichage de classes, cliquez sur le nom de votre classe de contrôle.  
  
3.  Dans le [fenêtre Propriétés](/visualstudio/ide/reference/properties-window), le nom de classe de contrôle s’affiche dans le **nom de la classe** liste.  
  
4.  Cliquez sur le **Messages** pour afficher les messages Windows disponibles à ajouter au contrôle.  
  
5.  Faites défiler vers le bas dans la liste des messages dans la fenêtre Propriétés jusqu'à ce que l’en-tête **réfléchi**. Sinon, cliquez sur le **catégories** bouton et réduire l’affichage pour voir les **réfléchi** titre.  
  
6.  Sélectionnez le message réfléchi pour lequel vous souhaitez définir un gestionnaire. Messages réfléchis sont marqués d’un signe égal (=).  
  
7.  Cliquez sur la cellule dans la colonne de droite dans la fenêtre Propriétés pour afficher le nom proposé pour le gestionnaire en tant que \<ajouter >*HandlerName*. (Par exemple, le **= WM_CTLCOLOR** Gestionnaire de messages \<ajouter >**CtlColor**).  
  
8.  Cliquez sur le nom suggéré pour l’accepter. Le gestionnaire est ajouté à votre projet.  
  
     Les noms de gestionnaires de messages que vous avez ajouté apparaissent dans la colonne de droite de la fenêtre des messages réfléchis.  
  
9. Pour modifier ou supprimer un gestionnaire de messages, répétez les étapes 4 à 7. Cliquez sur la cellule qui contient le nom du gestionnaire à modifier ou supprimer et cliquez sur la tâche appropriée.  
  
## <a name="see-also"></a>Voir aussi  
 [Mappage de Messages à des fonctions](../../mfc/reference/mapping-messages-to-functions.md)   
 [Ajout de fonctionnalités à l’aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d’une classe](../../ide/adding-a-class-visual-cpp.md)   
 [Ajout d’une fonction membre](../../ide/adding-a-member-function-visual-cpp.md)   
 [Ajout d’une Variable membre](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Substitution d’une fonction virtuelle](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Gestionnaire de messages MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigation dans la Structure de classe](../../ide/navigating-the-class-structure-visual-cpp.md)

