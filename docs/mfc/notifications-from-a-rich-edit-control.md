---
title: "Notifications d&#39;un contr&#244;le RichEdit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditCtrl (classe), notifications"
  - "messages, notification"
  - "notifications, de CRichEditCtrl"
  - "contrôles RichEdit, notifications"
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Notifications d&#39;un contr&#244;le RichEdit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les messages de notification d'événements affectant un contrôle RichEdit \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\).  Ils peuvent être traités par la fenêtre parente ou, en utilisant le renvoi de message, par le contrôle RichEdit lui\-même.  Les contrôles RichEdits prennent en charge tous les messages de notification utilisées avec les contrôles d'édition ainsi que plusieurs supplémentaires.  Vous pouvez déterminer les messages de notification un contrôle RichEdit envoie la fenêtre parente en définissant le masque d'« événement ».  
  
 Pour définir le filtre d'événement pour un contrôle RichEdit, utilisez la fonction membre d'[SetEventMask](../Topic/CRichEditCtrl::SetEventMask.md).  Vous pouvez récupérer le masque d'événement actuel d'un contrôle RichEdit à l'aide de la fonction membre d'[GetEventMask](../Topic/CRichEditCtrl::GetEventMask.md).  
  
 Les paragraphes suivants présentent plusieurs notifications spécifiques et leurs utilisations :  
  
-   **EN\_MSGFILTER** gestion de la notification d'**EN\_MSGFILTER** permet à une classe, ou le contrôle RichEdit ou sa fenêtre parente, filtrent tout clavier et l'entrée de la souris au contrôle.  Le gestionnaire peut empêcher le message de la souris ou clavier d'être traité ou de modifier le message en modifiant la structure spécifiée d'[MSGFILTER](http://msdn.microsoft.com/library/windows/desktop/bb787936).  
  
-   Handle d'**EN\_PROTECTED**le message de notification d'**EN\_PROTECTED** pour détecter si l'utilisateur essaie de modifier le texte par.  Pour marquer une plage de texte comme protégée, vous pouvez définir le résultat par caractère.  Pour plus d'informations, consultez l'[Mise en forme de caractères dans les contrôles RichEdits](../mfc/character-formatting-in-rich-edit-controls.md).  
  
-   **EN\_DROPFILES** vous pouvez permettre à l'utilisateur pour supprimer des fichiers dans un contrôle RichEdit lors de le traitement du message de notification d'**EN\_DROPFILES**.  La structure spécifiée d'[ENDROPFILES](http://msdn.microsoft.com/library/windows/desktop/bb787895) contient des informations sur les fichiers sont supprimés.  
  
-   **EN\_SELCHANGE** une application peut détecter lorsque la sélection actuelle change lors de le traitement du message de notification d'**EN\_SELCHANGE**.  Le message de notification spécifie une structure d'[SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb787952) contenant des informations sur la nouvelle sélection.  
  
## Voir aussi  
 [Utilisation de CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)