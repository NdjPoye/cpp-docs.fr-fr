---
title: "D&#233;finition d&#39;un gestionnaire de messages pour un message r&#233;fl&#233;chi | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.defining.msg.msghandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestion des messages, messages réfléchis"
  - "messages, réfléchis"
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;finition d&#39;un gestionnaire de messages pour un message r&#233;fl&#233;chi
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lorsque vous avez créé une nouvelle classe de contrôle MFC, vous pouvez définir des gestionnaires de messages pour celle\-ci.  Les gestionnaires de messages réfléchis permettent à votre classe de contrôle de traiter ses propres messages avant la réception du message par le parent.  Vous pouvez utiliser la fonction MFC [CWnd::SendMessage](../Topic/CWnd::SendMessage.md) pour envoyer des messages à partir de votre contrôle à une fenêtre parente.  
  
 Cette fonctionnalité permet, par exemple, de créer une zone de liste qui se redessine elle\-même, sans demander à la fenêtre parente d'effectuer cette opération \(owner drawn\).  Pour plus d'informations sur les messages réfléchis, consultez [Gestion des messages ayant fait l'objet d'une réflexion](../../mfc/handling-reflected-messages.md).  
  
 Pour créer un [contrôle ActiveX](../../mfc/activex-controls-on-the-internet.md) avec la même fonctionnalité, vous devez créer un projet pour celui\-ci.  
  
> [!NOTE]
>  Vous ne pouvez pas ajouter de message réfléchi \(OCM\_*Message*\) pour un contrôle ActiveX à l'aide de la fenêtre Propriétés, de la manière décrite ci\-dessous.  Vous devez ajouter ces messages manuellement.  
  
### Pour définir un gestionnaire de messages pour un message réfléchi à partir de la fenêtre Propriétés  
  
1.  Ajoutez un contrôle \(par exemple une liste, un contrôle rebar, une barre d'outils ou un contrôle d'arborescence\) à votre projet MFC.  
  
2.  Dans l'affichage de classes, cliquez sur le nom de votre classe de contrôle.  
  
3.  Dans la [fenêtre Propriétés](../Topic/Properties%20Window.md), le nom de la classe de contrôle s'affiche dans la liste **Nom de la classe**.  
  
4.  Cliquez sur le bouton **Messages** pour afficher les messages Windows disponibles pouvant être ajoutés au contrôle.  
  
5.  Faites défiler la liste des messages dans la fenêtre Propriétés jusqu'à ce que l'en\-tête **Réfléchi** s'affiche.  Vous pouvez également cliquer sur le bouton **Catégories** et réduire la vue afin d'afficher l'en\-tête **Réfléchi**.  
  
6.  Sélectionnez le message réfléchi pour lequel vous souhaitez définir un gestionnaire.  Les messages réfléchis sont marqués d'un signe égal \(\=\).  
  
7.  Cliquez sur la cellule de la colonne de droite de la fenêtre Propriétés afin d'afficher le nom proposé pour le gestionnaire \<add\>*HandlerName*. \(Par exemple, le nom proposé pour le gestionnaire de messages **\=WM\_CTLCOLOR** suggère \<add\>**CtlColor**\).  
  
8.  Cliquez sur le nom proposé pour l'accepter.  Le gestionnaire est ajouté au projet.  
  
     Les noms des gestionnaires de messages que vous avez ajoutés s'affichent dans la colonne de droite de la fenêtre des messages réfléchis.  
  
9. Pour modifier ou supprimer un gestionnaire de messages, répétez les étapes 4 via 7.  Cliquez sur la cellule qui contient le nom de gestionnaire pour modifier ou supprimer et cliquez sur la tâche appropriée.  
  
## Voir aussi  
 [Mappage de messages à des fonctions](../../mfc/reference/mapping-messages-to-functions.md)   
 [Ajout de fonctionnalités à l'aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d'une classe](../../ide/adding-a-class-visual-cpp.md)   
 [Ajout d'une fonction membre](../../ide/adding-a-member-function-visual-cpp.md)   
 [Ajout d'une variable membre](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Substitution d'une fonction virtuelle](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC, gestionnaire de messages](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Parcours de la structure de classe](../../ide/navigating-the-class-structure-visual-cpp.md)