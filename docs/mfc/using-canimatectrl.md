---
title: "Utilisation de CAnimateCtrl | Microsoft Docs"
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
  - "CAnimateCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles animation (C++), CAnimateCtrl (classe)"
  - "CAnimateCtrl (classe), à propos de la classe CAnimateCtrl"
  - "contrôles (MFC), animation"
ms.assetid: 696c0805-bef0-4e2e-a9e7-b37b9215b7f0
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de CAnimateCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un contrôle animations, représenté par la classe [CAnimateCtrl](../mfc/reference/canimatectrl-class.md), est une fenêtre qui affiche un clip au format name \(AVI\) de format AVI — vidéo\/audio format standard windows.  Un clip AVI est un jeu de cadres bitmap, comme le film.  
  
 Étant donné que le thread continue d'exécuter lorsque le AVI clip s'affiche, il courante pour un contrôle animations consiste à afficher l'activité du système pendant une opération longue.  Par exemple, la boîte de dialogue de recherche windows affiche la loupe mobile comme recherche système pour un fichier.  
  
 Les contrôles animations peuvent jouer uniquement des clips AVI simples, et ils ne prennent pas en charge le bruit. \(Pour obtenir la liste complète des limitations, consultez [CAnimateCtrl](../mfc/reference/canimatectrl-class.md).\) Les fonctionnalités d'un contrôle animations sérieusement sont limitées et sujet à la modification, vous devez utiliser une autre solution telle que le contrôle de MCIWnd si vous avez besoin d'un contrôle pour fournir des fonctions du média de lecture et\/ou d'enregistrement.  Pour plus d'informations sur le contrôle de MCIWnd, consultez la documentation amovibles.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Utilisation d'un contrôle Animation](../mfc/using-an-animation-control.md)  
  
-   [Notifications envoyées par les contrôles d'animation](../mfc/notifications-sent-by-animation-controls.md)  
  
## Voir aussi  
 [Contrôles](../mfc/controls-mfc.md)