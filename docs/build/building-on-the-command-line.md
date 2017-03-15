---
title: "G&#233;n&#233;ration &#224; partir de la ligne de commande | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "générations (C++), ligne de commande"
  - "ligne de commande (C++), générer à partir de"
  - "ligne de commande (C++), compilateurs"
  - "générations à partir de la ligne de commande (C++)"
  - "compiler le code source (C++), ligne de commande"
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# G&#233;n&#233;ration &#224; partir de la ligne de commande
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez générer des applications C et C\+\+ sur la ligne de commande en utilisant les outils inclus dans [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  Chaque édition de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] installe un ensemble d'outils en ligne de commande comprenant un compilateur, un éditeur de liens et d'autres outils de génération, ainsi qu'un fichier de commandes qui définit l'environnement de build requis.  Par défaut, ces outils sont installés dans *lecteur*:\\Program Files \(x86\)\\Microsoft Visual Studio *version*\\VC\\bin\\.  \(Le répertoire réel sur votre ordinateur dépend du système, de la version de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] et de vos choix d'installation.\)  
  
 Pour fonctionner correctement, les outils en ligne de commande [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] requièrent plusieurs variables d'environnement personnalisées pour votre installation.  Quand [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] est installé, il crée un fichier de commandes vcvarsall.bat que vous pouvez exécuter pour définir les variables d'environnement requises.  Il crée également un raccourci permettant d'ouvrir une fenêtre d'invite de commandes développeur dans laquelle ces variables sont déjà définies.  Ces variables d'environnement sont spécifiques à votre installation et sont susceptibles d'être modifiées par des mises à niveau ou des mises à jour du produit.  Par conséquent, nous vous recommandons d'utiliser vcvarsall.bat ou un raccourci vers la fenêtre d'invite de commandes développeur au lieu de les définir vous\-même.  Pour plus d'informations, voir [Définition du chemin d'accès et des variables d'environnement pour la génération à partir de la ligne de commande](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
### Pour ouvrir une fenêtre d'invite de commandes développeur  
  
1.  Dans l'écran d'accueil de Windows 8, entrez Visual Studio Tools.  Notez que les résultats de la recherche changent à mesure que vous tapez ; lorsque **Visual Studio Tools** apparaît, choisissez cette option.  
  
     Dans les versions antérieures de Windows, choisissez **Démarrer** et entrez Visual Studio Tools dans la zone de recherche.  Lorsque **Visual Studio Tools** apparaît dans les résultats de la recherche, choisissez cette option.  
  
2.  Dans le dossier **Visual Studio Tools**, ouvrez **Invite de commandes développeur** pour votre version de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
 Pour générer un projet C\/C\+\+ sur la ligne de commande, vous pouvez utiliser les outils en ligne de commande [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] suivants :  
  
 [CL](../build/reference/compiling-a-c-cpp-program.md)  
 Utilisez le compilateur \(cl.exe\) pour compiler et lier les fichiers de code source dans les applications, les bibliothèques et les DLL.  
  
 [Link](../build/reference/linking.md)  
 Utilisez l'éditeur de liens \(link.exe\) pour lier les bibliothèques et les fichiers objets compilés dans les applications et les DLL.  
  
 [MSBuild \(Visual C\+\+\)](../build/msbuild-visual-cpp.md)  
 Utilisez MSBuild \(msbuild.exe\) pour générer des projets [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] et des solutions [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  Cela équivaut à exécuter la commande **Générer un projet** ou **Générer la solution** dans l'environnement IDE de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
 [DEVENV](../Topic/Devenv%20Command%20Line%20Switches.md)  
 Utilisez DEVENV \(devenv.exe\) en association avec un commutateur de ligne de commande \(par exemple, **\/Build** ou **\/Clean**\) pour exécuter certaines commandes de génération sans afficher l'environnement IDE de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
 [NMAKE](../build/nmake-reference.md)  
 Utilisez NMAKE \(nmake.exe\) pour automatiser les tâches qui génèrent des projets [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] en utilisant un fichier makefile traditionnel.  
  
 Quand vous générez sur la ligne de commande, vous pouvez obtenir des informations sur des avertissements, des erreurs et des messages en lançant [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], puis en choisissant, dans la barre de menus, **Aide** et **Rechercher**.  
  
## Dans cette section  
 Les articles répertoriés dans cette section de la documentation montrent comment générer des applications sur la ligne de commande. Ils expliquent aussi comment personnaliser l'environnement de build en ligne de commande pour utiliser les ensembles d'outils 64 bits et cibler les plateformes x86, x64 et ARM. Enfin, ils illustrent l'utilisation des outils de génération en ligne de commande MSBuild et NMAKE.  
  
 [Procédure pas à pas : compilation d'un programme C\+\+ natif sur la ligne de commande](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)  
 Fournit un exemple illustrant la création et la compilation un programme C\+\+ simple sur la ligne de commande.  
  
 [Procédure pas à pas : compilation d'un programme C sur la ligne de commande](../Topic/Walkthrough:%20Compiling%20a%20C%20Program%20on%20the%20Command%20Line.md)  
 Décrit comment compiler un programme écrit dans le langage de programmation C.  
  
 [Procédure pas à pas : compilation d'un programme C\+\+\/CLI sur la ligne de commande](../build/walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)  
 Décrit comment créer et compiler un programme C\+\+\/CLI qui utilise le .NET Framework.  
  
 [Procédure pas à pas : compilation d'un programme C\+\+\/CX sur la ligne de commande](../build/walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)  
 Décrit comment créer et compiler un programme C\+\+\/CX qui utilise le Windows Runtime.  
  
 [Définition du chemin d'accès et des variables d'environnement pour les générations sur la ligne de commande](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)  
 Décrit comment ouvrir une fenêtre d'invite de commandes avec les variables d'environnement requises définies pour des générations sur la ligne de commande ciblant les plateformes x86, x64 et ARM, à l'aide d'un ensemble d'outils 32 bits ou 64 bits.  
  
 [Référence NMAKE](../build/nmake-reference.md)  
 Fournit des liens vers des articles qui décrivent l'utilitaire Microsoft Program Maintenance Utility \(NMAKE.EXE\).  
  
 [MSBuild \(Visual C\+\+\)](../build/msbuild-visual-cpp.md)  
 Fournit des liens vers des articles qui expliquent comment utiliser MSBuild.EXE.  
  
## Rubriques connexes  
 [\/MD, \/MT, \/LD \(Utiliser la bibliothèque Runtime\)](../build/reference/md-mt-ld-use-run-time-library.md)  
 Décrit comment utiliser ces options de compilateur pour utiliser une bibliothèque runtime Debug ou Release.  
  
 [Options du compilateur C\/C\+\+](../build/reference/compiler-options.md)  
 Fournit des liens vers des articles qui présentent les options de compilateur C et C\+\+, ainsi que CL.exe.  
  
 [Options de l'éditeur de liens](../build/reference/linker-options.md)  
 Fournit des liens vers des articles qui présentent les options de l'éditeur de liens et LINK.exe.  
  
 [Outils de génération C\/C\+\+](../build/reference/c-cpp-build-tools.md)  
 Fournit des liens vers les outils de génération C\/C\+\+ inclus dans [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
## Voir aussi  
 [Génération de programmes C\/C\+\+](../build/building-c-cpp-programs.md)