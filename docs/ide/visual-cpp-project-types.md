---
title: "Types de projets Visual C++ | Microsoft Docs"
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
  - "programmes [C++], projets"
  - "modèles de projet [Visual Studio], C++"
  - "TODO, commentaires [C++]"
  - "projets [C++], types"
  - "modèles [C++], projets"
  - "applications [C++], projets"
  - "projets Visual C++, types"
ms.assetid: 7337987e-1e7b-4120-9a4b-94f0401f15e7
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Types de projets Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser un modèle de projet pour créer la structure de base du programme, les menus, les barres d’outils, les icônes, les références et les instructions `#include` adaptés au type de projet que vous voulez créer. Visual Studio intègre plusieurs types de modèles de projet Visual C\+\+ qui s’accompagnent pour la plupart d’Assistants qui vous permettent de personnaliser vos projets au moment de les créer. De suite après avoir créé un projet, vous pouvez le générer et exécuter l’application. Il est d’ailleurs recommandé de procéder à une génération intermittente à mesure que vous développez votre application.  
  
 Vous n’êtes pas tenu d’utiliser un modèle pour créer un projet. Cependant, dans la plupart des cas, c’est un choix judicieux, car il est plus facile de modifier les fichiers et la structure de projet fournis que de les créer entièrement.  
  
> [!NOTE]
>  Vous pouvez créer un projet en langage C à partir de modèles de projet C\+\+. Dans le projet généré, recherchez les fichiers ayant une extension de nom de fichier .cpp et remplacez\-la par .c. Ensuite, dans la page **Propriétés du projet** du projet \(et non de la solution\), développez **Propriétés de configuration**, **C\/C\+\+**, puis sélectionnez **Avancé**. Modifiez le paramètre **Compilation sous** en choisissant **Compiler comme code C \(\/TC\)**.  
  
## Modèles de projet  
 Visual Studio propose les modèles de projet Visual C\+\+ suivants.  
  
### Applications du Windows Store  
  
||  
|-|  
|[Modèles de projet C\#, VB et C\+\+ pour les applications du Store](http://go.microsoft.com/fwlink/p/?LinkID=262279)|  
  
### ATL  
  
|Modèle de projet|Comment créer un projet|  
|----------------------|-----------------------------|  
|Projet ATL|[Création d'un projet ATL](../atl/reference/creating-an-atl-project.md)|  
  
### CLR  
  
|Modèle de projet|  
|----------------------|  
|[\(NOTINBUILD\) Modèle de bibliothèque de classes \(C\+\+\)](http://msdn.microsoft.com/fr-fr/0d779bfa-5c5a-4b10-a9d5-a6791764a78f)|  
|[Comment : créer des applications console CLR](../dotnet/how-to-create-clr-console-applications-cpp-cli.md)|  
|[Modèle de projet vide CLR NOTINBUILD \(C\+\+\)](http://msdn.microsoft.com/fr-fr/f57c5572-5581-440f-b684-eec646764f08)|  
  
### Général  
  
|Modèle de projet|Comment créer un projet|  
|----------------------|-----------------------------|  
|Projet vide|[Création de projets et de solutions](../Topic/Creating%20Solutions%20and%20Projects.md)|  
|Assistant personnalisé|[Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)|  
|Projet Makefile|[Création d'un projet Makefile](../ide/creating-a-makefile-project.md)|  
  
### MFC  
  
|Modèle de projet|Comment créer un projet|  
|----------------------|-----------------------------|  
|Contrôle ActiveX MFC|[Création d'un contrôle ActiveX MFC](../mfc/reference/creating-an-mfc-activex-control.md)|  
|Application MFC|[Création d'une application MFC](../mfc/reference/creating-an-mfc-application.md)|  
|DLL MFC|[Création d'un projet DLL MFC](../mfc/reference/creating-an-mfc-dll-project.md)|  
  
### Test  
  
|Modèle de projet|Comment créer un projet|  
|----------------------|-----------------------------|  
|Projet de test managé|[Créer un projet de test unitaire](../Topic/Create%20a%20unit%20test%20project.md)|  
|Projet de test unitaire natif|[Tests unitaires de code natif avec l’Explorateur de tests](http://msdn.microsoft.com/fr-fr/8a09d6d8-3613-49d8-9ffe-11375ac4736c)|  
  
### Win32  
  
|Modèle de projet|Comment créer un projet|  
|----------------------|-----------------------------|  
|Projet de console Win32|[Création d'une application console](../windows/creating-a-console-application.md)|  
|Projet Win32|[Comment : créer une application de bureau Windows](../Topic/How%20to:%20Create%20a%20Windows%20Desktop%20Application.md)|  
  
## Commentaires TODO  
 La plupart des fichiers générés par un modèle de projet contiennent des commentaires TODO pour vous aider à repérer les endroits où vous pouvez fournir votre propre code source. Pour plus d’informations sur l’ajout de code, consultez [Ajout de fonctionnalités à l'aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md) et [Working with Resource Files](../mfc/working-with-resource-files.md).  
  
## Voir aussi  
 [Création de projets de bureau à l'aide des Assistants Application](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Utilisation de projets pour créer des applications](http://msdn.microsoft.com/fr-fr/3339fa90-bac2-4b95-8361-662a2e0e7dfe)   
 [Projets CLR](../ide/files-created-for-clr-projects.md)