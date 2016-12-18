---
title: "Macros pour les propri&#233;t&#233;s et les commandes de g&#233;n&#233;ration | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles"
  - "VC.Project.VCCLCompilerTool.XMLDocumentationFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "$(ConfigurationName) (macro)"
  - "$(DevEnvDir) (macro)"
  - "$(FrameworkDir) (macro)"
  - "$(FrameworkSDKDir) (macro)"
  - "$(FrameworkVersion) (macro)"
  - "$(FxCopDir) (macro)"
  - "$(Inherit) (macro)"
  - "$(InputDir) (macro)"
  - "$(InputExt) (macro)"
  - "$(InputFileName) (macro)"
  - "$(InputName) (macro)"
  - "$(InputPath) (macro)"
  - "$(IntDir) (macro)"
  - "$(NoInherit) (macro)"
  - "$(OutDir) (macro)"
  - "$(ParentName) (macro)"
  - "$(PlatformName) (macro)"
  - "$(ProjectDir) (macro)"
  - "$(ProjectExt) (macro)"
  - "$(ProjectFileName) (macro)"
  - "$(ProjectName) (macro)"
  - "$(ProjectPath) (macro)"
  - "$(References) (macro)"
  - "$(RemoteMachine) (macro)"
  - "$(RootNamespace) (macro)"
  - "$(SafeRootNamespace) (macro)"
  - "$(SolutionDir) (macro)"
  - "$(SolutionExt) (macro)"
  - "$(SolutionFileName) (macro)"
  - "$(SolutionName) (macro)"
  - "$(SolutionPath) (macro)"
  - "$(StopEvaluating) (macro)"
  - "$(TargetDir) (macro)"
  - "$(TargetExt) (macro)"
  - "$(TargetFileName) (macro)"
  - "$(TargetName) (macro)"
  - "$(TargetPath) (macro)"
  - "$(VCInstallDir) (macro)"
  - "$(VSInstallDir) (macro)"
  - "$(WebDeployPath) (macro)"
  - "$(WebDeployRoot) (macro)"
  - "macros de génération (C++)"
  - "générations (C++), macros"
  - "$(ConfigurationName) (macro)"
  - "$(DevEnvDir) (macro)"
  - "$(FrameworkDir) (macro)"
  - "$(FrameworkSDKDir) (macro)"
  - "$(FrameworkVersion) (macro)"
  - "$(FxCopDir) (macro)"
  - "$(Inherit) (macro)"
  - "$(InputDir) (macro)"
  - "$(InputExt) (macro)"
  - "$(InputFileName) (macro)"
  - "$(InputName) (macro)"
  - "$(InputPath) (macro)"
  - "$(IntDir) (macro)"
  - "macros (C++), macros de génération"
  - "$(NoInherit) (macro)"
  - "$(OutDir) (macro)"
  - "$(ParentName) (macro)"
  - "$(PlatformName) (macro)"
  - "$(ProjectDir) (macro)"
  - "$(ProjectExt) (macro)"
  - "$(ProjectFileName) (macro)"
  - "$(ProjectName) (macro)"
  - "$(ProjectPath) (macro)"
  - "propriétés (C++), macros relatives aux propriétés de génération"
  - "$(References) (macro)"
  - "$(RemoteMachine) (macro)"
  - "$(RootNamespace) (macro)"
  - "$(SafeRootNamespace) (macro)"
  - "$(SolutionDir) (macro)"
  - "$(SolutionExt) (macro)"
  - "$(SolutionFileName) (macro)"
  - "$(SolutionName) (macro)"
  - "$(SolutionPath) (macro)"
  - "$(StopEvaluating) (macro)"
  - "$(TargetDir) (macro)"
  - "$(TargetExt) (macro)"
  - "$(TargetFileName) (macro)"
  - "$(TargetName) (macro)"
  - "$(TargetPath) (macro)"
  - "$(VCInstallDir) (macro)"
  - "$(VSInstallDir) (macro)"
  - "$(WebDeployPath) (macro)"
  - "$(WebDeployRoot) (macro)"
ms.assetid: 239bd708-2ea9-4687-b264-043f1febf98b
caps.latest.revision: 22
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Macros pour les propri&#233;t&#233;s et les commandes de g&#233;n&#233;ration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser ces macros partout dans la boîte de dialogue **Pages de propriétés** d’un projet où les chaînes sont acceptées. Ces macros ne respectent pas la casse.  
  
 Pour afficher les macros actuellement disponibles, dans la colonne située à droite d’un nom de propriété, cliquez sur la flèche déroulante vers le bas. Si **Modifier** est disponible, cliquez sur cet élément puis, dans la boîte de dialogue Modifier, cliquez sur **Macros**. Pour plus d’informations, consultez la section **Specifying User\-Defined Values** de [Pages de propriétés](../ide/property-pages-visual-cpp.md).  
  
 Les macros marquées « Déconseillée » ne sont plus utilisées ou ont été remplacées par une [macro de métadonnées d’élément](../Topic/ItemMetadata%20Element%20\(MSBuild\).md) équivalente \(**%\(***nom***\)**\). Les macros marquées « Déconseillée ; migrées » sont également déconseillées. En outre, si le projet contenant la macro est migré depuis Visual Studio 2008, Visual Studio convertit la macro en la macro actuelle équivalente.  
  
|Macro|Description|  
|-----------|-----------------|  
|**$\(RemoteMachine\)**|Définit sur la valeur de la propriété **Remote Machine**  sur la page des propriétés du débogage. Pour plus d’informations, consultez [Modification des paramètres du projet pour une configuration Debug C ou C\+\+](../Topic/Project%20Settings%20for%20a%20C++%20Debug%20Configuration.md).|  
|**$\(Configuration\)**|Le nom de la configuration de projet actuelle \(par exemple « Debug »\).|  
|**$\(Platform\)**|Le nom de la plateforme de projet actuelle \(par exemple « Win32 »\).|  
|**$\(ParentName\)**|\(Déconseillée\). Nom de l’élément contenant cet élément de projet. Il s’agira du nom du dossier parent ou du nom du projet.|  
|**$\(RootNameSpace\)**|L’espace de noms, s’il y en a un, contenant l’application.|  
|**$\(IntDir\)**|Chemin du répertoire spécifié pour les fichiers intermédiaires. S’il s’agit d’un chemin relatif, les fichiers intermédiaires sont placés dans ce chemin ajouté au répertoire du projet. Ce chemin doit se terminer par une barre oblique. Ceci se résout en la valeur de la propriété **Intermediate Directory**. N’utilisez pas **$\(OutDir\)** pour définir cette propriété.|  
|**$\(OutDir\)**|Chemin du répertoire des fichiers de sortie. S’il s’agit d’un chemin relatif, les fichiers de sortie sont placés dans ce chemin ajouté au répertoire du projet. Ce chemin doit se terminer par une barre oblique. Ceci se résout en la valeur de la propriété **Output Directory**. N’utilisez pas **$\(IntDir\)** pour définir cette propriété.|  
|**$\(DevEnvDir\)**|Le répertoire d’installation de Visual Studio \(défini comme étant lecteur \+ chemin\) ; se termine par la barre oblique inverse « \\ ».|  
|**$\(InputDir\)**|\(Déconseillée ; migrée.\) Le répertoire du fichier d’entrée \(défini comme étant lecteur \+ chemin\) ; se termine par la barre oblique inverse « \\ ». Si le projet est l’entrée, cette macro est équivalente à **$\(ProjectDir\)**.|  
|**$\(InputPath\)**|\(Déconseillée ; migrée.\) Le nom du chemin absolu du fichier d’entrée \(défini comme étant lecteur \+ chemin \+ nom de base \+ extension de fichier\). Si le projet est l’entrée, cette macro est équivalente à **$\(ProjectPath\)**.|  
|**$\(InputName\)**|\(Déconseillée ; migrée.\) Nom de base du fichier d’entrée. Si le projet est l’entrée, cette macro est équivalente à **$\(ProjectName\)**.|  
|**$\(InputFileName\)**|\(Déconseillée ; migrée.\) Le nom de fichier du fichier d’entrée \(défini comme étant nom de base \+ extension de fichier\). Si le projet est l’entrée, cette macro est équivalente à **$\(ProjectFileName\)**.|  
|**$\(InputExt\)**|\(Déconseillée ; migrée.\) L’extension de fichier du fichier d’entrée. Elle inclut le point \(« . »\) avant l’extension de fichier. Si le projet est l’entrée, cette macro est équivalente à **$\(ProjectExt\)**.|  
|**$\(ProjectDir\)**|Le répertoire du projet \(défini comme étant lecteur \+ chemin\) ; se termine par la barre oblique inverse « \\ ».|  
|**$\(ProjectPath\)**|Le nom du chemin absolu du projet \(défini comme étant lecteur \+ chemin \+ nom de base \+ extension de fichier\).|  
|**$\(ProjectName\)**|Le nom de base du projet.|  
|**$\(ProjectFileName\)**|Le nom de fichier du projet \(défini comme étant nom de base \+ extension de fichier\).|  
|**$\(ProjectExt\)**|L’extension de fichier du projet. Elle inclut le point \(« . »\) avant l’extension de fichier.|  
|**$\(SolutionDir\)**|Le répertoire de la solution \(défini comme étant lecteur \+ chemin\) ; se termine par la barre oblique inverse « \\ ».|  
|**$\(SolutionPath\)**|Le nom du chemin absolu de la solution \(défini comme étant lecteur \+ chemin \+ nom de base \+ extension de fichier\).|  
|**$\(SolutionName\)**|Le nom de base de la solution.|  
|**$\(SolutionFileName\)**|Le nom de fichier de la solution \(défini comme étant nom de base \+ extension de fichier\).|  
|**$\(SolutionExt\)**|L’extension de fichier de la solution. Elle inclut le point \(« . »\) avant l’extension de fichier.|  
|**$\(TargetDir\)**|Le répertoire du fichier de sortie principal pour la build \(défini comme étant lecteur \+ chemin\) ; se termine par la barre oblique inverse « \\ ».|  
|**$\(TargetPath\)**|Le nom du chemin absolu du fichier de sortie principal pour la build \(défini comme étant lecteur \+ chemin \+ nom de base \+ extension de fichier\).|  
|**$\(TargetName\)**|Le nom de base du fichier de sortie principal pour la build.|  
|**$\(TargetFileName\)**|Le nom de fichier du fichier de sortie principal pour la build \(défini comme étant nom de base \+ extension de fichier\).|  
|**$\(TargetExt\)**|L’extension de fichier du fichier de sortie principal pour la build. Elle inclut le point \(« . »\) avant l’extension de fichier.|  
|**$\(VSInstallDir\)**|Le répertoire où vous avez installé Visual Studio.<br /><br /> Cette propriété contient la version du Visual Studio ciblé, qui peut être différente de celle du Visual Studio hôte. Par exemple, lors d’une génération avec `$(PlatformToolset) = v110`, **$\(VSInstallDir\)** contient le chemin de l’installation de Visual Studio 2012.|  
|**$\(VCInstallDir\)**|Le répertoire où vous avez installé Visual C\+\+.<br /><br /> Cette propriété contient la version du Visual C\+\+ ciblé, qui peut être différente de celle du Visual Studio hôte. Par exemple, lors d’une génération avec `$(PlatformToolset) = v90`, **$\(VCInstallDir\)** contient le chemin de l’installation de Visual C\+\+ 2008.|  
|**$\(FrameworkDir\)**|Le répertoire où le .NET Framework a été installé.|  
|**$\(FrameworkVersion\)**|La version du .NET Framework utilisée par Visual Studio. Combiné avec **$\(FrameworkDir\)**, le chemin complet de la version du .NET Framework utilisé par Visual Studio.|  
|**$\(FrameworkSDKDir\)**|Le répertoire où vous avez installé le .NET Framework. Le .NET Framework peut avoir été installé dans le cadre de Visual Studio ou bien séparément.|  
|**$\(WebDeployPath\)**|Le chemin relatif à partir de la racine du déploiement auquel les sorties du projet appartiennent. Retourne la même valeur que <xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath%2A>.|  
|**$\(WebDeployRoot\)**|Le chemin absolu de l’emplacement de **\<localhost\>**. Par exemple, c:\\inetpub\\wwwroot.|  
|**$\(SafeParentName\)**|\(Déconseillée\). Le nom du parent immédiat dans un format de nom valide. Par exemple, une forme est le parent d’un fichier .resx.|  
|**$\(SafeInputName\)**|\(Déconseillée\). Le nom du fichier sous forme de nom de classe valide, moins l’extension de fichier.|  
|**$\(SafeRootNamespace\)**|\(Déconseillée\). Le nom de l’espace de noms où les Assistants Projet ajouteront le code. Cet espace de noms contiendra seulement des caractères qui sont autorisés dans un identificateur C\+\+ valide.|  
|**$\(FxCopDir\)**|Le chemin du fichier fxcop.cmd. Le fichier fxcop.cmd n’est pas installé avec toutes les éditions de Visual C\+\+.|  
  
## Voir aussi  
 [Génération de projets C\+\+ dans Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)