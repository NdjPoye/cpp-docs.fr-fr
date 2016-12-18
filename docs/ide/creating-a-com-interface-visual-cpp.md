---
title: "Cr&#233;ation d&#39;une interface COM (Visual C++) | Microsoft Docs"
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
  - "vc.codewiz.com.creating.interfaces"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interfaces COM, créer"
ms.assetid: 1be84d3c-6886-4d1e-8493-56c4d38a96d4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;une interface COM (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ propose des Assistants et modèles permettant de créer des projets qui utilisent des interfaces de définition COM et des dispinterfaces pour vos objets COM et vos classes Automation.  
  
 Vous pouvez utiliser ces Assistants pour accomplir les trois tâches courantes ci\-dessous :  
  
-   [Ajout de la prise en charge ATL à votre projet MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md)  
  
     Ajoute la prise en charge ATL à une application MFC après la création d'un projet MFC à l'aide de l'[Assistant Application MFC](../mfc/reference/mfc-application-wizard.md), puis en exécutant l'Assistant Code **Ajouter la prise en charge ATL aux MFC**.  Cette prise en charge s'applique uniquement aux objets simples COM ajoutés à un fichier exécutable MFC ou à un projet DLL.  Ces objets ATL peuvent posséder plusieurs interfaces.  
  
-   [Création d'un contrôle ActiveX MFC](../mfc/reference/creating-an-mfc-activex-control.md)  
  
     Ouvre l'[Assistant Contrôle ActiveX MFC](../mfc/reference/mfc-activex-control-wizard.md) pour créer un contrôle ActiveX possédant une dispinterface et une table d'événements définies dans le fichier .idl et dans la classe de contrôle, respectivement.  
  
-   [Ajout d'un contrôle ATL](../atl/reference/adding-an-atl-control.md)  
  
     Utilise conjointement l'[Assistant Projet ATL](../atl/reference/atl-project-wizard.md) et l'[Assistant Contrôle ATL](../atl/reference/atl-control-wizard.md) pour créer un contrôle ActiveX ATL.  
  
     Vous pouvez également ajouter un contrôle ATL à un projet MFC auquel vous avez ajouté la prise en charge ATL, de la manière décrite ci\-dessus.  En outre, si vous sélectionnez **Contrôle ATL** dans la boîte de dialogue **Ajouter une classe** alors que vous n'avez pas encore ajouté la prise en charge ATL à votre projet MFC, Visual Studio affiche une boîte de dialogue vous demandant de confirmer l'ajout de la prise en charge ATL à votre projet MFC.  
  
     Cet Assistant crée une source IDL et une table COM dans les classes du projet.  
  
 Si un projet ATL est ouvert, la boîte de dialogue [Ajouter une classe](../ide/add-class-dialog-box.md) propose des Assistants et modèles supplémentaires pour l'ajout d'interfaces COM à votre projet.  Les Assistants suivants vous permettent de définir une ou plusieurs interfaces pour l'objet :  
  
-   [Assistant Composant ATL COM\+ 1.0](../atl/reference/atl-com-plus-1-0-component-wizard.md)  
  
-   [Assistant Objet simple ATL](../atl/reference/atl-simple-object-wizard.md)  
  
-   [Assistant Composant Active Server Page ATL](../atl/reference/atl-active-server-page-component-wizard.md)  
  
-   [Assistant Contrôle ATL](../atl/reference/atl-control-wizard.md)  
  
 Vous pouvez également implémenter de nouvelles interfaces sur votre contrôle COM en cliquant avec le bouton droit sur la classe de contrôle de l'objet dans l'Affichage de classes et en cliquant sur [Implémenter l'interface](../ide/implement-interface-wizard.md).  
  
> [!NOTE]
>  Visual Studio ne propose pas d'Assistant pour l'ajout d'une interface à un projet.  Vous pouvez ajouter une interface à un projet ATL ou [ajouter la prise en charge ATL à votre projet MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md) en ajoutant un objet simple à l'aide de l'[Assistant Objet simple ATL](../atl/reference/atl-simple-object-wizard.md).  Vous pouvez également ouvrir le fichier .idl du projet et créer l'interface en tapant :  
  
```  
interface IMyInterface {  
};  
  
```  
  
 Pour plus d'informations, consultez [Implémentation d'une interface](../ide/implementing-an-interface-visual-cpp.md) et [Ajout d'objets et de contrôles à un projet ATL](../atl/reference/adding-objects-and-controls-to-an-atl-project.md).  
  
 Visual C\+\+ propose différents modes d'affichage et plusieurs manières de [modifier les interfaces COM](../ide/editing-a-com-interface.md) définies pour vos projets.  L'[Affichage de classes](http://msdn.microsoft.com/fr-fr/8d7430a9-3e33-454c-a9e1-a85e3d2db925) propose des icônes pour les interfaces ou dispinterfaces éventuellement définies dans un fichier .idl de votre projet C\+\+.  
  
 Pour les classes d'objets COM fondés sur ATL, l'Affichage de classes lit la table COM dans la classe ATL afin d'afficher la relation entre la classe ATL et les interfaces éventuelles qu'elle implémente.  
  
 Dans l'Affichage de classes et ses menus contextuels, vous pouvez utiliser les interfaces pour :  
  
-   ajouter des objets ATL à une application fondée sur MFC ;  
  
-   ajouter des méthodes, des propriétés et des événements ;  
  
-   accéder directement au code d'interface d'un élément en double\-cliquant sur ce dernier.  
  
## Voir aussi  
 [Création de projets de bureau à l'aide des Assistants Application](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Ajout de fonctionnalités à l'aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md)