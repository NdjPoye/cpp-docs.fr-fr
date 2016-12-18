---
title: "Contr&#244;le ActiveX MFC (Assistant) | Microsoft Docs"
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
  - "vc.appwiz.mfc.ctl.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX (C++), MFC"
  - "Contrôle ActiveX MFC (Assistant)"
  - "contrôles ActiveX MFC (C++), Assistants"
  - "contrôles OLE (C++)"
  - "contrôles OLE (C++), créer"
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;le ActiveX MFC (Assistant)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un contrôle ActiveX est un type spécifique de [serveur Automation](../../mfc/automation-servers.md) ; c'est un composant réutilisable.  L'application qui héberge le contrôle ActiveX est le [client Automation](../../mfc/automation-clients.md) de ce contrôle.  Si vous souhaitez créer un composant réutilisable de ce type, utilisez l'Assistant Contrôle ActiveX MFC pour créer votre contrôle.  Pour plus d'informations, consultez [Contrôles ActiveX MFC](../../mfc/mfc-activex-controls.md).  
  
 Vous pouvez également utiliser l'[Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md) pour créer une application MFC de type serveur Automation.  
  
 Un contrôle ActiveX créé avec cet Assistant peut posséder une interface utilisateur ou bien être invisible.  Vous pouvez indiquer cette option dans la page [Paramètres du contrôle](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) de l'Assistant.  Un contrôle Timer est un exemple de contrôle ActiveX qui peut être défini pour être invisible.  
  
 Les contrôles ActiveX peuvent posséder une interface utilisateur complexe.  Certains contrôles s'apparentent à des formulaires encapsulés : un contrôle peut contenir de nombreux champs, chacun comportant un contrôle Windows à sa droite.  Par exemple, un objet pièce automobile implémenté en tant qu'objet ActiveX MFC peut posséder une interface utilisateur de type formulaire, qui permet aux utilisateurs de lire et modifier le numéro de la pièce, sa désignation ou d'autres informations.  Pour plus d'informations, consultez [Contrôles ActiveX MFC](../../mfc/mfc-activex-controls.md).  
  
 Si vous souhaitez créer un conteneur pour vos objets ActiveX, consultez [Création d'un conteneur de contrôles ActiveX](../../mfc/reference/creating-an-mfc-activex-control-container.md).  
  
 Le programme de démarrage MFC inclut des fichiers sources \(.cpp\), des fichiers de ressources \(.rc\) et un fichier projet \(.vcxproj\) C\+\+.  Le code généré dans ces fichiers de démarrage est basé sur MFC.  
  
 La liste d'exemples ci\-dessous présente les types d'améliorations que vous pouvez apporter à votre contrôle ActiveX, et les tâches à effectuer pour y parvenir :  
  
-   [Optimisation d'un contrôle ActiveX](../../mfc/mfc-activex-controls-optimization.md)  
  
-   [Ajout d'événements stock à un contrôle ActiveX](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)  
  
-   [Ajout d'événements personnalisés](../../mfc/mfc-activex-controls-adding-custom-events.md)  
  
-   [Ajout de méthodes stock](../../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [Ajout de méthodes personnalisées](../../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [Ajout de propriétés stock](../../mfc/mfc-activex-controls-adding-stock-properties.md)  
  
-   [Ajout de propriétés personnalisées](../../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [Programmation de contrôles ActiveX dans un conteneur de contrôles ActiveX](../../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
## Vue d'ensemble  
 Cette page de l'Assistant décrit les paramètres d'application en cours pour le nouveau projet de contrôle ActiveX MFC.  Par défaut, l'Assistant crée un projet comme suit :  
  
-   Le projet par défaut ne génère ni licence utilisateur, ni fichier d'aide.  Vous pouvez modifier ces paramètres par défaut dans la page [Paramètres de l'application](../../mfc/reference/application-settings-mfc-activex-control-wizard.md).  Seules les sélections effectuées dans cette page de l'Assistant Contrôle ActiveX MFC sont prises en compte dans la page **Vue d'ensemble**.  
  
-   Le projet contient une classe de contrôle et une classe de page de propriétés, basées sur le nom du projet.  Vous pouvez modifier les noms de votre projet et des fichiers associés dans la page [Noms du contrôle](../../mfc/reference/control-names-mfc-activex-control-wizard.md).  
  
-   Le contrôle n'est pas créé à partir d'un contrôle Windows existant, est activé lorsqu'il devient visible, possède une interface utilisateur et propose une boîte de dialogue **À propos de**.  Vous pouvez modifier ces paramètres par défaut dans la page [Paramètres du contrôle](../../mfc/reference/control-settings-mfc-activex-control-wizard.md).  
  
## Voir aussi  
 [Création et gestion de projets Visual C\+\+](../../ide/creating-and-managing-visual-cpp-projects.md)   
 [Types de projets Visual C\+\+](../../ide/visual-cpp-project-types.md)   
 [Concepts](../../atl/active-template-library-atl-concepts.md)