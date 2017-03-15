---
title: "Testing the Modified ATL DHTML Control | Microsoft Docs"
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
  - "DHTML controls, tester"
  - "contrôles HTML, tester"
  - "testing controls"
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Testing the Modified ATL DHTML Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Essayez votre nouveau contrôle pour voir comment il fonctionne maintenant.  
  
#### Pour générer et tester le contrôle modifié  
  
1.  Régénérez le projet et ouvrez \-le dans l'outil Test Container.  Consultez [propriétés et événements de test avec Test Container](../mfc/testing-properties-and-events-with-test-container.md) pour plus d'informations sur l'accès à l'outil Test Container.  
  
     Redimensionnez le contrôle pour afficher tous les boutons que vous avez ajoutés.  
  
2.  Examinez les deux boutons que vous avez inséré en modifiant le HTML.  Chaque bouton permet d'atteindre le label que vous avez identifié dans [Modifier le contrôle ATL DHTML](../atl/modifying-the-atl-dhtml-control.md): **Refresh** et **HelloHTML**.  
  
3.  Testez les deux nouveaux boutons pour voir comment ils s'exécutent.  
  
 Testez maintenant les méthodes qui ne font pas partie de l'interface utilisateur.  
  
1.  Mettez en surbrillance le contrôle, la bordure est activée.  
  
2.  Dans le menu de **Control** , cliquez sur **Invoke Methods**.  
  
 Les méthodes dans la liste étiquetée **Nom de la méthode** sont les méthodes que le conteneur peut appeler : `MethodInvoked`et`GoToURL`.  Toutes les autres méthodes sont contrôlées par l'interface utilisateur.  
  
1.  Sélectionnez une méthode pour appeler et cliquez sur `Invoke` pour afficher le message de la méthode ou pour naviguer vers www.microsoft.com.  
  
2.  Dans la boîte de dialogue d' **Invoke Methods** , cliquez sur **Fermer**.  
  
 Pour en savoir plus sur les différents éléments et fichiers qui composent un contrôle ATL DHTML, consultez l' [Identifier les éléments du projet de contrôle DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md).  
  
## Voir aussi  
 [Prise en charge pour un contrôle DHTML](../atl/atl-support-for-dhtml-controls.md)