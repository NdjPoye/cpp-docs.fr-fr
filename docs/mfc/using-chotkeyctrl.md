---
title: "Utilisation de CHotKeyCtrl | Microsoft Docs"
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
  - "CHotKeyCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHotKeyCtrl (classe), utilisation"
  - "contrôles hot key"
  - "clés, hot et CHotKeyCtrl"
ms.assetid: 9b207117-d848-4224-8888-c3d197bb0c95
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de CHotKeyCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un contrôle de touche rapide d'accès, représenté par la classe [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md), est une fenêtre qui affiche une représentation textuelle de la combinaison de touches les types d'utilisateur dans ce mode, telle que. CTRL\+SHIFT\+Q.  Il contient également une représentation interne de cette clé sous forme de code de clé virtuelle et d'ensemble d'indicateurs qui représentent l'état de l'équipe.  Le contrôle de touche rapide d'accès ne définit pas réellement la touche rapide d'accès \(ce qui appartient à votre programme\). \(Pour obtenir la liste de codes touche virtuelle standard, consultez Winuser.h.\)  
  
 Utilisez un contrôle de touche rapide d'accès pour obliger un utilisateur à entrer une touche rapide d'accès associée à une fenêtre ou un thread.  Les contrôles de touche rapide d'accès sont souvent utilisés dans les boîtes de dialogue \(par exemple, vous pouvez afficher lors de la demande à l'utilisateur d'affecter une touche rapide d'accès\).  Il incombe de votre programme de récupérer des valeurs décrivant la touche rapide d'accès du contrôle de touche rapide d'accès d'appeler des fonctions appropriées pour associer la touche rapide d'accès avec une fenêtre ou un thread.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Utilisation d'un contrôle de touche rapide d'accès.](../mfc/using-a-hot-key-control.md)  
  
-   [Définition d'une touche rapide d'accès.](../mfc/setting-a-hot-key.md)  
  
-   [Touches globales rapides d'accès.](../mfc/global-hot-keys.md)  
  
-   [Touches rapides d'accès spécifiques aux threads](../mfc/thread-specific-hot-keys.md)  
  
## Voir aussi  
 [Contrôles](../mfc/controls-mfc.md)