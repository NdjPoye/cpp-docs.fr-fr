---
title: "Comment&#160;: ajouter des contr&#244;les de ruban et des gestionnaires d&#39;&#233;v&#233;nements | Microsoft Docs"
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
  - "gestionnaires d'événements, ajouter"
  - "contrôles du ruban, ajouter"
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Comment&#160;: ajouter des contr&#244;les de ruban et des gestionnaires d&#39;&#233;v&#233;nements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les contrôles du ruban sont des éléments, comme les boutons et les zones de liste déroulante, que vous ajoutez aux panneaux.  Les panneaux sont des zones de la barre de ruban qui affichent un groupe de contrôles connexes.  
  
 Dans cette rubrique, vous allez ouvrir le concepteur de ruban, ajouter un bouton, puis lier un événement qui affiche « Hello World ».  
  
### Pour ouvrir le Concepteur de ruban  
  
1.  Dans Visual Studio, dans le menu **Affichage**, cliquez sur **Affichage des ressources**.  
  
2.  Dans **Affichage des ressources**, double\-cliquez sur la ressource du ruban pour l'afficher dans l'aire de conception.  
  
### Pour ajouter un bouton et un gestionnaire d'événement  
  
1.  Depuis la **Barre d'outils**, cliquez sur **Bouton** et faites\-le glisser jusqu'à un panneau dans l'aire de conception.  
  
2.  Cliquez avec le bouton droit sur le bouton, puis cliquez sur **Ajouter un gestionnaire d'événements**.  
  
3.  Dans **Assistant Gestionnaire d'événements**, vérifiez les paramètres par défaut et cliquez sur **Ajouter**.  Pour plus d'informations, consultez [Assistant Gestionnaire d'événements](../ide/event-handler-wizard.md).  
  
4.  Dans l'éditeur de code, ajoutez le code suivant dans la fonction gestionnaire :  
  
    ```  
    MessageBox((LPCTSTR)L"Hello World");  
    ```  
  
## Voir aussi  
 [RibbonGadgets, exemple : application de gadgets du ruban](../top/visual-cpp-samples.md)   
 [Concepteur de ruban \(MFC\)](../mfc/ribbon-designer-mfc.md)