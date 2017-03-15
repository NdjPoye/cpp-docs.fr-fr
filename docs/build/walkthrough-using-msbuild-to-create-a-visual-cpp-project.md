---
title: "Proc&#233;dure pas &#224; pas&#160;: utilisation de MSBuild pour cr&#233;er un projet Visual&#160;C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "msbuild.cpp.walkthrough.createproject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSBuild (C++), créer un projet (procédure pas à pas)"
ms.assetid: 52350d1c-c373-4868-923c-5e8be6f67adb
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: utilisation de MSBuild pour cr&#233;er un projet Visual&#160;C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette procédure pas à pas montre comment utiliser [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] pour générer un projet [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] dans une invite de commandes.  Vous apprendrez comment créer des fichiers sources C\+\+ et un fichier projet basé sur XML pour une application console [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  Après avoir généré le projet, vous apprendrez comment personnaliser le processus de génération.  
  
 Cette procédure pas à pas décrit les tâches suivantes :  
  
-   Création des fichiers sources C\+\+ pour votre projet.  
  
-   Création du fichier projet XML [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)].  
  
-   Utilisation de [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] pour générer votre projet.  
  
-   Utilisation de [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] pour personnaliser votre projet.  
  
## Composants requis  
 Les éléments suivants sont nécessaires pour effectuer cette procédure pas à pas :  
  
-   [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]  
  
-   Connaissances générales du système [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)].  
  
## Création des fichiers sources C\+\+  
 Dans cette procédure pas à pas vous créerez un projet qui comporte un fichier source et un fichier d'en\-tête.  Le fichier source main.cpp contient la fonction principale pour l'application console.  Le fichier d'en\-tête main.h contient le code pour inclure le fichier d'en\-tête iostream.  Vous pouvez créer ces fichiers C\+\+ à l'aide de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] ou d'un éditeur de texte.  
  
#### Pour créer les fichiers sources C\+\+ pour votre projet  
  
1.  Créez un répertoire pour votre projet.  
  
2.  Créez un fichier nommé main.cpp et ajoutez le code suivant à ce fichier :  
  
    ```cpp  
    // main.cpp : the application source code.  
    #include <iostream>  
    #include "main.h"  
    int main()  
    {  
       std::cout << "Hello, from MSBuild!\n";  
       return 0;  
    }  
    ```  
  
3.  Créez un fichier nommé main.h et ajoutez le code suivant à ce fichier :  
  
    ```hlsl  
    // main.h: the application header code.  
    /* Additional source code to include. */  
    ```  
  
## Création du fichier projet XML MSBuild  
 Un fichier projet [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] est un fichier XML qui contient un élément racine du projet \(\<Projet\>\).  Dans l'exemple de projet suivant, l'élément \<Project\> contient sept éléments enfants :  
  
-   Trois balises de groupe d'éléments \(\<ItemGroup\>\) qui spécifient la configuration du projet et de la plateforme, le nom du fichier source et le nom du fichier d'en\-tête.  
  
-   Trois balises d'importation \(\<Import\>\) qui spécifient l'emplacement des paramètres Microsoft [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  
  
-   Une balise de groupe de propriétés \(\<PropertyGroup\>\) qui spécifie les paramètres du projet.  
  
#### Pour créer le fichier projet MSBuild  
  
1.  Utilisez un éditeur de texte pour créer un fichier projet nommé `myproject.vcxproj`, puis ajoutez l'élément racine \<Project\> suivant.  Insérez les éléments dans les étapes suivantes entre les balises \<Project\> racine :  
  
    ```xml  
    <Project DefaultTargets="Build" ToolsVersion="12.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    </Project>  
    ```  
  
2.  Ajoutez les deux éléments \<ProjectConfiguration\> enfants dans un élément \<ItemGroup\>.  L'élément enfant spécifie les configurations Debug et Release pour un système d'exploitation Windows 32 bits :  
  
    ```xml  
    <ItemGroup>  
      <ProjectConfiguration Include="Debug|Win32">  
        <Configuration>Debug</Configuration>  
        <Platform>Win32</Platform>  
      </ProjectConfiguration>  
      <ProjectConfiguration Include="Release|Win32">  
        <Configuration>Release</Configuration>  
        <Platform>Win32</Platform>  
      </ProjectConfiguration>  
    </ItemGroup>  
  
    ```  
  
3.  Ajoutez l'élément \<Import\/\> suivant qui spécifie le chemin d'accès des paramètres C\+\+ par défaut pour ce projet :  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />  
  
    ```  
  
4.  Ajoutez l'élément de groupe de propriétés suivant \(\<PropertyGroup\>\) qui spécifie deux propriétés du projet :  
  
    ```xml  
    <PropertyGroup>  
      <ConfigurationType>Application</ConfigurationType>  
      <PlatformToolset>v120</PlatformToolset>  
    </PropertyGroup>  
    ```  
  
5.  Ajoutez l'élément \<Import\/\> suivant qui spécifie le chemin d'accès des paramètres C\+\+ actuels pour ce projet :  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />  
    ```  
  
6.  Ajoutez l'élément enfant \<ClCompile\> dans un élément \<ItemGroup\>.  L'élément enfant spécifie le nom du fichier source C\/C\+\+ à compiler :  
  
    ```xml  
    <ItemGroup>  
      <ClCompile Include="main.cpp" />  
    </ItemGroup>  
    ```  
  
7.  Ajoutez l'élément enfant \<ClInclude\> dans un élément \<ItemGroup\>.  L'élément enfant spécifie le nom du fichier d'en\-tête pour le fichier source C\/C\+\+ :  
  
    ```xml  
    <ItemGroup>  
      <ClInclude Include="main.h" />  
    </ItemGroup>  
    ```  
  
8.  Ajoutez l'élément \<Import\> suivant qui spécifie le chemin d'accès du fichier qui définit la cible pour ce projet :  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />  
  
    ```  
  
### Fichier projet complet  
 Le code suivant affiche le fichier projet complet que vous avez créé au cours de la procédure précédente.  
  
```xml  
<Project DefaultTargets="Build" ToolsVersion="12.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <ItemGroup>  
    <ProjectConfiguration Include="Debug|Win32">  
      <Configuration>Debug</Configuration>  
      <Platform>Win32</Platform>  
    </ProjectConfiguration>  
    <ProjectConfiguration Include="Release|Win32">  
      <Configuration>Release</Configuration>  
      <Platform>Win32</Platform>  
    </ProjectConfiguration>  
  </ItemGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />  
  <PropertyGroup>  
    <ConfigurationType>Application</ConfigurationType>  
    <PlatformToolset>v120</PlatformToolset>  
  </PropertyGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />  
  <ItemGroup>  
    <ClCompile Include="main.cpp" />  
  </ItemGroup>  
  <ItemGroup>  
    <ClInclude Include="main.h" />  
  </ItemGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />  
</Project>  
```  
  
## Utilisation de MSBuild pour générer votre projet  
 À l'invite de commandes, tapez la commande suivante afin de générer votre application console :  
  
```  
msbuild myproject.vcxproj /p:configuration=debug  
```  
  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] crée un répertoire pour les fichiers de sortie, puis compile et lie votre projet pour générer le programme Myproject.exe.  Après avoir fini le processus de génération, utilisez la commande suivante pour exécuter l'application :  
  
```  
myproject  
```  
  
 L'application doit afficher « Hello, from MSBuild\! » dans la fenêtre de console.  
  
## Personnalisation de votre projet  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]vous permet d'exécuter des cibles de génération prédéfinies, d'appliquer des propriétés définies par l'utilisateur et d'utiliser des outils personnalisés, des événements et des étapes de génération.  Cette section pas à pas décrit les tâches suivantes :  
  
-   Utilisation de [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] avec les cibles de génération.  
  
-   Utilisation de [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] avec les propriétés de génération.  
  
-   Utilisation de [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] avec le compilateur et les outils 64 bits.  
  
-   Utilisation de [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] avec différents ensembles d'outils.  
  
-   Ajout de personnalisations [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)].  
  
### Utilisation de MSBuild avec des cibles de génération  
 Une *cible de génération* est un jeu nommé de commandes prédéfinies ou définies par l'utilisateur qui peuvent être exécutées lors de la génération.  Utilisez l'option de ligne de commande cible \(**\/t**\) pour spécifier une cible de génération.  Dans le cas de l'exemple de projet `myproject`, la cible prédéfinie **clean** supprime tous les fichiers dans le dossier de débogage et crée un nouveau fichier journal.  
  
 À l'invite de commandes, tapez la commande suivante pour nettoyer `myproject`.  
  
 `msbuild myproject.vcxproj /t:clean`  
  
### Utilisation de MSBuild avec les propriétés de génération  
 L'option de ligne de commande de propriété \(**\/p**\) vous permet de substituer une propriété dans votre fichier de génération de projet.  Dans l'exemple de projet `myproject`, la configuration de génération Debug ou Release est spécifiée par la propriété `Configuration` et le système d'exploitation destiné à exécuter l'application générée est spécifié par la propriété `Platform`.  
  
 À l'invite de commandes, tapez la commande suivante pour créer une version Debug de l'application `myproject` destinée à s'exécuter sur un système Windows 32 bits.  
  
 `msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`  
  
 Supposons que l'exemple de projet `myproject` définit également une configuration pour Windows 64 bits, et une autre configuration pour un système d'exploitation personnalisé nommé `myplatform`.  
  
 À l'invite de commandes, tapez la commande suivante pour créer une version Release qui s'exécute sur Windows 64 bits.  
  
 `msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`  
  
 À l'invite de commandes, tapez la commande suivante afin de créer une version Release pour `myplatform`.  
  
 `msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`  
  
### Utilisation de MSBuild avec le compilateur et les outils 64 bits  
 Si vous avez installé [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] sur Windows 64 bits, les outils natifs et croisés x64 64 bits sont installés par défaut.  Vous pouvez configurer [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] et utiliser les outils et le compilateur 64 bits pour générer votre application en définissant la propriété `PreferredToolArchitecture`.  Cette propriété n'affecte pas les propriétés de configuration du projet ou de plateforme.  Par défaut, la version 32 bits des outils est utilisée.  Pour spécifier la version 64 bits du compilateur et des outils, ajoutez l'élément de groupe de propriétés suivant au fichier projet Myproject.vcxproj après l'élément `Microsoft.Cpp.default.props` \<\<Import \/\>\> :  
  
```xml  
<PropertyGroup>  
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>  
</PropertyGroup>  
```  
  
 À l'invite de commandes, tapez la commande suivante pour utiliser les outils 64 bits afin de générer votre application.  
  
 `msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`  
  
### Utilisation de MSBuild avec un ensemble d'outils différent  
 Si les ensembles d'outils et les bibliothèques d'autres versions de [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] sont installés, [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] peut générer des applications pour la version [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] actuelle ou pour les autres versions installées.  Par exemple, si vous avez installé [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)], pour spécifier l'ensemble d'outils [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 11.0 pour Windows XP, ajoutez l'élément de groupe de propriétés suivant au fichier de projet Myproject.vcxproj après l'élément `<Import />` de Microsoft.Cpp.props :  
  
```xml  
<PropertyGroup>  
    <PlatformToolset>v110_xp</PlatformToolset>  
</PropertyGroup>  
```  
  
 Pour régénérer votre projet avec l'ensemble d'outils [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 11.0 Windows XP, tapez l'une ou l'autre des commandes suivantes :  
  
 `msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`  
  
 `msbuild myproject.vcxproj /t:rebuild`  
  
### Ajout de personnalisations MSBuild  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] offre différents moyens pour personnaliser votre processus de génération.  Les rubriques suivantes indiquent comment ajouter des étapes de génération personnalisée, des outils et des événements à votre projet [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] :  
  
-   [Comment : ajouter une étape de génération personnalisée à des projets MSBuild](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)  
  
-   [Comment : ajouter des outils de génération personnalisée à des projets MSBuild](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)  
  
-   [Comment : utiliser des événements de build dans des projets MSBuild](../build/how-to-use-build-events-in-msbuild-projects.md)