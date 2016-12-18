---
title: "Modification des &#233;tiquettes de contr&#244;les d&#39;arborescence | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl (classe), modifier les étiquettes"
  - "modifier les étiquettes de contrôles d'arborescence"
  - "modification d'étiquette dans la classe CTreeCtrl"
  - "contrôles d'arborescence, modification d'étiquette"
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Modification des &#233;tiquettes de contr&#244;les d&#39;arborescence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'utilisateur peut modifier directement les noms des éléments dans un contrôle d'arborescence \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) qui contient le style de **TVS\_EDITLABELS**.  L'utilisateur démarre la modification en cliquant sur le nom de l'élément qui est active.  Une application engage la modifier à l'aide de la fonction membre [EditLabel](../Topic/CTreeCtrl::EditLabel.md).  L'arborescence envoie une notification en cas de démarrage et lorsqu'il est annulée ou terminé.  Lorsque la modification est terminé, vous êtes chargé de mettre à jour le nom de l'élément, le cas échéant.  
  
 Lorsque le changement de nom commence, un contrôle d'arborescence envoie un message de notification [TVN\_BEGINLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773506).  Lors de cette notification, vous pouvez autoriser la modification des noms et empêcher la modification d'autres informations.  Retourne 0 autorise la modification, et retourner une valeur non nulle l'empêché.  
  
 Lorsque le changement de nom est annulée ou terminée, un contrôle d'arborescence envoie un message de notification [TVN\_ENDLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773515).  Le paramètre d'`lParam` est l'adresse d'une structure [NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418).  Le membre de **élément** est une structure [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) qui identifie l'élément y compris le texte modifié.  Vous êtes chargé de mettre à jour le nom de l'élément, le cas échéant, par exemple après avoir validé la chaîne modifiée.  Le membre **pszText** de`TV_ITEM` autorisé est 0 si la modification est annulé.  
  
 Lors de le changement de nom, généralement en réponse au message de notification [TVN\_BEGINLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773506), vous pouvez obtenir un pointeur vers le contrôle d'édition utilisée pour le changement de nom à l'aide de la fonction membre [GetEditControl](../Topic/CTreeCtrl::GetEditControl.md).  Vous pouvez appeler la fonction membre [SetLimitText](../Topic/CEdit::SetLimitText.md) du contrôle d'édition pour limiter la quantité de texte qu'un utilisateur peut entrer ou sous\-classe le contrôle d'édition pour désactiver et ignorer les caractères non valides.  Notez, toutefois, que le contrôle d'édition s'affiche uniquement *après* que**TVN\_BEGINLABELEDIT** est envoyé.  
  
## Voir aussi  
 [Utilisation de CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)