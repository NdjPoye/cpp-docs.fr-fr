---
title: Types de projet Visual C++ | Documents Microsoft
ms.custom: 
ms.date: 10/30/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- programs [C++], projects
- project templates [Visual Studio], C++
- TODO comments [C++]
- projects [C++], types
- templates [C++], projects
- applications [C++], projects
- Visual C++ projects, types
ms.assetid: 7337987e-1e7b-4120-9a4b-94f0401f15e7
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a837aa04b0e0c2b8d3d9f5cfd48181a9ea23b346
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="visual-c-project-types"></a>Types de projets Visual C++

Vous pouvez utiliser un modèle de projet pour créer la structure de base du programme, les menus, les barres d’outils, les icônes, les références et les instructions `#include` adaptés au type de projet que vous voulez créer. Visual Studio intègre plusieurs types de modèles de projet Visual C++ qui s’accompagnent pour la plupart d’Assistants qui vous permettent de personnaliser vos projets au moment de les créer. Immédiatement après avoir créé un projet, vous pouvez générer et exécuter l’application ; Il est conseillé de génération intermittente à mesure que vous développez votre application.

Vous n’êtes pas tenu d’utiliser un modèle pour créer un projet. Cependant, dans la plupart des cas, c’est un choix judicieux, car il est plus facile de modifier les fichiers et la structure de projet fournis que de les créer entièrement.  
  
> [!NOTE]
> Vous pouvez créer un projet en langage C à partir de modèles de projet C++. Dans le projet généré, recherchez les fichiers ayant une extension de nom de fichier .cpp et remplacez-la par .c. Ensuite, dans la page **Propriétés du projet** du projet (et non de la solution), développez **Propriétés de configuration**, **C/C++** , puis sélectionnez **Avancé**. Modifiez le paramètre **Compilation sous** en choisissant **Compiler comme code C (/TC)**.

## <a name="project-templates"></a>Modèles de projet

Les modèles de projet inclus dans Visual Studio peut varier selon la version du produit et les charges de travail que vous avez installé. Si vous avez installé le développement de bureau avec une charge de travail de C++, Visual Studio propose ces modèles de projet Visual C++.

### <a name="windows-desktop"></a>Bureau Windows

|Modèle de projet|Description|  
|----------------------|-----------------------------| 
|[Application Console Windows](../windows/creating-a-console-application.md)|Projet de création d’une application console Windows.|
|[Application de bureau Windows](../windows/walkthrough-creating-windows-desktop-applications-cpp.md)|Projet de création d’une application de bureau (Win32) de Windows.|
|[Bibliothèque de liens dynamiques](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)|Projet de création d’une bibliothèque de liens dynamiques (DLL).|
|[Bibliothèque statique](../windows/walkthrough-creating-and-using-a-static-library-cpp.md)|Projet de création d’une bibliothèque statique (LIB).|
|Assistant de bureau Windows|Un Assistant permettant de créer des applications de bureau Windows et les bibliothèques avec des options supplémentaires.|

### <a name="general"></a>Général

|Modèle de projet|Description|
|----------------------|-----------------------------|
|Projet vide|Projet vide pour la création d’une application, une bibliothèque ou une DLL. Vous devez ajouter n’importe quel code ou les ressources requises.|
|[Projet Makefile](../ide/creating-a-makefile-project.md)|Système de génération de projet pour à l’aide d’un externe.|
|Projet d’éléments partagés|Un projet est utilisé pour le partage de fichiers entre plusieurs projets.|

### <a name="atl"></a>ATL

|Modèle de projet|Description|
|----------------------|-----------------------------|
|[Projet ATL](../atl/reference/creating-an-atl-project.md)|Un projet qui utilise Active Template Library.|

### <a name="test"></a>Tester

|Modèle de projet|Description|
|----------------------|-----------------------------|
|[Projet de Test unitaire natif](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)|Un projet qui contient des tests unitaires C++ natifs.|

### <a name="mfc"></a>MFC

Si vous ajoutez que le MFC et ATL prennent en charge le composant à votre installation de Visual Studio, ces modèles de projet sont ajoutés à Visual Studio.

|Modèle de projet|Description|
|----------------------|-----------------------------|
|[Application MFC](../mfc/reference/creating-an-mfc-application.md)|Projet de création d’une application qui utilise la bibliothèque Microsoft Foundation classes (MFC).|
|[Contrôle ActiveX MFC](../mfc/reference/creating-an-mfc-activex-control.md)|Projet de création d’un contrôle ActiveX qui utilise la bibliothèque MFC.|
|[DLL MFC](../mfc/reference/creating-an-mfc-dll-project.md)|Projet de création d’une bibliothèque de liens dynamiques qui utilise la bibliothèque MFC.|

### <a name="windows-universal-apps"></a>Applications Windows universelles

Si vous ajoutez le composant Outils de plateforme universelle Windows de C++ à votre installation de Visual Studio, ces modèles de projet sont ajoutés à Visual Studio.

Pour une vue d’ensemble des applications Windows universelles en C++, consultez [Universal Windows applications (C++)](../windows/universal-windows-apps-cpp.md).

|Modèle de projet|Description|
|----------------------|-----------------------------|
|Applications vide|Un projet pour une application de plateforme Windows universelle (UWP) d’une page qui n’a aucune disposition ni aucun contrôle prédéfini.|
|DirectX 11 App|Un projet pour une application de plateforme Windows universelle qui utilise DirectX 11.|
|Application DirectX 12|Un projet pour une application de plateforme Windows universelle qui utilise DirectX 12.|
|Application DirectX 11 et XAML|Un projet pour une application de plateforme Windows universelle qui utilise DirectX 11 et XAML.|
|Application de Test unitaire|Projet pour créer une application de tests unitaires pour les applications de plateforme Windows universelle (UWP).|
|DLL|Un projet pour une bibliothèque de liens dynamiques (DLL) native qui peut être utilisé par un composant d’application ou le runtime de plateforme Windows universelle.|
|Bibliothèque statique|Un projet pour une bibliothèque de liens statiques native (LIB) qui peut être utilisé par un composant d’application ou le runtime de plateforme Windows universelle.|
|Composant Windows Runtime|Projet pour un composant Windows Runtime qui peut être utilisé par une application de plateforme Windows universelle, quel que soit le langage de programmation dans lequel l’application est écrite.|
|Projet de package d’Application Windows|Un projet qui crée un package UWP qui permet à une application de bureau être distribués via le Store de Microsoft ou de chargement.|

## <a name="todo-comments"></a>Commentaires TODO

La plupart des fichiers générés par un modèle de projet contiennent des commentaires TODO pour vous aider à repérer les endroits où vous pouvez fournir votre propre code source. Pour plus d’informations sur l’ajout de code, consultez [Ajout de fonctionnalités avec les Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md) et [utilisation des fichiers de ressources](../windows/working-with-resource-files.md).

## <a name="see-also"></a>Voir aussi

[Création de projets de bureau à l’aide des Assistants Application](../ide/creating-desktop-projects-by-using-application-wizards.md)   
