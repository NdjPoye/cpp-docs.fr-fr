---
title: "Utilisation d&#39;un contr&#244;le de touche d&#39;acc&#232;s rapide | Microsoft Docs"
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
  - "CHotKeyCtrl (classe), utilisation"
  - "contrôles hot key"
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Utilisation d&#39;un contr&#244;le de touche d&#39;acc&#232;s rapide
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'utilisation standard d'une commande de touche d'accès rapide suit le modèle ci\-dessous :  
  
-   Le contrôle est créé.  Si le contrôle est spécifié dans un modèle de la boîte de dialogue, la création est automatique lorsque la boîte de dialogue est créée. \(Vous devez avoir un membre [CAnimateCtrl](../mfc/reference/chotkeyctrl-class.md) dans la classe de la boîte de dialogue qui correspond au contrôle de touche d'accès rapide.\) Autrement, vous pouvez utiliser la fonction membre [Créer](../Topic/CHotKeyCtrl::Create.md) pour créer le contrôle dans une fenêtre enfant n'importe quelle fenêtre.  
  
-   Si vous souhaitez définir une valeur par défaut pour le contrôle, appelez la fonction membre [SetHotKey](../Topic/CHotKeyCtrl::SetHotKey.md).  Si vous souhaitez empêcher certains états de l'évolution, appelez [SetRules](../Topic/CHotKeyCtrl::SetRules.md).  Pour les contrôles dans une boîte de dialogue, le bon moment pour le faire est dans la fonction [OnInitDialog](../Topic/CDialog::OnInitDialog.md) de la boîte de dialogue.  
  
-   L'utilisateur interagit avec le contrôle en appuyant sur une combinaison de touches d'accès rapide lorsque le contrôle de touche d'accès rapide est activé.  L'utilisateur affiche ensuite d'une certaine façon que cette tâche est terminée, éventuellement en cliquant sur un bouton de la boîte de dialogue.  
  
-   Lorsque votre programme reçoit la notification selon laquelle l'utilisateur a sélectionné une touche d'accès rapide, il doit utiliser la fonction membre [GetHotKey](../Topic/CHotKeyCtrl::GetHotKey.md) pour récupérer les valeurs de la clé virtuelle ainsi que de décalage d'états à partir du contrôle des touches d'accès rapide.  
  
-   Une fois que vous connaissez la clé que l'utilisateur a sélectionné, vous pouvez définir la touche d'accès rapide à l'aide d'une des méthodes décrites dans [Définir une touche d'accès rapide](../mfc/setting-a-hot-key.md).  
  
-   Si le contrôle des touches d'accès rapides se trouve dans une boîte de dialogue, lui et l'objet `CHotKeyCtrl` seront détruits automatiquement.  Sinon, vous devez vérifier que le flux de contrôle et l'objet `CHotKeyCtrl` sont correctement détruits.  
  
## Voir aussi  
 [Utilisation de CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)