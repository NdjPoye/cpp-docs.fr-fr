---
title: "Conteneurs de contr&#244;les ActiveX | Microsoft Docs"
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
  - "conteneurs de contrôles ActiveX (C++)"
  - "contrôles OLE (C++), conteneurs"
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conteneurs de contr&#244;les ActiveX
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un conteneur de contrôles ActiveX est un conteneur qui prend entièrement en charge les contrôles ActiveX et peut les incorporer dans ses propres fenêtres ou dialogues.  Un contrôle ActiveX est un composant logiciel réutilisable que vous pouvez utiliser dans les projets de développement.  Les contrôles permettent à l'utilisateur de votre application d'accéder à des base de données, de surveiller des données, et d'effectuer des sélections dans vos applications.  Pour plus d'informations sur les contrôles ActiveX, consultez l'article [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md).  
  
 Les conteneurs de contrôle prennent généralement deux formes dans un projet :  
  
-   Boîtes de dialogue et fenêtres sous forme de dialogue telles que des modes formulaire, où un contrôle ActiveX est utilisé quelque part dans la boîte de dialogue.  
  
-   Fenêtres dans une application, où un contrôle ActiveX est utilisé dans la barre d'outils, ou tout autre emplacement dans la fenêtre d'utilisateur.  
  
 Le conteneur de contrôles ActiveX interagit avec le contrôle via des [méthodes](../mfc/mfc-activex-controls-methods.md) exposées et des [propriétés](../mfc/mfc-activex-controls-properties.md).  Ces méthodes et propriétés, accessibles et modifiées par le conteneur de contrôle, sont accessibles par le biais d'une classe wrapper du projet au conteneur de contrôles ActiveX.  Le contrôle ActiveX incorporé peut également interagir avec le conteneur de déclenchement \(émission\) [événements](../mfc/mfc-activex-controls-events.md) pour notifier le conteneur qu'une action s'est produite.  Le conteneur de contrôle peut choisir de réagir à ces notifications ou non.  
  
 Des éléments supplémentaires décrivent plusieurs rubriques, de la création d'un projet conteneur de contrôles ActiveX aux problèmes de base d'implémentation liés aux conteneurs de contrôle ActiveX créés avec Visual C\+\+ :  
  
-   [Création d'un conteneur de contrôles ActiveX MFC](../mfc/reference/creating-an-mfc-activex-control-container.md)  
  
-   [Conteneurs de contrôles ActiveX](../mfc/containers-for-activex-controls.md)  
  
-   [Conteneurs de contrôles ActiveX : activation manuelle d'une relation contenant\-contenu de contrôle ActiveX](../mfc/activex-control-containers-manually-enabling-activex-control-containment.md)  
  
-   [Conteneurs de contrôles ActiveX : insertion d'un contrôle dans une application de conteneur de contrôle](../mfc/inserting-a-control-into-a-control-container-application.md)  
  
-   [Conteneurs de contrôles ActiveX : association d'un contrôle ActiveX à une variable membre](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)  
  
-   [Conteneurs de contrôles ActiveX : gestion d'événements à partir d'un contrôle ActiveX](../mfc/activex-control-containers-handling-events-from-an-activex-control.md)  
  
-   [Conteneurs de contrôles ActiveX : consultation et modification des propriétés de contrôle](../mfc/activex-control-containers-viewing-and-modifying-control-properties.md)  
  
-   [Conteneurs de contrôles ActiveX : programmation de contrôles ActiveX dans un conteneur de contrôles ActiveX](../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
-   [Conteneurs de contrôles ActiveX : utilisation de contrôles dans un conteneur autre que de boîte de dialogue](../mfc/activex-control-containers-using-controls-in-a-non-dialog-container.md)  
  
 Pour plus d'informations sur l'utilisation des contrôles ActiveX dans une boîte de dialogue, consultez les rubriques [Éditeur de boîtes de dialogue](../mfc/dialog-editor.md).  
  
 Pour obtenir la liste des articles qui expliquent les détails de développement des contrôles ActiveX à l'aide de Visual C\+\+ et les classes de contrôle ActiveX MFC, consultez [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md).  Les éléments sont regroupées par catégories fonctionnelles.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)