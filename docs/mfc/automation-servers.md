---
title: "Serveurs Automation | Microsoft Docs"
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
  - "Automation (serveurs)"
  - "composants COM, Automation (serveurs)"
  - "tables de dispatch, Automation (serveurs)"
  - "serveurs, Automation"
ms.assetid: 523fd155-51ce-4f91-b986-b74bdbdd7d92
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Serveurs Automation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'automatisation rend possible pour votre application la manipulation d'objets implémentés dans une autre application, ou l'exposition d'objets pour qu'ils puissent être manipulés.  Un serveur d'automatisation est une application qui montre les objets programmables \(appelés objets d'automatisation\) à d'autres applications \(appelées [Clients d'automatisation](../mfc/automation-clients.md)\).  Les serveurs d'automatisation sont parfois appelés composants d'automatisation.  
  
 Montrer les objets d'automatisation permets aux clients d'automatiser certaines procédures en accédant directement aux objets et aux fonctionnalités que le serveur rend disponibles.  Montrer les objets de cette manière est bénéfique lorsque des applications fournissent des fonctionnalités qui sont utiles à d'autres applications.  Par exemple, un module de traitement de mots peut montrer sa fonctionnalité de vérification de l'orthographe pour qu'un autre programme puisse l'utiliser.  L'exposition d'objets permet alors aux vendeurs d'améliorer les fonctionnalités de leurs applications en utilisant la fonctionnalité prête à l'emploi d'autres applications.  
  
 Ces objets d'Automation possèdent des propriétés et des méthodes qui leur servent d'interface externe.  Les propriétés sont appelées les attributs des objets d'Automation.  Les propriétés sont comme les membres de données d'une classe C\+\+.  Les méthodes sont des fonctions qui utilisent des objets d'Automation.  Les méthodes sont comme les fonctions membres publiques d'une classe en C\+\+.  
  
> [!NOTE]
>  Bien que les propriétés sont comme les membres de données C\+\+, elles ne sont pas directement accessibles.  Pour fournir un accès transparent, installez une variable interne dans l'objet d'Automation avec une paire de fonctions d'obtention\/d'initialisation pour y accéder.  
  
 En exposant des fonctionnalités d'application via une interface commune et bien définie, Automation permet de générer des applications dans un seul langage de programmation général, tel que Microsoft Visual Basic, et non pas dans des macro\-langages spécifiques à chaque application.  
  
##  <a name="_core_support_for_automation_servers"></a> Prise en charge des serveurs d'Automation  
 Visual C\+\+ et l'infrastructure MFC fournissent la prise en charge complète des serveurs Automation.  Ils gèrent une grande partie de la charge mémoire générée par un serveur Automation, vous pouvez concentrer vos efforts sur la fonctionnalité de votre application.  
  
 Le mécanisme principal de l'infrastructure pour la prise en charge de l'automatisation est la table d'envoi, un ensemble de macros qui s'étend dans les déclarations et les appels nécessaires pour exposer les méthodes et les propriétés pour OLE.  Une table classique de dispatch ressemble à ceci :  
  
 [!code-cpp[NVC_MFCAutomation#1](../mfc/codesnippet/CPP/automation-servers_1.cpp)]  
  
 La fenêtre des Propriétés et l'Affichage de classes aident à maintenir les tables de dispatch.  Lorsque vous ajoutez une nouvelle méthode ou propriété dans une classe, Visual C\+\+ ajoute une macro correspondant à `DISP_FUNCTION` ou `DISP_PROPERTY` avec des paramètres indiquant le nom de la classe, les noms externes et internes de la méthode, propriété, et les types de données.  
  
 La boîte de dialogue **Ajouter une classe** simplifie également la déclaration de classes d'Automation et la gestion de leurs propriétés et opérations.  Lorsque vous utilisez la boîte de dialogue Ajouter une Classe pour ajouter une classe à votre projet, vous spécifiez sa classe de base.  Si la classe de base permet l'automatisation, la boîte de dialogue Ajouter une Classe affiche les commandes que vous utilisez pour spécifier si la nouvelle classe doit prendre en charge l'automation, si elle est « OLE créable » \(autrement dit, si les objets de la classe peuvent être créés sur une requête d'un client COM\), ainsi que le nom externe pour que le client COM l'utilise.  
  
 La boîte de dialogue **Ajouter une classe** créé alors une déclaration de classe, y compris les macros appropriées pour les fonctionnalités OLE que vous avez spécifiées.  Elle ajoute également le squelette du code pour l'implémentation des fonctions membres de votre classe.  
  
 L'Application Wizard MFC simplifie les étapes de l'obtention de l'application de serveur Automation à partir de rien.  Si vous sélectionnez la case à cocher **Automation** de la page **Fonctionnalités avancées**, l'Application Wizard MFC ajoute à la fonction de votre application `InitInstance` les appels requis pour stocker vos objets Automation et exécuter l'application en tant que serveur Automation.  
  
### Que voulez\-vous faire ?  
  
-   [En savoir plus sur les clients Automation](../mfc/automation-clients.md)  
  
-   [En savoir plus sur la classe CCmdTarget](../mfc/reference/ccmdtarget-class.md)  
  
-   [En savoir plus sur la classe COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)  
  
## Voir aussi  
 [Automation](../mfc/automation.md)   
 [Assistant Application MFC](../mfc/reference/mfc-application-wizard.md)