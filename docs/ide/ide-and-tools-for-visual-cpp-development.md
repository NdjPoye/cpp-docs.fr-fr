---
title: "IDE et outils de d&#233;veloppement Visual&#160;C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "Visual C++, outils de développement"
ms.assetid: 56eabafb-1956-4f0f-bec5-29b887763559
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDE et outils de d&#233;veloppement Visual&#160;C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans l'environnement de développement intégré (IDE) Visual Studio, Visual C++ partage plusieurs fenêtres et outils en commun avec d'autres langages. Beaucoup d’entre eux, y compris **l’Explorateur de solutions**, l’éditeur de code et le débogueur, sont documentés dans MSDN Library, sous [Visual Studio IDE](../Topic/Visual%20Studio%20IDE.md). Il arrive souvent qu’une fenêtre ou un outil partagé n’ait pas tout à fait les mêmes fonctionnalités pour C++ et pour les langages .NET ou Javascript. Certaines fenêtres ou certains outils sont disponibles seulement dans Visual Studio Pro ou Visual Studio Enterprise. Cette rubrique présente l'IDE Visual Studio du point de vue de Visual C++ et fournit des liens vers d'autres rubriques relatives à Visual C++.  
  
 En plus des outils partagés dans l'IDE Visual Studio, Visual C++ propose plusieurs outils spécifiques pour le développement de code natif. Ces outils sont également répertoriés dans cet article. Pour obtenir la liste des outils disponibles dans chaque édition de Visual Studio, consultez [Visual C++ Tools and Templates in Visual Studio Editions](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md).  
  
## <a name="creating-a-solution-and-projects"></a>Création d'une solution et de projets  
 Dans toutes les éditions de Visual C++, vous organisez le code source et les fichiers associés d'un exécutable (par exemple des fichiers .exe, .dll ou .lib) en un projet. Un projet a un fichier projet au format XML (.vcxproj) qui spécifie tous les fichiers et toutes les ressources nécessaires à la compilation du programme, ainsi que d’autres paramètres de configuration, par exemple la plateforme cible (x86, x64 ou ARM) et si vous générez une version Release ou Debug du programme. Un projet (ou de nombreux projets) sont contenus dans une *solution*. Par exemple, une solution peut contenir plusieurs projets de DLL Win32 et une seule application console Win32 qui utilise ces DLL. Quand vous générez le projet, le moteur MSBuild consomme le fichier projet. En outre, il produit le fichier exécutable et/ou toute autre sortie personnalisée que vous avez spécifiée.  
  
 **Modèles de projet**  
  
 Visual C++ est fourni avec plusieurs modèles de projet, qui contiennent le code de démarrage et les paramètres nécessaires pour différents types de programmes de base. En général, vous commencez par choisir **fichier &#124 ; Nouveau projet** pour créer un projet à partir d’un modèle de projet, puis ajouter de nouveaux fichiers de code source pour ce projet ou commencez à coder dans les fichiers fournis. Pour obtenir des informations spécifiques aux projets C++ et aux Assistants Projet, consultez [Creating and Managing Visual C++ Projects](../ide/creating-and-managing-visual-cpp-projects.md).  
  
 **Assistants Application**  
  
 Visual C++ fournit des Assistants pour certains types de projets. Un Assistant vous guide pas à pas à travers le processus de création d'un projet. Cela s’avère utile pour les types de projet qui ont beaucoup d’options et de paramètres. Pour plus d'informations, consultez [Creating Desktop Projects By Using Application Wizards](../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
## <a name="creating-user-interfaces-with-designers"></a>Création d'interfaces utilisateur avec les concepteurs  
 Si votre programme a une interface utilisateur, une des premières tâches à effectuer est d'y placer des contrôles, comme des boutons, des zones de liste, etc. Visual Studio inclut une aire de conception visuelle et une boîte à outils pour chaque variante des applications C++. Quel que soit le type d'application que vous créez, l'idée de base est la même : vous faites glisser un contrôle depuis la fenêtre Boîte à outils et vous le déposez sur l'aire de conception à l'emplacement souhaité. En arrière-plan, Visual Studio génère les ressources et le code requis pour que tout fonctionne.  
  
 Pour plus d’informations sur la conception d’une interface utilisateur pour une application de plateforme Windows universelle, consultez  [Design et l’interface Utilisateur](https://developer.microsoft.com/en-us/windows/design).  
  
 Pour plus d’informations sur la création d’une interface utilisateur pour une application MFC, consultez [MFC Desktop Applications](../mfc/mfc-desktop-applications.md). Pour plus d’informations sur les programmes de Windows Win32, consultez [Applications de bureau Windows](../windows/windows-desktop-applications-cpp.md).  
  
 Pour plus d'informations sur les applications Windows Forms avec C++/CLI, consultez [Création d'une application Windows Forms à l'aide du .NET Framework (C++)](http://msdn.microsoft.com/fr-fr/8e007885-6c8b-4fb2-a41d-91febd114a9b).  
  
## <a name="writing-and-editing-code"></a>Écriture et modification du code  
 **Colorisation sémantique**  
  
 Une fois un projet créé, tous les fichiers du projet sont affichés dans la fenêtre Explorateur de solutions. Quand vous cliquez sur un fichier .h ou .cpp dans l'Explorateur de solutions, le fichier s'ouvre dans l'éditeur de code. L'éditeur de code est un traitement de texte spécialisé pour le code source C++. Il colore selon une certaine codification les mots clés du langage, les noms des méthodes et des variables, ainsi que les autres éléments de votre code pour rendre le code plus lisible et plus facile à comprendre.  
  
 **IntelliSense**  
  
 L'éditeur de code prend également en charge plusieurs fonctionnalités réunies sous le nom d'Intellisense. Vous pouvez placer le pointeur sur une méthode et voir une documentation de base pour celui-ci. Après avoir tapé un nom de variable de classe et un « . » ou « -> », une liste des membres de l'instance de cette classe s'affiche. Si vous tapez un nom de classe, puis « :: », une liste des membres statiques s'affiche. Quand vous commencez à taper un nom de classe ou de méthode, l'éditeur de code affiche des suggestions pour compléter l'instruction. Pour plus d'informations, consultez [Using IntelliSense](../Topic/Using%20IntelliSense.md).  
  
 **Extraits de code**  
  
 Vous pouvez utiliser des extraits de code Intellisense pour générer des constructions de code fréquemment utilisées ou compliquées avec un raccourci clavier. Pour plus d'informations, consultez [Code Snippets](../Topic/Code%20Snippets.md).  
  
## <a name="navigating-code"></a>Navigation dans le code  
 Le menu Affichage permet d'accéder à de nombreuses fenêtres et de nombreux outils pour naviguer dans vos fichiers de code. Pour obtenir des informations détaillées sur ces fenêtres, consultez [Viewing the Structure of Code](../Topic/Viewing%20the%20Structure%20of%20Code.md).  
  
 **Explorateur de solutions**  
  
 Dans toutes les éditions de Visual Studio, utilisez le volet Explorateur de solutions pour naviguer entre les fichiers d'un projet. Développez une icône de fichier .h ou .cpp pour afficher les classes du fichier. Développez une classe pour voir ses membres. Double-cliquez sur un membre pour accéder à sa définition ou à son implémentation dans le fichier.  
  
 **Affichage de classes et la fenêtre Définition de Code**  
  
 Utilisez le volet Affichage de classes pour voir les espaces de noms et les classes à travers tous les fichiers, y compris les classes partielles. Vous pouvez développer chaque espace de noms ou chaque classe pour voir ses membres et double-cliquer sur le membre pour accéder à cet emplacement dans le fichier source. Si vous ouvrez la fenêtre Définition de Code, vous pouvez voir la définition ou l'implémentation du type quand vous le choisissez dans Affichage de classes.  
  
 **Explorateur d’objets**  
  
 Utilisez l'Explorateur d'objets pour explorer les informations sur les types dans les composants Windows Runtime (fichiers .winmd), les assemblys .NET et les bibliothèques de types COM. Il n'est pas utilisé avec les DLL Win32.  
  
 **Atteindre la définition/déclaration**  
  
 Appuyez sur F12 sur un nom d'API ou une variable d'un membre pour accéder à sa définition. Si la définition se trouve dans un fichier .winmd (pour une application du [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] ), les informations sur le type s'affichent dans l'Explorateur d'objets. Vous pouvez également accéder à la définition ou à la déclaration en cliquant avec le bouton droit sur le nom ou le type d'une variable, puis en choisissant l'option dans le menu contextuel.  
  
 **Rechercher toutes les références**  
  
 Dans un fichier de code source, cliquez avec le bouton droit sur le nom d'un type, d'une méthode ou d'une variable, puis choisissez Rechercher toutes les références pour obtenir une liste de tous les emplacements dans le fichier, le projet ou la solution où le type est utilisé. Rechercher toutes les références fonctionne de façon intelligente et retourne seulement les instances d'une même variable, même si d'autres variables ont le même nom dans d'autres portées.  
  
 **L’architecture et des graphiques de dépendance (Édition intégrale)**  
  
 Utilisez le Navigateur de l'architecture pour voir les relations entre les différents éléments de votre code. Pour plus d’informations, consultez [Rechercher du code avec le navigateur de l’architecture](http://msdn.microsoft.com/fr-fr/b1707926-ef73-47f9-92cd-e00d0fac7e76). Utiliser les graphiques de dépendance pour voir les relations de dépendance. Pour plus d'informations, consultez [How to: Generate Dependency Graphs for C and C++ Code](http://msdn.microsoft.com/fr-fr/3bd5cf9f-62f6-41d0-9f35-d4b2637cba3c).  
  
## <a name="adding-and-editing-resources"></a>Ajout et modification de ressources  
 Le terme « ressource » dans le contexte d'un projet de bureau Visual Studio correspond à des éléments comme des boîtes de dialogue, des icônes, des chaînes localisables, des écrans de démarrage, des chaînes de connexion de base de données ou des données arbitraires que vous voulez inclure dans le fichier exécutable.  
  
 Pour plus d’informations sur l’ajout et la modification de ressources dans les projets de bureau C++ natif, consultez [Working with Resource Files](../mfc/working-with-resource-files.md).  
  
## <a name="building-compiling-and-linking"></a>Génération (compilation et liaison)  
 Appuyez sur **Ctrl+Maj+B** pour compiler et lier un projet. Visual Studio utilise [MSBuild](MSBuild1.md) pour créer du code exécutable. Vous pouvez définir les options générales de build sous **Outils &#124 ; Options de &#124 ; Projets et Solutions** et vous pouvez définir des propriétés pour des projets spécifiques sous **projet &#124 ; Propriétés**. Erreurs de génération et des avertissements sont signalées dans la liste d’erreurs (**Ctrl +\\, E**). Des informations supplémentaires sont parfois affichées dans la fenêtre Sortie (**Alt+2**). Pour plus d’informations, consultez la page  [utilisation des propriétés de projet](../ide/working-with-project-properties.md) et [génération de projets C++ dans Visual Studio](../ide/building-cpp-projects-in-visual-studio.md).  
  
 Vous pouvez également utiliser le compilateur Visual C++ (cl.exe) et de nombreux autres outils autonomes liés à la génération, comme NMAKE et LIB, directement à partir de la ligne de commande. Pour plus d’informations, consultez [Building on the Command Line](../build/building-on-the-command-line.md) et [C/C++ Building Reference](../build/reference/c-cpp-building-reference.md).  
  
## <a name="testing"></a>Test  
 Visual Studio inclut une infrastructure de tests unitaires pour le code C++ natif et pour C++/CLI. Pour plus d'informations, consultez [Vérification du code à l'aide de tests unitaires](../Topic/Unit%20Test%20Your%20Code.md) et [Écriture de tests unitaires pour C/C++ avec l'infrastructure de tests unitaires Microsoft pour C++](../Topic/Writing%20Unit%20tests%20for%20C-C++%20with%20the%20Microsoft%20Unit%20Testing%20Framework%20for%20C++.md)  
  
## <a name="debugging"></a>Débogage  
 Vous pouvez déboguer votre programme en appuyant sur F5 quand votre projet est défini sur Debug. Lors du débogage, vous pouvez définir des points d'arrêt en appuyant sur F9, parcourir le code pas à pas en appuyant sur F10, afficher les valeurs de variables ou de registres spécifiés, et même dans certains cas apporter des modifications dans le code et continuer le débogage sans recompiler. Pour plus d'informations, consultez [Debugging in Visual Studio](../Topic/Debugging%20in%20Visual%20Studio.md).  
  
## <a name="deploying-completed-applications"></a>Déploiement des applications terminées  
 Vous déployez un [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] pour les clients via le Windows Store via la **PROJET &#124 ; Magasin** option de menu. Le déploiement de la bibliothèque CRT est géré automatiquement en arrière-plan. Pour plus d’informations, consultez [Vente d’applications](http://go.microsoft.com/fwlink/p/?LinkId=262280).  
  
 Quand vous déployez une application de bureau C++ native sur un autre ordinateur, vous devez installer l'application elle-même et tous les fichiers bibliothèques dont elle dépend. Il existe trois façons de déployer le runtime Visual C++ avec une application : le déploiement central, le déploiement local ou la liaison statique. Pour plus d’informations, consultez [déploiement des Applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md).  
  
 Pour plus d’informations sur le déploiement d’un C + c++ / programme CLI, consultez la rubrique [Guide de déploiement pour les développeurs](../Topic/.NET%20Framework%20Deployment%20Guide%20for%20Developers.md),  
  
## <a name="other-tools"></a>Autres outils  
  
## <a name="related-articles"></a>Articles connexes  
  
|||  
|-|-|  
|[Outils Visual C++ et des modèles dans les éditions de Visual Studio](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md)|Affiche toutes les fonctionnalités disponibles dans les différentes éditions de Visual Studio.|  
|[Visite guidée de Visual C++](http://msdn.microsoft.com/fr-fr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)|Fournit une vue d'ensemble de l'environnement de développement Visual Studio et des types d'applications C++ que vous pouvez créer.|  
|[Création et gestion de projets Visual C++](../ide/creating-and-managing-visual-cpp-projects.md)|Fournit une vue d'ensemble des projets C++ dans Visual Studio et des liens vers d'autres articles qui expliquent comment les créer et les gérer.|  
|[Génération de programmes C/C++](../build/building-c-cpp-programs.md)|Décrit comment générer des projets C++.|  
|[Déploiement d’Applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)|Fournit une vue d'ensemble du déploiement pour les applications C++ et des liens vers d'autres articles qui décrivent le déploiement en détail.|  
|[Portage et mise à niveau de programmes](http://msdn.microsoft.com/fr-fr/c36c44b3-5a9b-4bb4-9b7a-469aa770ed00)|Liens vers des articles qui décrivent comment ouvrir des applications C++ qui ont été créées dans des versions antérieures de Visual Studio et comment ouvrir des applications qui ont été créées avec des outils autres que Visual Studio.|  
|||  
|[Visual C++](../top/visual-cpp-in-visual-studio-2015.md)|Décrit les principales fonctionnalités de Visual C++ dans Visual Studio et fournit un lien vers le reste de la documentation Visual C++.|