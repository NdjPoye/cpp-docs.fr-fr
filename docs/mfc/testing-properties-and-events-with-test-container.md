---
title: "Test des propri&#233;t&#233;s et des &#233;v&#233;nements avec le conteneur de test | Microsoft Docs"
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
  - "ActiveX Control Test Container"
  - "contrôles ActiveX (C++), tester"
  - "déboguer des contrôles ActiveX"
  - "propriétés (MFC), tester"
  - "conteneur de test"
  - "tester, conteneurs de test"
  - "tstcon32.exe"
ms.assetid: 626867cf-fe53-4c30-8973-55bb93ef3917
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Test des propri&#233;t&#233;s et des &#233;v&#233;nements avec le conteneur de test
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'application de Test, expédiée Container dans Visual C\+\+, est un conteneur de contrôles ActiveX pour tester et déboguer des contrôles ActiveX.  Test Container permet au développeur de contrôle pour tester les fonctionnalités du contrôle en modifiant les propriétés, en appelant les méthodes, et de déclenchement ses événements.  Test Container peut afficher les journaux des notifications de liaison de données et fournit également des fonctionnalités pour tester une fonctionnalité de la persistance de contrôle ActiveX : vous pouvez enregistrer des propriétés à une source de données ou au substorage, le recharger, et consulter les données de flux stockées.  Cette section décrit comment utiliser les fonctionnalités de base de données de Test Container.  Pour obtenir des informations supplémentaires, sélectionnez le menu de **Aide** pendant l'exécution de Test Container.  
  
### Pour accéder au contrôle ActiveX Test Container  
  
1.  Construisez le [TSTCON Sample: ActiveX Control Test Container](../top/visual-cpp-samples.md).  
  
### Pour tester le contrôle ActiveX  
  
1.  Dans le menu **Modifier** de Test Container, cliquez sur **Insérer Nouveau Contrôle**.  
  
2.  Dans la boîte de dialogue **Insérer Nouveau Contrôle** , sélectionnez le contrôle et cliquez sur **OK**.  La commande apparaîtra dans le conteneur de commandes.  
  
    > [!NOTE]
    >  Si votre contrôle n'est pas répertorié dans la boîte de dialogue **Insérer un contrôle**, veillez à bien l'avoir enregistré avec la commande de **Register Controls** dans le menu de **Fichier** de Test Container.  
  
 À ce stade vous pouvez tester les propriétés et les événements de votre contrôle.  
  
#### Essayer les propriétés  
  
1.  Dans le menu **Contrôle**, cliquez sur **Appeler les méthodes**.  
  
2.  Dans la liste déroulante **Nom de méthode**, sélectionnez la méthode de PropPut de la propriété à tester.  
  
3.  Modifiez **Valeur du paramètre** ou **Type de paramètre** puis cliquez sur le bouton de **Valeur Set**.  
  
4.  Cliquez sur **Appeler** pour appliquer la nouvelle valeur à l'objet.  
  
     La propriété contient maintenant la nouvelle valeur.  
  
#### Pour tester des événements et spécifier la destination des informations d'événements.  
  
1.  Dans le menu **Outils**, cliquez sur **Options**.  
  
2.  Spécifiez la destination des informations d'événements.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Comment : déboguer un contrôle ActiveX](../Topic/How%20to:%20Debug%20an%20ActiveX%20Control.md)