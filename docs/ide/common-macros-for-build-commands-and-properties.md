---
title: "Macros communs pour les propriétés et les commandes de génération | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
dev_langs: C++
helpviewer_keywords:
- $(FrameworkSDKDir) macro
- ProjectName macro $(ProjectName)
- DevEnvDir macro $(DevEnvDir)
- $(DevEnvDir) macro
- TargetPath macro $(TargetPath)
- VSInstallDir macro $(VSInstallDir)
- $(InputFileName) macro
- $(SolutionFileName) macro
- macros [C++], build macros
- InputFileName macro $(InputFileName)
- $(VCInstallDir) macro
- $(IntDir) macro
- $(ConfigurationName) macro
- SolutionDir macro $(SolutionDir)
- $(TargetPath) macro
- $(Inherit) macro
- $(SolutionPath) macro
- WebDeployRoot macro $(WebDeployRoot)
- WebDeployPath macro $(WebDeployPath)
- StopEvaluating macro $(StopEvaluating)
- $(RootNamespace) macro
- $(WebDeployRoot) macro
- ProjectPath macro $(ProjectPath)
- $(ProjectPath) macro
- $(InputDir) macro
- SolutionName macro $(SolutionName)
- ProjectExt macro $(ProjectExt)
- $(TargetExt) macro
- $(ProjectFileName) macro
- TargetName macro $(TargetName)
- $(References) macro
- References macro $(References)
- TargetExt macro $(TargetExt)
- ProjectDir macro $(ProjectDir)
- $(TargetDir) macro
- SolutionExt macro $(SolutionExt)
- $(SolutionDir) macro
- ProjectFileName macro $(ProjectFileName)
- VCInstallDir macro $(VCInstallDir)
- $(InputExt) macro
- $(TargetFileName) macro
- $(SolutionExt) macro
- PlatformName macro $(PlatformName)
- IntDir macro $(IntDir)
- $(FrameworkVersion) macro
- $(ProjectDir) macro
- build macros [C++]
- InputPath macro $(InputPath)
- $(VSInstallDir) macro
- $(WebDeployPath) macro
- TargetFileName macro $(TargetFileName)
- NoInherit macro $(NoInherit)
- ConfigurationName macro $(ConfigurationName)
- $(ProjectExt) macro
- TargetDir macro $(TargetDir)
- InputName macro $(InputName)
- $(ProjectName) macro
- FrameworkSDKDir macro $(FrameworkSDKDir)
- $(ParentName) macro
- InputExt macro $(InputExt)
- $(SafeRootNamespace) macro
- InputDir macro $(InputDir)
- $(FxCopDir) macro
- $(RemoteMachine) macro
- Inherit macro $(Inherit)
- FrameworkVersion macro $(FrameworkVersion)
- $(StopEvaluating) macro
- $(OutDir) macro
- FrameworkDir macro $(FrameworkDir)
- SolutionFileName macro $(SolutionFileName)
- $(NoInherit) macro
- RemoteMachine macro $(RemoteMachine)
- properties [C++], build property macros
- $(TargetName) macro
- $(SolutionName) macro
- $(InputPath) macro
- ParentName macro $(ParentName)
- OutDir macro $(OutDir)
- SafeRootNamespace macro $(SafeRootNamespace)
- FxCopDir macro $(FxCopDir)
- $(InputName) macro
- RootNamespace macro $(RootNamespace)
- builds [C++], macros
- $(FrameworkDir) macro
- $(PlatformName) macro
- SolutionPath macro $(SolutionPath)
ms.assetid: 239bd708-2ea9-4687-b264-043f1febf98b
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f96e403516d6f85804fa798d7a0c28575482ff43
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="common-macros-for-build-commands-and-properties"></a>Macros communs pour les propriétés et les commandes de génération
En fonction de vos options d’installation, Visual Studio peut mettre des centaines de macros à votre disposition. Ceux-ci correspondent aux propriétés qui sont définies dans vos paramètres de projet par défaut ou dans les fichiers .props ou .targets MSBuild. Vous pouvez utiliser ces macros partout dans la boîte de dialogue **Pages de propriétés** d’un projet où les chaînes sont acceptées. Ces macros ne respectent pas la casse.  
  
 Pour afficher les macros actuellement disponibles, dans la colonne située à droite d’un nom de propriété, cliquez sur la flèche déroulante vers le bas. Si **Modifier** est disponible, cliquez sur cet élément puis, dans la boîte de dialogue Modifier, cliquez sur **Macros**. Pour plus d’informations, consultez la section **Specifying User-Defined Values** de [Pages de propriétés](../ide/property-pages-visual-cpp.md).  
  
 Les macros marquées « Déconseillée » ne sont plus utilisées ou ont été remplacées par une [macro de métadonnées d’élément](/visualstudio/msbuild/itemmetadata-element-msbuild) équivalente (**%(***nom***)**). Les macros marquées « Déconseillée ; migrées » sont également déconseillées. En outre, si le projet contenant la macro est migré depuis Visual Studio 2008, Visual Studio convertit la macro en la macro actuelle équivalente.  
  
 Le tableau suivant décrit un sous-ensemble couramment utilisé des macros disponibles. Cette liste n’est pas exhaustive. Pour plus d’informations sur les définitions de propriété MSBuild sont créées et utilisées en tant que macros dans les fichiers .vcxproj .props et .targets, consultez [propriétés MSBuild](/visualstudio/msbuild/msbuild-properties).  
  
|Macro|Description|  
|-----------|-----------------|  
|**$ (RemoteMachine)**|Définit sur la valeur de la propriété **Remote Machine** sur la page des propriétés du débogage. Pour plus d’informations, consultez [Modification des paramètres du projet pour une configuration Debug C ou C++](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration) .|  
|**$(Configuration)**|Nom de la configuration de projet actuelle, par exemple « Debug ».|  
|**$(Platform)**|Le nom de la plateforme du projet actuel, par exemple, « Win32 ».|  
|**$ (ParentName)**|(Déconseillée). Nom de l’élément contenant cet élément de projet. Il s’agira du nom du dossier parent ou du nom du projet.|  
|**RootNamespace**|L’espace de noms, s’il y en a un, contenant l’application.|  
|**$(IntDir)**|Chemin du répertoire spécifié pour les fichiers intermédiaires. S’il s’agit d’un chemin d’accès relatif, fichiers intermédiaires sont placés dans ce chemin ajouté au répertoire du projet. Ce chemin doit se terminer par une barre oblique. Ceci se résout en la valeur de la propriété **Intermediate Directory** . N’utilisez pas **$(OutDir)** pour définir cette propriété.|  
|**$(OutDir)**|Chemin du répertoire des fichiers de sortie. S’il s’agit d’un chemin relatif, les fichiers de sortie sont placés dans ce chemin ajouté au répertoire du projet. Ce chemin doit se terminer par une barre oblique. Ceci se résout en la valeur de la propriété **Output Directory** . N’utilisez pas **$(IntDir)** pour définir cette propriété.|  
|**Devenvdir**|Le répertoire d’installation de Visual Studio (défini comme étant lecteur + chemin) ; inclut la barre oblique de fin '\\'.|  
|**Inputdir**|(Déconseillée ; migrée.) Le répertoire du fichier d’entrée (défini comme étant lecteur + chemin) ; inclut la barre oblique de fin '\\'. Si le projet est l’entrée, cette macro est équivalente à **$(ProjectDir)**.|  
|**InputPath**|(Déconseillée ; migrée.) Le nom du chemin absolu du fichier d’entrée (défini comme étant lecteur + chemin + nom de base + extension de fichier). Si le projet est l’entrée, cette macro est équivalente à **$(ProjectPath)**.|  
|**$ (InputName)**|(Déconseillée ; migrée.) Nom de base du fichier d’entrée. Si le projet est l’entrée, cette macro est équivalente à **$(ProjectName)**.|  
|**InputFilename**|(Déconseillée ; migrée.) Le nom de fichier du fichier d’entrée (défini comme étant nom de base + extension de fichier). Si le projet est l’entrée, cette macro est équivalente à **$(ProjectFileName)**.|  
|**Inputext**|(Déconseillée ; migrée.) L’extension de fichier du fichier d’entrée. Elle inclut le point (« . ») avant l’extension de fichier. Si le projet est l’entrée, cette macro est équivalente à **$(ProjectExt)**.|  
|**$(ProjectDir)**|Le répertoire du projet (défini comme étant lecteur + chemin) ; inclut la barre oblique de fin '\\'.|  
|**$(ProjectPath)**|Le nom du chemin absolu du projet (défini comme étant lecteur + chemin + nom de base + extension de fichier).|  
|**$(ProjectName)**|Le nom de base du projet.|  
|**$(ProjectFileName)**|Le nom de fichier du projet (défini comme étant nom de base + extension de fichier).|  
|**$(ProjectExt)**|L’extension de fichier du projet. Elle inclut le point (« . ») avant l’extension de fichier.|  
|**$ (SolutionDir)**|Le répertoire de la solution (défini comme étant lecteur + chemin) ; inclut la barre oblique de fin '\\'. Défini uniquement lors de la création d’une solution dans l’IDE.|  
|**Solutionpath**|Le nom du chemin absolu de la solution (défini comme étant lecteur + chemin + nom de base + extension de fichier). Défini uniquement lors de la création d’une solution dans l’IDE.|  
|**Solutionname**|Le nom de base de la solution. Défini uniquement lors de la création d’une solution dans l’IDE.|  
|**Solutionfilename**|Le nom de fichier de la solution (défini comme étant nom de base + extension de fichier). Défini uniquement lors de la création d’une solution dans l’IDE.|  
|**Solutionext**|L’extension de fichier de la solution. Elle inclut le point (« . ») avant l’extension de fichier. Défini uniquement lors de la création d’une solution dans l’IDE.|  
|**Targetdir**|Le répertoire du fichier de sortie principal pour la build (défini comme étant lecteur + chemin) ; inclut la barre oblique de fin '\\'.|  
|**$ (TargetPath)**|Le nom du chemin absolu du fichier de sortie principal pour la build (défini comme étant lecteur + chemin + nom de base + extension de fichier).|  
|**$ (TargetName)**|Le nom de base du fichier de sortie principal pour la build.|  
|**TargetFileName**|Le nom de fichier du fichier de sortie principal pour la build (défini comme étant nom de base + extension de fichier).|  
|**$ (TargetExt)**|L’extension de fichier du fichier de sortie principal pour la build. Elle inclut le point (« . ») avant l’extension de fichier.|  
|**$(VSInstallDir)**|Le répertoire où vous avez installé Visual Studio.<br /><br /> Cette propriété contient la version du Visual Studio ciblé, qui peut être différente de celle du Visual Studio hôte. Par exemple, lors d’une génération avec `$(PlatformToolset) = v110`, **$(VSInstallDir)** contient le chemin de l’installation de Visual Studio 2012.|  
|**$(VCInstallDir)**|Le répertoire où vous avez installé Visual C++.<br /><br /> Cette propriété contient la version du Visual C++ ciblé, qui peut être différente de celle du Visual Studio hôte. Par exemple, lors de la génération avec `$(PlatformToolset) = v140`, **$ (VCInstallDir)** contient le chemin d’accès à l’installation de Visual C++ 2015.|  
|**$(FrameworkDir)**|Le répertoire où le .NET Framework a été installé.|  
|**FrameworkVersion**|La version du .NET Framework utilisée par Visual Studio. Combiné avec **$(FrameworkDir)**, le chemin complet de la version du .NET Framework utilisé par Visual Studio.|  
|**Frameworksdkdir**|Le répertoire où vous avez installé le .NET Framework. Le .NET Framework peut avoir été installé dans le cadre de Visual Studio ou bien séparément.|  
|**WebDeployPath**|Le chemin relatif à partir de la racine du déploiement auquel les sorties du projet appartiennent. Retourne la même valeur que <xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath%2A>.|  
|**WebDeployRoot**|Le chemin d’accès absolu vers l’emplacement de  **\<localhost >**. Par exemple, c:\inetpub\wwwroot.|  
|**$(SafeParentName)**|(Déconseillée). Le nom du parent immédiat dans un format de nom valide. Par exemple, une forme est le parent d’un fichier .resx.|  
|**$(SafeInputName)**|(Déconseillée). Le nom du fichier sous forme de nom de classe valide, moins l’extension de fichier.|  
|**Saferootnamespace**|(Déconseillée). Le nom de l’espace de noms où les Assistants Projet ajouteront le code. Cet espace de noms contiendra seulement des caractères qui sont autorisés dans un identificateur C++ valide.|  
|**FXCOPDIR**|Le chemin du fichier fxcop.cmd. Le fichier fxcop.cmd n’est pas installé avec toutes les éditions de Visual C++.|  
  
## <a name="see-also"></a>Voir aussi  
 [Génération de projets C++ dans Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)