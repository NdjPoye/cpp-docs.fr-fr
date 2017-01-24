---
title: "Mappage de messages &#224; des fonctions | Microsoft Docs"
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
  - "vc.codewiz.mapping.msg.function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tables des messages (C++), mapper des messages à des fonctions"
  - "messages Windows (C++), ajouter des gestionnaires de messages"
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mappage de messages &#224; des fonctions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La fenêtre Propriétés vous permet de lier des gestionnaires de messages \(fonctions membres de classes d'interfaces utilisateur MFC\) aux messages générés par vos ressources d'applications.  Ils utilisent des [tables des messages MFC](../../mfc/messages-and-commands-in-the-framework.md) pour créer la liaison.  
  
 Si vous utilisez l'affichage de classes pour créer une nouvelle classe dérivée d'une des classes d'infrastructure, il place automatiquement une classe complète et fonctionnelle dans les fichiers d'en\-tête \(.h\) et d'implémentation \(.cpp\) que vous spécifiez.  
  
> [!NOTE]
>  Pour ajouter une nouvelle classe qui ne gère pas les messages, créez\-la directement dans l'éditeur de texte.  
  
### Pour définir ou supprimer un gestionnaire de messages à l'aide de la fenêtre Propriétés  
  
1.  Dans l'affichage de classes, cliquez sur la classe  
  
2.  Dans la fenêtre Propriétés, cliquez sur le bouton **Messages**.  
  
    > [!NOTE]
    >  Le bouton **Messages** est disponible si vous sélectionnez le nom de la classe dans l'affichage de classes ou si vous cliquez à l'intérieur de la fenêtre source.  
  
     Si votre projet possède un gestionnaire pour un message, son nom s'affiche dans la colonne de droite, en regard du message.  
  
3.  Si le message ne possède pas de gestionnaire, cliquez sur la cellule de la colonne de droite de la fenêtre Propriétés afin d'afficher le nom proposé pour le gestionnaire, indiqué au format suivant : \<add\>*HandlerName*. \(Par exemple, le nom proposé pour le gestionnaire de messages `WM_TIMER` est \<add\>`OnTimer`\).  
  
4.  Cliquez sur le nom proposé pour ajouter le code stub pour la fonction.  
  
5.  Pour modifier un gestionnaire de messages, double\-cliquez sur le message dans l'affichage de classes et modifiez le code dans la fenêtre source.  
  
 Pour supprimer un gestionnaire de messages, double\-cliquez sur le gestionnaire dans la colonne de droite et sélectionnez \<delete\>*HandlerName*.  Le code de la fonction est transformé en commentaires.  
  
## Voir aussi  
 [MFC, gestionnaire de messages](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Ajout de fonctionnalités à l'aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d'une classe](../../ide/adding-a-class-visual-cpp.md)   
 [Ajout d'une fonction membre](../../ide/adding-a-member-function-visual-cpp.md)   
 [Ajout d'une variable membre](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Substitution d'une fonction virtuelle](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Adding Event Handlers for Dialog Box Controls](../../mfc/adding-event-handlers-for-dialog-box-controls.md)   
 [Parcours de la structure de classe](../../ide/navigating-the-class-structure-visual-cpp.md)