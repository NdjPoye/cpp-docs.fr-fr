---
title: "IDE et les outils de développement Visual C++ | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Visual C++, development tools
ms.assetid: 56eabafb-1956-4f0f-bec5-29b887763559
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e503c3ecbf0cd7245aadeb231030a91577e1e865
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ide-and-tools-for-visual-c-development"></a>IDE et outils de développement Visual C++
Dans l'environnement de développement intégré (IDE) Visual Studio, Visual C++ partage plusieurs fenêtres et outils en commun avec d'autres langages. Beaucoup d'entre eux, y compris **l’Explorateur de solutions**, l’éditeur de Code et le débogueur, sont décrits dans [IDE de Visual Studio](/visualstudio/ide/visual-studio-ide). Il arrive souvent qu’une fenêtre ou un outil partagé n’ait pas tout à fait les mêmes fonctionnalités pour C++ et pour les langages .NET ou Javascript. Certaines fenêtres ou certains outils sont disponibles seulement dans Visual Studio Pro ou Visual Studio Enterprise.   
  
 En plus des outils partagés dans l'IDE Visual Studio, Visual C++ propose plusieurs outils spécifiques pour le développement de code natif. Ces outils sont également répertoriés dans cet article. Pour obtenir la liste des outils sont disponibles dans chaque édition de Visual Studio, consultez [outils Visual C++ et des fonctionnalités dans les éditions Visual Studio](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md).  
## <a name="creating-a-solution-and-projects"></a>Création d'une solution et de projets  

Un « projet » est en fait un ensemble de fichiers de code source et de ressources, telles que des images ou des fichiers de données qui sont intégrées dans un fichier exécutable. Visual Studio 2017 peut prendre en charge n’importe quel système de génération ou les outils de génération personnalisée que vous souhaitez utiliser, avec prise en charge complète d’Intellisense, parcourir et de débogage :
 - MSBuild est le système de génération « natifs » pour Visual Studio et est souvent le meilleur choix pour les applications UWP ou héritées applications de bureau Windows qui utilisent MFC ou ATL. Pour plus d’informations sur les projets C++ basées sur MSBuild, consultez [création et gestion des projets MSBuild](creating-and-managing-visual-cpp-projects.md).
 - CMake est un inter-plateformes générer système qui est intégré dans l’IDE de Visual Studio lorsque vous installez la charge de travail de bureau C++. Pour plus d’informations, consultez [CMake projects in Visual C++](cmake-tools-for-visual-cpp.md).
 - N’importe quel autre C++ système de génération, y compris un ensemble de fichiers, est pris en charge via la fonctionnalité Ouvrir le dossier. Vous créez des fichiers JSON simples pour appeler le programme de génération et de configurer des sessions de débogage. Pour plus d’informations, consultez [mettre votre code C++ vers Visual Studio](https://blogs.msdn.microsoft.com/vcblog/2017/04/14/bring-your-cpp-code-to-visual-studio/).
 
 
 **Modèles de projet (MSBuild)**  
  
 Visual C++ est fourni avec plusieurs modèles de projet MSBuild ; Ces modèles contiennent le code de démarrage et les paramètres nécessaires pour différents types de programmes de base de. En général, vous commencez par choisir **fichier &#124; Nouveau projet** pour créer un projet à partir d’un modèle de projet, puis ajouter de nouveaux fichiers de code source à ce projet et commencez le codage dans les fichiers fournis. Pour plus d’informations spécifiques aux projets C++ et des Assistants de projet, consultez [création et gestion de projets Visual C++](../ide/creating-and-managing-visual-cpp-projects.md).  
  
 **Assistants Application (MSBuild)**  
  
 Visual C++ fournit des Assistants pour certains types de projet MSBuild quand vous choisissez **fichier &#124; Nouveau projet**. Un Assistant vous guide pas à pas à travers le processus de création d'un projet. Cela s’avère utile pour les types de projet qui ont beaucoup d’options et de paramètres. Pour plus d’informations, consultez [création bureau projets par à l’aide d’Assistants Application](../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
## <a name="creating-user-interfaces-with-designers-msbuild"></a>Création d’interfaces utilisateur avec les concepteurs (MSBuild) 
 Si votre programme a une interface utilisateur, une des premières tâches à effectuer est d’y placer des contrôles, comme des boutons, des zones de liste, etc. Visual Studio inclut une aire de conception visuelle et une boîte à outils pour chaque variante des applications C++. Quel que soit le type d'application que vous créez, l'idée de base est la même : vous faites glisser un contrôle depuis la fenêtre Boîte à outils et vous le déposez sur l'aire de conception à l'emplacement souhaité. En arrière-plan, Visual Studio génère les ressources et le code requis pour que tout fonctionne. Puis vous écrivez le code pour remplir les contrôles avec des données ou de personnaliser leur apparence et leur comportement.
  
 Pour plus d’informations sur la conception d’une interface utilisateur pour une application de plateforme Windows universelle, consultez [conception et l’interface utilisateur](https://developer.microsoft.com/en-us/windows/design).  
  
 Pour plus d’informations sur la création d’une interface utilisateur pour une application MFC, consultez [Applications de bureau MFC](../mfc/mfc-desktop-applications.md). Pour plus d’informations sur les programmes Windows Win32, consultez [Applications de bureau Windows](../windows/windows-desktop-applications-cpp.md).  
  
 Pour plus d’informations sur les applications Windows Forms avec c++ / CLI, consultez [création d’une Application Windows Forms à l’aide du .NET Framework (C++)](http://msdn.microsoft.com/en-us/8e007885-6c8b-4fb2-a41d-91febd114a9b).  
  
## <a name="writing-and-editing-code"></a>Écriture et modification du code  
 **Colorisation sémantique**  
  
 Après avoir créé un projet, tous les fichiers projet sont affichés dans le **l’Explorateur de solutions** fenêtre. Lorsque vous cliquez sur un fichier .h ou .cpp dans **l’Explorateur de solutions**, le fichier s’ouvre dans l’éditeur de code. L'éditeur de code est un traitement de texte spécialisé pour le code source C++. Il colore selon une certaine codification les mots clés du langage, les noms des méthodes et des variables, ainsi que les autres éléments de votre code pour rendre le code plus lisible et plus facile à comprendre.  
  
 **IntelliSense**  
  
 L'éditeur de code prend également en charge plusieurs fonctionnalités réunies sous le nom d'Intellisense. Vous pouvez placer le pointeur sur une méthode et voir une documentation de base pour celui-ci. Après avoir tapé un nom de variable de classe et un « . » ou « -> », une liste des membres de l'instance de cette classe s'affiche. Si vous tapez un nom de classe, puis « :: », une liste des membres statiques s'affiche. Quand vous commencez à taper un nom de classe ou de méthode, l'éditeur de code affiche des suggestions pour compléter l'instruction. Pour plus d’informations, consultez [Utilisation d’IntelliSense](/visualstudio/ide/using-intellisense).  
  
 **Extraits de code**  
  
 Vous pouvez utiliser des extraits de code Intellisense pour générer des constructions de code fréquemment utilisées ou compliquées avec un raccourci clavier. Pour plus d’informations, consultez [Extraits de code](/visualstudio/ide/code-snippets).  
  
## <a name="navigating-code"></a>Navigation dans le code  
 Le **vue** menu permet d’accéder à plusieurs fenêtres et outils pour naviguer dans vos fichiers de code. Pour plus d’informations sur ces fenêtres, consultez [affichage de la Structure du Code](/visualstudio/ide/viewing-the-structure-of-code).  
  
 **Explorateur de solutions**  
  
 Dans toutes les éditions de Visual Studio, utilisez le volet Explorateur de solutions pour naviguer entre les fichiers d'un projet. Développez une icône de fichier .h ou .cpp pour afficher les classes du fichier. Développez une classe pour voir ses membres. Double-cliquez sur un membre pour accéder à sa définition ou à son implémentation dans le fichier.  
  
 **Affichage de classes et fenêtre Définition de Code**  
  
 Utilisez le **affichage de classes** volet pour afficher les espaces de noms et les classes dans tous les fichiers, y compris les classes partielles. Vous pouvez développer chaque espace de noms ou chaque classe pour voir ses membres et double-cliquer sur le membre pour accéder à cet emplacement dans le fichier source. Si vous ouvrez la fenêtre Définition de Code, vous pouvez voir la définition ou l'implémentation du type quand vous le choisissez dans Affichage de classes.  
  
 **Explorateur d’objets**  
  
 Utilisez **Explorateur d’objets** pour Explorer les informations de type dans les composants Windows Runtime (fichiers .winmd), les assemblys .NET et COM de bibliothèques de types. Il n'est pas utilisé avec les DLL Win32.  
  
 **Atteindre la définition/déclaration**  
  
 Appuyez sur F12 sur un nom d'API ou une variable d'un membre pour accéder à sa définition. Si la définition se trouve dans un fichier .winmd (pour une application du [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]), les informations sur le type s'affichent dans l'Explorateur d'objets. Vous pouvez également choisir **atteindre la définition** ou **atteindre la déclaration** en cliquant sur le nom de variable ou de type et en choisissant l’option dans le menu contextuel.  
  
 **Rechercher toutes les références**  
  
 Dans un fichier de code source, le bouton droit de la souris sur le nom d’un type ou la méthode ou la variable, puis choisissez **rechercher toutes les références** pour retourner une liste de tous les emplacements dans le fichier, le projet ou la solution où le type est utilisé. **Rechercher toutes les références** fonctionne de façon intelligente et retourne uniquement les instances de la même variable, même si d’autres variables dans d’autres portées ont le même nom.  
  
 **L’architecture et graphiques de dépendance (Ultimate)**  
  
 Utilisez **de l’Architecture** pour afficher les relations entre les différents éléments dans votre code. Pour plus d’informations, consultez [rechercher du code avec l’Architecture](http://msdn.microsoft.com/en-us/b1707926-ef73-47f9-92cd-e00d0fac7e76). Utiliser des graphiques de dépendance pour afficher les relations de dépendance. Pour plus d’informations, consultez [Comment : générer des graphiques de dépendance pour le Code C et C++](http://msdn.microsoft.com/en-us/3bd5cf9f-62f6-41d0-9f35-d4b2637cba3c).  
  
## <a name="adding-and-editing-resources--msbuild"></a>Ajout et modification de ressources (MSBuild)
 Le terme « ressource » dans le contexte d'un projet de bureau Visual Studio correspond à des éléments comme des boîtes de dialogue, des icônes, des chaînes localisables, des écrans de démarrage, des chaînes de connexion de base de données ou des données arbitraires que vous voulez inclure dans le fichier exécutable.  
  
 Pour plus d’informations sur l’ajout et modification de ressources dans les projets de bureau C++ natifs, consultez [utilisation des fichiers de ressources](../windows/working-with-resource-files.md).  
  
## <a name="building-compiling-and-linking"></a>Génération (compilation et liaison)  
 Appuyez sur **Ctrl+Maj+B** pour compiler et lier un projet. Pour créer du code exécutable, Visual Studio utilise [MSBuild](/visualstudio/msbuild/msbuild1) ou CMake ou l’environnement de génération tout ce qui permet de paramétrer **ouvrir le dossier**. Pour les projets de MSBuild, vous définissez des options générales de build sous **Tools &#124; Options &#124; Projets et Solutions** et vous pouvez définir des propriétés pour des projets spécifiques sous **projet &#124; Propriétés**. Erreurs de build et les avertissements sont signalés dans la liste d’erreurs (**Ctrl +\\, E**). Projets non-MSBuild sont configurés avec les fichiers JSON que vous créez dans l’Explorateur de solutions. Quelle que soit système vous utilisez, la fenêtre de sortie de génération (**Alt + 2**) affiche des informations sur le processus de génération. Pour plus d’informations sur les configurations de MSBuild, consultez [utilisation des propriétés de projet](../ide/working-with-project-properties.md) et [génération de projets C++ dans Visual Studio](../ide/building-cpp-projects-in-visual-studio.md).  
  
 Vous pouvez également utiliser le compilateur Visual C++ (cl.exe) et de nombreux autres outils autonomes liés à la génération, comme NMAKE et LIB, directement à partir de la ligne de commande. Pour plus d’informations, consultez [code de génération C/C++ sur la ligne de commande](../build/building-on-the-command-line.md) et [référence à la génération C/C++](../build/reference/c-cpp-building-reference.md).  
  
## <a name="testing"></a>Test  
 Visual Studio inclut une infrastructure de tests unitaires pour le code C++ natif et pour C++/CLI. Pour plus d’informations, consultez [vérification du Code à l’aide de Tests unitaires](/visualstudio/test/unit-test-your-code) et [écriture de tests unitaires pour C/C++ avec l’infrastructure de tests unitaires Microsoft pour C++](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)  
  
## <a name="debugging"></a>Débogage  
 Vous pouvez déboguer votre programme en appuyant sur **F5** lorsque la configuration de votre projet est définie sur Debug. Pendant le débogage, vous pouvez définir des points d’arrêt en appuyant sur **F9**, parcourir le code en appuyant sur **F10**, afficher les valeurs des variables spécifiées ou les registres et même dans certains cas apporter des modifications dans le code et continuer débogage sans recompiler. Pour plus d’informations, consultez [Débogage dans Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).  
  
## <a name="deploying-completed-applications"></a>Déploiement des applications terminées  
 Vous déployez un [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] pour les clients via le Windows Store via le **projet &#124; Magasin** option de menu. Le déploiement de la bibliothèque CRT est géré automatiquement en arrière-plan. Pour plus d’informations, consultez [Vente d’applications](http://go.microsoft.com/fwlink/p/?LinkId=262280).  
  
 Quand vous déployez une application de bureau C++ native sur un autre ordinateur, vous devez installer l'application elle-même et tous les fichiers bibliothèques dont elle dépend. Il existe trois façons de déployer le runtime Visual C++ avec une application : le déploiement central, le déploiement local ou la liaison statique. Pour plus d’informations, consultez [déploiement des Applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md).  
  
 Pour plus d’informations sur le déploiement d’un c++ / programme de l’interface CLI, consultez [Guide de déploiement pour les développeurs](/dotnet/framework/deployment/deployment-guide-for-developers),  

## <a name="related-articles"></a>Articles connexes  
  
|||  
|-|-|  
|[Outils et fonctionnalités Visual C++ dans les éditions de Visual Studio](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)|Affiche toutes les fonctionnalités disponibles dans les différentes éditions de Visual Studio.|  
|[Création et gestion des projets MSBuild](../ide/creating-and-managing-visual-cpp-projects.md)|Fournit une vue d’ensemble des projets MSBuild de C++ dans Visual Studio et des liens vers d’autres articles qui expliquent comment créer et les gérer.|  
|[CMake des projets dans Visual C++](cmake-tools-for-visual-cpp.md).|Décrit comment générer CMake ou autres projets non MSBuild dans Visual C++.|
|[Génération de programmes C/C++](../build/building-c-cpp-programs.md)|Décrit comment générer des projets C++.|  
|[Déploiement d’Applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)|Fournit une vue d'ensemble du déploiement pour les applications C++ et des liens vers d'autres articles qui décrivent le déploiement en détail.|  
|[Guide du portage et de la mise à niveau de Visual C++](../porting/visual-cpp-porting-and-upgrading-guide.md)|Obtenir des informations détaillées sur la mise à niveau des applications C++ qui ont été créées dans les versions antérieures de Visual Studio et également comment migrer les applications qui ont été créées à l’aide des outils autres que Visual Studio.|  
|[Visual C++](../top/visual-cpp-in-visual-studio.md)|Décrit les principales fonctionnalités de Visual C++ dans Visual Studio et fournit un lien vers le reste de la documentation Visual C++.|
