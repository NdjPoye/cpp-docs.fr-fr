---
title: "Utilisation d&#39;une barre de bo&#238;te de dialogue avec un contr&#244;le rebar | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WM_EX_TRANSPARENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "barres de boîte de dialogue, utiliser avec des bandes rebar"
  - "rebar (contrôles), barres de boîte de dialogue"
  - "WS_EX_TRANSPARENT (style)"
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Utilisation d&#39;une barre de bo&#238;te de dialogue avec un contr&#244;le rebar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comme indiqué dans [Contrôles rebars et bandes](../mfc/rebar-controls-and-bands.md), chaque bande ne peut contenir qu'une fenêtre enfant \(ou contrôle\).  Il peut s'agir d'une limitation si vous souhaitez avoir plusieurs fenêtre enfant par bande.  Une solution pratique consiste à créer une ressource barre de la boîte de dialogue avec plusieurs vérifications puis d'ajouter une bande rebar \(contenant la barre de la boîte de dialogue\) pour vérifier rebar.  
  
 Normalement, si vous souhaitez que la bande de la barre de la boîte de dialogue pour être transparentes, vous définissez le style étendue par **WS\_EX\_TRANSPARENT** pour l'objet de la barre de la boîte de dialogue.  Toutefois, étant donné que **WS\_EX\_TRANSPARENT** a des problèmes liés à peindre correctement l'arrière\-plan d'une barre de la boîte de dialogue, vous devez exécuter le travail une quantité supplémentaire pour obtenir l'effet souhaité.  
  
 La procédure suivante décrit les étapes nécessaires pour effectuer la transparence sans utiliser le style étendue par **WS\_EX\_TRANSPARENT**.  
  
### Pour implémenter une barre de la boîte de dialogue donnée transparente dans une bande rebar  
  
1.  Utilisation [Ajoutez la boîte de dialogue classe](../mfc/reference/adding-an-mfc-class.md), ajoutez une nouvelle classe \(par exemple, `CMyDlgBar`\) qui implémente l'objet de la barre de la boîte de dialogue.  
  
2.  Ajoutez un gestionnaire pour l'événement `WM_ERASEBKGND`.  
  
3.  Dans le gestionnaire, modifiez le code existant pour faire correspondre l'exemple suivant :  
  
     [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/CPP/using-a-dialog-bar-with-a-rebar-control_1.cpp)]  
  
4.  Ajoutez un gestionnaire pour l'événement `WM_MOVE`.  
  
5.  Dans le gestionnaire, modifiez le code existant pour faire correspondre l'exemple suivant :  
  
     [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/CPP/using-a-dialog-bar-with-a-rebar-control_2.cpp)]  
  
 Les nouveaux handlers simulent la transparence de la barre de la boîte de dialogue lors de le transfert du message d'`WM_ERASEBKGND` de la fenêtre parente et en forçant un redessiner chaque fois que l'objet de la barre de la boîte de dialogue est déplacé.  
  
## Voir aussi  
 [Utilisation de CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)