---
title: "Vue d&#39;ensemble de MSBuild (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "MSBuild (vue d'ensemble)"
ms.assetid: dd258f6f-ab51-48d9-b274-f7ba911d05ca
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Vue d&#39;ensemble de MSBuild (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MSBuild est la norme de système de génération pour les projets Visual C++. Lorsque vous générez un projet dans l’environnement de développement intégré (IDE) Visual Studio, il utilise l’outil msbuild.exe, un fichier de projet basé sur XML et des fichiers de paramètres facultatifs. Bien que vous pouvez utiliser msbuild.exe et un fichier de projet sur la ligne de commande, l’IDE fournit une interface utilisateur afin que vous puissiez plus facilement configurer les paramètres et générer un projet. Cette présentation décrit la manière dont Visual C++ utilise le système MSBuild.  
  
## <a name="prerequisites"></a>Composants requis  
 Lisez les documents suivants à propos de MSBuild.  
  
 [MSBuild](MSBuild1.md)  
 Vue d’ensemble des concepts MSBuild.  
  
 [Référence MSBuild](../Topic/MSBuild%20Reference.md)  
 Informations de référence sur le système MSBuild.  
  
 [Référence de schéma de fichier de projet](../Topic/MSBuild%20Project%20File%20Schema%20Reference.md)  
 Répertorie les éléments de schémas XML MSBuild, ainsi que leurs attributs et éléments enfants et parents. Notez en particulier le [ItemGroup](../Topic/ItemGroup%20Element%20\(MSBuild\).md), [PropertyGroup](../Topic/PropertyGroup%20Element%20\(MSBuild\).md), [cible](../Topic/Target%20Element%20\(MSBuild\).md), et [tâche](../Topic/Task%20Element%20\(MSBuild\).md) éléments.  
  
 [Référence de ligne de commande](../Topic/MSBuild%20Command-Line%20Reference.md)  
 Décrit les arguments de ligne de commande et les options que vous pouvez utiliser avec msbuild.exe.  
  
 [Référence des tâches](../Topic/MSBuild%20Task%20Reference.md)  
 Décrit les tâches MSBuild. Notez en particulier ces tâches, qui sont spécifiques à Visual C++ : [BscMake, tâche](../Topic/BscMake%20Task.md), [CL, tâche](../Topic/CL%20Task.md), [CPPClean, tâche](../Topic/CPPClean%20Task.md), [LIB (tâche)](../Topic/LIB%20Task.md), [lier la tâche](../Topic/Link%20Task.md), [MIDL (tâche)](../Topic/MIDL%20Task.md), [MT, tâche](../Topic/MT%20Task.md), [RC, tâche](../Topic/RC%20Task.md), [setenv, tâche](../Topic/SetEnv%20Task.md), [VCMessage, tâche](../Topic/VCMessage%20Task.md), [XDCMake, tâche](../Topic/XDCMake%20Task.md), [tâche XSD](../Topic/XSD%20Task.md).  
  
## <a name="msbuild-on-the-command-line"></a>MSBuild sur la ligne de commande  
 L’instruction suivante à partir de la [de ligne de commande référence](../Topic/MSBuild%20Command-Line%20Reference.md) document montre que l’outil msbuild.exe prend un implicite ou explicite `project file` argument (fichier .vcxproj pour les projets Visual C++) et zéro ou plus de la ligne de commande `options`.  
  
 **msbuild.exe [** `project file` **] [** `options` **]**  
  
 Utilisez le **/target** (ou **/t**) et **cette propriété** (ou **/p**) les options de ligne de commande pour remplacer les propriétés et les cibles qui sont spécifiées dans le fichier projet.  
  
 Des fonctions essentielles du fichier projet consiste à spécifier un *cible*, qui est une opération spécifique appliquée à votre projet et que les entrées et sorties qui sont requis pour effectuer cette opération. Un fichier de projet peut spécifier une ou plusieurs cibles, qui peuvent inclure une cible par défaut.  
  
 Chaque cible se compose d’une séquence d’un ou plusieurs *tâches*. Chaque tâche est représentée par une classe .NET Framework qui contient une commande exécutable. Par exemple, le [tâche CL](../Topic/CL%20Task.md) contient le [cl.exe](../build/reference/compiling-a-c-cpp-program.md) commande.  
  
 Un *paramètre de la tâche* est une propriété de la tâche de classe et représente généralement une option de ligne de commande de la commande exécutable. Par exemple, le `FavorSizeOrSpeed` paramètre de la `CL` tâche correspond à la **/Os** et **/Ot** options du compilateur.  
  
 Les paramètres de tâche supplémentaires prennent en charge l’infrastructure MSBuild. Par exemple, le `Sources` paramètre de la tâche spécifie un ensemble de tâches qui peuvent être consommées par d’autres tâches. Pour plus d’informations sur les tâches MSBuild, consultez [référence des tâches](../Topic/MSBuild%20Task%20Reference.md).  
  
 La plupart des tâches requièrent des entrées et sorties, telles que les noms de fichiers, chemins d’accès et chaîne, numériques ou booléennes paramètres. Par exemple, une entrée commune est le nom d’un fichier de source .cpp à compiler. Un paramètre d’entrée important est une chaîne qui spécifie la configuration de build et la plateforme, par exemple, « débogage &#124 ; Win32 ». Entrées et sorties sont spécifiées par un ou plusieurs XML défini par l’utilisateur `Item` éléments contenus dans un `ItemGroup` élément.  
  
 Un fichier de projet peut également spécifier définis par l’utilisateur *propriétés* et *groupe de définitions d’élément**éléments*. Propriétés et éléments forment des paires nom/valeur qui peuvent être utilisés en tant que variables dans la build. Le composant de nom d’une paire définit un *macro*, et le composant de valeur déclare la *valeur macro*. Une macro de propriété est accessible à l’aide de $(*nom*) notation et une macro d’élément est accessible à l’aide de %(*nom*) notation.  
  
 Autres éléments XML dans un fichier projet peuvent tester des macros, puis conditionnelle la valeur d’une macro ou contrôler l’exécution de la build. Noms de macros et les chaînes littérales peuvent être concaténées pour générer des constructions telles qu’un nom de chemin d’accès et de fichier. Sur la ligne de commande, le **cette propriété** option définit ou substitue une propriété de projet. Les éléments ne peuvent pas être référencés sur la ligne de commande.  
  
 Le système MSBuild peut exécuter de façon conditionnelle une cible avant ou après une autre cible. En outre, le système peut générer une cible si les fichiers que la cible consomme sont plus récents que les fichiers qu’elle émet.  
  
## <a name="msbuild-in-the-ide"></a>MSBuild dans l’IDE  
 Lorsque vous définissez les propriétés de projet dans l’IDE et puis enregistrez le projet, Visual C++ écrit les paramètres du projet dans votre fichier projet. Le fichier projet contienne des paramètres qui sont uniques à votre projet, mais il ne contient pas tous les paramètres qui sont requis pour générer votre projet. Le fichier projet contient `Import` qui comprennent un réseau d’autres éléments *fichiers de support.* Les fichiers de support contiennent les propriétés, les cibles et les paramètres qui sont requis pour générer le projet restants.  
  
 La plupart des cibles et des propriétés dans les fichiers de prise en charge existent uniquement pour implémenter le système de génération. La section suivante décrit certaines cibles et propriétés utiles que vous pouvez spécifier sur la ligne de commande MSBuild. Pour découvrir d’autres cibles et propriétés, explorez les fichiers dans les répertoires de fichiers de prise en charge.  
  
### <a name="support-file-directories"></a>Répertoires de fichiers de prise en charge  
 Par défaut, les fichiers de prise en charge de Visual C++ principales sont situés dans les répertoires suivants.  
  
|Répertoire|Description|  
|---------------|-----------------|  
|*lecteur*: \Program Files\MSBuild\Microsoft.Cpp\v4.0\\*version*\|Contient les fichiers cibles (.targets) et fichiers de propriétés (.props) qui sont utilisés par les cibles. Par défaut, la macro $ (VCTargetsPath) référence ce répertoire.|  
|*lecteur*: \Program Files\MSBuild\Microsoft.Cpp\v4.0\\*version*\Platforms\\*plate-forme*\|Contient les fichiers spécifiques à la plateforme cible et la propriété qui substituent les cibles et les propriétés de son répertoire parent. Ce répertoire contient également un fichier .dll qui définit les tâches qui sont utilisés par les cibles dans ce répertoire.<br /><br /> Le *plate-forme* espace réservé représente le `ARM`, `Win32`, ou `x64` sous-répertoire.|  
|*lecteur*: \Program Files\MSBuild\Microsoft.Cpp\v4.0\\*version*\Platforms\\*plate-forme*\PlatformToolsets\\*ensemble d’outils*\|Contient les répertoires qui permettent la génération de générer des applications Visual C++ avec la valeur *version* de l’ensemble d’outils.<br /><br /> Le *plate-forme* espace réservé représente le `ARM`, `Win32`, ou `x64` sous-répertoire. Le *toolset* espace réservé représente le sous-répertoire de l’ensemble d’outils pour générer des applications Windows, Windows XP ou Windows Phone.|  
|*lecteur*: Files\MSBuild\Microsoft.Cpp\v4.0\Platforms\\*plate-forme*\PlatformToolsets\\*ensemble d’outils*\|Contient les répertoires qui permettent la génération générer les applications Visual C++ 10.0 ou 9.0.<br /><br /> Le *plate-forme* espace réservé représente le `Itanium`, `Win32`, ou `x64` sous-répertoire. Le *toolset* espace réservé représente le `v90` ou `v100` sous-répertoire de l’ensemble d’outils.|  
  
### <a name="support-files"></a>Fichiers de prise en charge  
 Les répertoires de fichiers de support contiennent des fichiers portant les extensions suivantes.  
  
|Extension|Description|  
|---------------|-----------------|  
|.targets|Contient `Target` les éléments XML qui spécifient les tâches exécutées par la cible. Peut également contenir `Property Group`, `Item Group`, `Item Definition Group`, définis par l’utilisateur `Item` les éléments qui sont utilisés pour assigner des fichiers et des options de ligne de commande aux paramètres de tâche.<br /><br /> Pour plus d’informations, consultez [Target, élément (MSBuild)](../Topic/Target%20Element%20\(MSBuild\).md).|  
|.props|Contient `Property Group` définis par l’utilisateur `Property` les éléments XML qui spécifient des fichiers et des paramètres qui sont utilisés pendant la génération.<br /><br /> Peut également contenir des `Item Definition Group` définis par l’utilisateur `Item` les éléments XML qui spécifient des paramètres supplémentaires. Les éléments définis dans un groupe de définitions d’élément sont semblables aux propriétés, mais ne sont pas accessibles à partir de la ligne de commande. Fichiers projet Visual C++ utilise fréquemment des éléments au lieu des propriétés pour représenter des paramètres.<br /><br /> Pour plus d’informations, consultez [ItemGroup, élément (MSBuild)](../Topic/ItemGroup%20Element%20\(MSBuild\).md), [ItemDefinitionGroup, élément (MSBuild)](../Topic/ItemDefinitionGroup%20Element%20\(MSBuild\).md), et [Item, élément (MSBuild)](../Topic/Item%20Element%20\(MSBuild\).md).|  
|.xml|Contient des éléments XML qui déclarent et initialisent des éléments d’interface utilisateur IDE tels que les feuilles de propriétés et les pages de propriétés et les contrôles de zone de liste et zone de texte.<br /><br /> Les fichiers .xml prend directement en charge l’IDE mais pas MSBuild. Toutefois, les valeurs des propriétés IDE sont attribués pour générer des propriétés et des éléments.<br /><br /> La plupart des fichiers .xml sont dans un sous-répertoire spécifique aux paramètres régionaux. Par exemple, les fichiers pour la région anglais (États-Unis) sont dans $(VCTargetsPath) \1033\\.|  
  
## <a name="user-targets-and-properties"></a>Cibles et propriétés utilisateur  
 Pour utiliser MSBuild plus efficacement sur la ligne de commande, il est utile de connaître les propriétés et cibles sont utiles et pertinentes. La plupart des propriétés et cibles aident à implémenter le système de génération Visual C++ et par conséquent, ne sont pas pertinentes pour l’utilisateur. Cette section décrit certaines propriétés d’orienté utilisateur utiles et les cibles.  
  
### <a name="platformtoolset-property"></a>Propriété PlatformToolset  
 Le `PlatformToolset` propriété détermine l’ensemble d’outils Visual C++ est utilisé dans la build. La valeur de la propriété est concaténée avec des chaînes littérales pour former le chemin d’accès d’un répertoire qui contient les fichiers cible et de propriété qui sont requis pour créer un projet pour une plateforme particulière.  
  
 Définir le `PlatformToolset` propriété `v110` utiliser [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] Outils et bibliothèques pour générer votre application.  
  
 `msbuild myProject.vcxproj /p:PlatformToolset=v110`  
  
 Définir le `PlatformToolset` propriété `v100` utiliser [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)] Outils et bibliothèques pour générer votre application.  
  
 `msbuild myProject.vcxproj /p:PlatformToolset=v100`  
  
 Définir le `PlatformToolset` propriété `v90` à utiliser des bibliothèques et des outils Visual C++ 2008 pour générer votre application. L’ensemble d’outils Visual C++ 2008 doit déjà être installé sur votre ordinateur pour que cette propriété soit effective.  
  
 `msbuild myProject.vcxproj /p:PlatformToolset=v90`  
  
### <a name="preferredtoolarchitecture-property"></a>Propriété de PreferredToolArchitecture  
 Le `PreferredToolArchitecture` propriété détermine si le compilateur 32 bits ou 64 bits et les outils sont utilisés dans la build. Cette propriété n’affecte pas l’architecture de plate-forme de sortie ou la configuration. Par défaut, MSBuild utilise le x86 version du compilateur et des outils si cette propriété n’est pas définie, ou est définie à toute valeur autre que `x64`.  
  
 Définir le `PreferredToolArchitecture` propriété `x64` à utiliser le compilateur 64 bits et les outils pour créer votre application.  
  
 `msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`  
  
### <a name="useenv-property"></a>Propriété UseEnv  
 Par défaut, les paramètres spécifiques à la plateforme du projet actuel substituent les variables d’environnement PATH, INCLUDE, LIB, LIBPATH, CONFIGURATION et PLATEFORME. Définir le `UseEnv` propriété `true` afin de garantir que les variables d’environnement ne sont pas substitués.  
  
 `msbuild myProject.vcxproj /p:UseEnv=true`  
  
### <a name="targets"></a>Cibles  
 Il existe des centaines de cibles dans les fichiers de prise en charge de Visual C++. Toutefois, la plupart sont des cibles orientées système que l’utilisateur peut ignorer. La plupart des cibles système sont préfixées par un trait de soulignement (_), ou avoir un nom commençant par « PrepareFor », « Compute », « Avant », « After », « Pre » ou « Post ».  
  
 Le tableau suivant répertorie plusieurs cibles orientées utilisateur intéressante.  
  
|une cible|Description|  
|------------|-----------------|  
|BscMake|Exécute l’outil Microsoft Browse Information Maintenance Utility, bscmake.exe.|  
|Build|Génère le projet.<br /><br /> Il s’agit de la cible par défaut pour un projet.|  
|ClCompile|Exécute l’outil du compilateur Visual C++, cl.exe.|  
|Nettoyer|Fichiers de génération temporaires et intermédiaires de suppressions.|  
|Lib|Exécute le Gestionnaire de bibliothèque Microsoft 32 bits, lib.exe.|  
|Link|Exécute l’outil de l’éditeur de liens Visual C++, link.exe.|  
|ManifestResourceCompile|Extrait une liste des ressources d’un manifeste, puis exécute l’outil compilateur de ressources Microsoft Windows, rc.exe.|  
|MIDL|Exécute l’outil de compilateur Microsoft Interface Definition Language (MIDL), midl.exe.|  
|Régénérer|Nettoie, puis génère votre projet.|  
|ResourceCompile|Exécute le compilateur de ressources Microsoft Windows, rc.exe.|  
|XdcMake|Exécute l’outil XML Documentation, xdcmake.exe.|  
|XSD|Exécute l’outil XML Schema Definition, xsd.exe.|  
  
## <a name="see-also"></a>Voir aussi  
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)