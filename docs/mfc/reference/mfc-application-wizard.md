---
title: "Assistant Application MFC | Microsoft Docs"
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
  - "vc.appwiz.mfc.exe.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers exécutables, créer"
  - "Assistant Application MFC"
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Assistant Application MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'Assistant Application MFC génère une application qui, lorsqu'elle est compilée, implémente les fonctions de base d'une application exécutable \(.exe\) Windows.  L'application de départ MFC inclut des fichiers sources C\+\+ \(.cpp\), des fichiers de ressources \(.rc\), des fichiers d'en\-tête \(.h\) et un fichier projet \(.vcxproj\).  Le code généré dans ces fichiers de démarrage est basé sur MFC.  
  
> [!NOTE]
>  Selon les options que vous sélectionnez, l'Assistant crée des fichiers supplémentaires dans votre projet.  Par exemple, si vous sélectionnez **Aide contextuelle** dans la page [Fonctionnalités avancées](../../mfc/reference/advanced-features-mfc-application-wizard.md), l'Assistant crée les fichiers nécessaires à la compilation des fichiers d'aide du projet.  Pour plus d'informations sur les fichiers créés par l'Assistant, consultez [Types de fichiers créés pour les projets Visual C\+\+](../../ide/file-types-created-for-visual-cpp-projects.md), ainsi que le fichier Readme.txt du projet.  
  
## Vue d'ensemble  
 La page Vue d'ensemble de l'Assistant décrit les paramètres d'application en cours pour l'application MFC que vous êtes en train de créer.  Par défaut, l'Assistant crée un projet comme suit :  
  
-   [Type d'application, Assistant Application MFC](../../mfc/reference/application-type-mfc-application-wizard.md)  
  
    -   Le projet est créé avec une prise en charge d'interface multidocument \(MDI\) avec onglets.  Pour plus d'informations, consultez [SDI et MDI](../../mfc/sdi-and-mdi.md).  
  
    -   Le projet utilise l'[Architecture document\/vue](../../mfc/document-view-architecture.md).  
  
    -   Le projet utilise des bibliothèques Unicode.  
  
    -   Le projet est créé à l'aide du style de projet Visual Studio et active la commutation de style visuel.  
  
    -   Le projet utilise les MFC dans une DLL partagée.  Pour plus d'informations, consultez [DLL en Visual C\+\+](../../build/dlls-in-visual-cpp.md).  
  
-   [Prise en charge des documents composés, Assistant Application MFC](../../mfc/reference/compound-document-support-mfc-application-wizard.md)  
  
    -   Le projet n'assure aucune prise en charge des documents composés.  
  
-   [Chaînes modèles de document, Assistant Application MFC](../../mfc/reference/document-template-strings-mfc-application-wizard.md)  
  
    -   Le projet utilise le nom du projet pour les chaînes modèles de document par défaut.  
  
-   [Prise en charge des bases de données, Assistant Application MFC](../../mfc/reference/database-support-mfc-application-wizard.md)  
  
    -   Le projet n'assure aucune prise en charge des bases de données.  
  
-   [Fonctionnalités de l'interface utilisateur, Assistant Application MFC](../../mfc/reference/user-interface-features-mfc-application-wizard.md)  
  
    -   Le projet implémente les fonctionnalités de l'interface utilisateur Windows standard, telles qu'un menu Système, une barre d'état, des boutons d'agrandissement et de réduction, une boîte de dialogue **À propos de**, une barre d'outils de menus et une barre ancrée standard, ainsi que des frames enfants.  
  
-   [Fonctionnalités avancées, Assistant Application MFC](../../mfc/reference/advanced-features-mfc-application-wizard.md)  
  
    -   Le projet prend en charge l'impression et l'aperçu avant impression.  
  
    -   Le projet prend en charge les contrôles ActiveX.  Pour plus d'informations, consultez [Ordre des opérations pour la création de contrôles ActiveX](../../mfc/sequence-of-operations-for-creating-activex-controls.md).  
  
    -   Le projet n'assure aucune prise en charge d'[Automation](../../mfc/automation.md), de [MAPI](../../mfc/mapi-support-in-mfc.md), de [Windows Sockets](../../mfc/windows-sockets-in-mfc.md) ou d'Active Accessibility.  
  
    -   Le projet prend en charge trois volets d'ancrage : **Explorateur**, **Sortie** et **Propriétés**.  
  
-   [Classes générées, Assistant Application MFC](../../mfc/reference/generated-classes-mfc-application-wizard.md)  
  
    -   La classe d'affichage du projet est dérivée de la classe CView \(voir [CView Class](../../mfc/reference/cview-class.md)\).  
  
    -   La classe d'application du projet est dérivée la classe CWinApp \(voir [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)\).  
  
    -   La classe de document du projet est dérivée la classe CDocument \(voir [CDocument Class](../../mfc/reference/cdocument-class.md)\).  
  
    -   La classe de frame principal du projet est dérivée la classe CMDIFrameWndEx \(voir [Classe CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)\).  
  
    -   La classe de frame enfant principal du projet est dérivée la classe CDMIChildWndEx \(voir [Classe CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md)\).  
  
 Pour changer ces paramètres par défaut, cliquez sur les titres d'onglet correspondants dans la colonne de gauche de l'Assistant et apportez les modifications dans la page appropriée.  
  
 Une fois que vous avez créé un projet d'application MFC, vous pouvez y ajouter des objets ou des contrôles à l'aide des [Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md) Visual C\+\+.  
  
## Voir aussi  
 [Création d'une application MFC](../../mfc/reference/creating-an-mfc-application.md)   
 [MFC, applications de bureau](../../mfc/mfc-desktop-applications.md)   
 [Utilisation des classes pour l'écriture d'applications pour Windows](../../mfc/using-the-classes-to-write-applications-for-windows.md)