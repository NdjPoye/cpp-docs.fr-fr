---
title: structure du fichier .vcxproj et .props | Documents Microsoft
ms.custom: 
ms.date: 04/27/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- .vcxproj file structure
ms.assetid: 14d0c552-29db-480e-80c1-7ea89d6d8e9c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d48b16d9a4250de8c8c3dfef62fdcfb5c1434960
ms.sourcegitcommit: 6f40bba1772a09ff0e3843d5f70b553e1a15ab50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/22/2018
---
# <a name="vcxproj-and-props-file-structure"></a>structure du fichier .vcxproj et .props

MSBuild est le système de projet par défaut dans Visual Studio ; Lorsque vous choisissez **fichier | Nouveau projet** dans Visual C++, vous créez un projet MSBuild dont les paramètres sont stockés dans un fichier de projet XML portant l’extension `.vcxproj`. Le fichier projet peut également importer des fichiers .targets où les paramètres peuvent être stockées et les fichiers .props. Dans la plupart des cas, vous évite de devoir modifier manuellement le fichier projet et en fait vous ne devez pas modifier manuellement à moins d’avoir une bonne compréhension de MSBuild. Chaque fois que possible, vous devez utiliser les pages de propriétés de Visual Studio pour modifier les paramètres de projet (consultez [utilisation des propriétés de projet](working-with-project-properties.md). Toutefois, dans certains cas, vous devrez peut-être modifier une feuille de fichier ou de la propriété de projet manuellement. Pour ces scénarios, cet article contient des informations de base sur la structure du fichier.

**Important :**

Si vous choisissez de modifier manuellement un fichier .vcxproj, tenez compte de ces faits :

1. La structure du fichier doit suivre un formulaire prescrit, qui est décrit dans cet article.

1. Le système de projet Visual C++ actuellement ne prend pas en charge les caractères génériques dans les éléments de projet. Par exemple, cela n’est pas reconnu :

   ```xml
   <ClCompile Include="*.cpp"/>
   ```

1. Le système de projet Visual C++ actuellement ne prend pas en charge les macros dans les chemins d’élément de projet. Par exemple, cela n’est pas reconnu :

   ```xml
   <ClCompile Include="$(IntDir)\generated.cpp"/>
   ```

1. Afin d’avoir des propriétés du projet correctement ajouté, supprimé ou modifié lors de la modification dans le **propriétés du projet** boîte de dialogue, le fichier doit contenir des groupes distincts pour chaque configuration de projet et les conditions doivent être sous cette forme :

   ```xml
   Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'"
   ```

1. Chaque propriété doit être spécifiée dans le groupe avec l’étiquette approprié, tel que spécifié dans le fichier de règle de propriété. Pour plus d’informations, consultez [fichiers de règle de propriété page xml](property-page-xml-files.md).

## <a name="vcxproj-file-elements"></a>éléments du fichier .vcxproj

Vous pouvez inspecter le contenu d’un fichier .vcxproj à l’aide de n’importe quel texte ou un éditeur XML. Vous pouvez les consulter dans Visual Studio en cliquant sur le projet dans l’Explorateur de solutions, en choisissant **décharger le projet** , puis en choisissant **Foo.vcxproj de modifier**.

La première chose à remarquer est que les éléments de niveau supérieur s’affichent dans un ordre particulier. Exemple :

- la plupart des groupes de propriétés et groupes d’éléments de définition se produire après l’importation de Microsoft.Cpp.Default.props.
- toutes les cibles sont importés à la fin du fichier.
- Il existe plusieurs groupes de propriétés, chacun avec un nom unique, et elles se produisent dans un ordre particulier.

L’ordre des éléments dans le fichier projet est très important, car MSBuild est basé sur un modèle d’évaluation séquentielle.  Si votre fichier projet, y compris toutes .props importées et les fichiers .targets, se compose de plusieurs définitions d’une propriété, la dernière définition remplace les précédents. Dans l’exemple suivant, la valeur « xyz » est définie lors de la compilation, car MSBUild moteur rencontre lors de son évaluation il de la dernière.

```xml
  <MyProperty>abc</MyProperty>
  <MyProperty>xyz</MyProperty>
```

L’extrait de code suivant montre un fichier .vcxproj minimale. N’importe quel fichier .vcxproj généré par Visual Studio contient ces éléments MSBuild de niveau supérieur et elles apparaissent dans cet ordre (bien qu’ils peuvent contenir plusieurs copies de chaque élément de niveau supérieur à ce type). Notez que `Label` attributs sont des balises arbitraires qui sont uniquement utilisées par Visual Studio en tant que variables pour modifier ; ils n’ont aucune autre fonction.

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003'>
   <ItemGroup Label="ProjectConfigurations" />
   <PropertyGroup Label="Globals" />
   <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
   <PropertyGroup Label="Configuration" />
   <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
   <ImportGroup Label="ExtensionSettings" />
   <ImportGroup Label="PropertySheets" />
   <PropertyGroup Label="UserMacros" />
   <PropertyGroup />
   <ItemDefinitionGroup />
   <ItemGroup />
   <Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
   <ImportGroup Label="ExtensionTargets" />
 </Project>
```

Les sections suivantes décrivent l’objectif de chacun de ces éléments et pourquoi ils sont classés ainsi :

### <a name="project-element"></a>Élément de projet

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003' >
```

`Project`est le nœud racine. Il spécifie la version de MSBuild à utiliser, ainsi que la cible par défaut doit être exécuté lorsque ce fichier est passé à MSBuild.exe.

### <a name="projectconfigurations-itemgroup-element"></a>ProjectConfigurations ItemGroup, élément

```xml
<ItemGroup Label="ProjectConfigurations" />
```

`ProjectConfigurations`contient la description de configuration de projet. Citons débogage | Win32, version | Win32, débogage | ARM et ainsi de suite. Plusieurs paramètres de projet sont spécifiques à une configuration donnée. Par exemple, vous souhaiterez probablement définir les propriétés de l’optimisation d’une version Release, mais pas une version debug.

Le `ProjectConfigurations` groupe d’éléments n’est pas utilisé au moment de la génération. L’IDE de Visual Studio est nécessaire afin de charger le projet. Ce groupe d’éléments de peut être déplacé vers un fichier .props et importé dans le fichier .vcxproj. Toutefois, dans ce cas, si vous avez besoin ajouter ou supprimer des configurations, vous devez modifier manuellement le fichier .props. Vous ne pouvez pas utiliser l’IDE.

### <a name="projectconfiguration-elements"></a>Éléments de configuration

L’extrait de code suivant montre une configuration de projet. Dans cet exemple « Debug | x 64' est le nom de configuration. Le nom de configuration de projet doit être dans le format $(Configuration)|$(Platform). Un nœud de Configuration de projet peut avoir deux propriétés : Configuration et plateforme. Ces propriétés sont automatiquement définies avec les valeurs spécifiées ici lors de la configuration est active.

   ```xml
   <ProjectConfiguration Include="Debug|x64">
     <Configuration>Debug</Configuration>
     <Platform>x64</Platform>
   </ProjectConfiguration>
   ```

L’IDE s’attend à trouver une configuration de projet pour n’importe quelle combinaison de valeurs de Configuration et la plateforme utilisée dans tous les éléments de configuration. Cela signifie souvent qu’un projet peut avoir des configurations de projet sans signification pour répondre à cette exigence. Par exemple, si un projet possède ces configurations :

- Déboguer | Win32
- Vente au détail | Win32
- Optimisation de 32 bits spéciale | Win32

elle doit également avoir ces configurations, bien que « Optimisation spéciale de 32 bits » n’a aucune signification pour x64 :

- Debug|x64
- Vente au détail | x64
- Optimisation de 32 bits spéciale | x64

Vous pouvez désactiver la génération et déploiement de commandes pour les paramètres dans le **Gestionnaire de Configuration de Solution**.

### <a name="globals-propertygroup-element"></a>Élément Globals PropertyGroup

```xml
 <PropertyGroup Label="Globals" />
```

`Globals`contient des paramètres de niveau de projet comme ProjectGuid RootNamespace et applicationtype en / ApplicationTypeRevision. Les deux derniers définissent souvent la cible du système d’exploitation. Un projet peut uniquement cibler un système d’exploitation unique dû au fait que les références et les éléments de projet ne peut pas avoir conditions actuellement. Ces propriétés sont généralement pas substituées ailleurs dans le fichier projet. Ce groupe n’est pas dépendantes de la configuration, et par conséquent généralement qu’un seul groupe Globals existe dans le fichier projet.

### <a name="microsoftcppdefaultprops-import-element"></a>Importation de Microsoft.Cpp.default.props, élément

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
```

Le **Microsoft.Cpp.default.props** feuille de propriétés est fourni avec Visual Studio et ne peut pas être modifiée. Il contient les paramètres par défaut pour le projet. Les valeurs par défaut peuvent varier selon l’applicationtype en.

### <a name="configuration-propertygroup-elements"></a>Éléments de configuration PropertyGroup

```xml
<PropertyGroup Label="Configuration" />
```

A `Configuration` groupe de propriétés a une condition de configuration attachée (tel que `Condition=”'$(Configuration)|$(Platform)'=='Debug|Win32'”`) et est disponible en plusieurs copies, un par configuration. Ce groupe de propriétés héberge les propriétés qui sont définies pour une configuration spécifique. Propriétés de configuration incluent PlatformToolset et également contrôler l’inclusion de feuilles de propriétés système dans **Microsoft.Cpp.props**. Par exemple, si vous définissez la propriété `<CharacterSet>Unicode</CharacterSet>`, puis la feuille de propriétés système **microsoft. Cpp.unicodesupport.props** seront inclus. Si vous Inspectez **Microsoft.Cpp.props**, vous verrez la ligne : `<Import Condition=”'$(CharacterSet)' == 'Unicode'”   Project=”$(VCTargetsPath)\microsoft.Cpp.unicodesupport.props”/>`.

### <a name="microsoftcppprops-import-element"></a>Importation de Microsoft.Cpp.props, élément

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
```

Le **Microsoft.Cpp.props** feuille de propriétés (directement ou via des importations) définit les valeurs par défaut pour de nombreuses propriétés spécifiques aux outils tels que l’optimisation et le niveau d’avertissement de propriétés du compilateur, TypeLibraryName l’outil MIDL propriété et ainsi de suite. Il importe également différentes feuilles de propriétés système basés sur les propriétés de configuration sont définies dans le groupe de propriétés immédiatement au-dessus.

### <a name="extensionsettings-importgroup-element"></a>Élément ExtensionSettings ImportGroup

```xml
<ImportGroup Label="ExtensionSettings" />
```

Le `ExtensionSettings` groupe contient des importations pour les feuilles de propriétés qui font partie des personnalisations de Build. Une personnalisation de Build est définie par trois fichiers : un fichier .targets, un fichier .props et un fichier .xml. Ce groupe d’importation contient les importations pour le fichier .props.

### <a name="propertysheets-importgroup-elements"></a>Éléments PropertySheets ImportGroup

```xml
<ImportGroup Label="PropertySheets" />
```

Le `PropertySheets` groupe contient les importations de feuilles de propriétés utilisateur. Voici les feuilles de propriétés que vous ajoutez via la vue du Gestionnaire de propriétés dans Visual Studio. L’ordre dans lequel ces importations sont répertoriées est important et est répercutée dans le Gestionnaire de propriétés. Le fichier projet contient généralement plusieurs instances de ce type de groupe d’importation, une pour chaque configuration de projet.

### <a name="usermacros-propertygroup-element"></a>Élément UserMacros PropertyGroup

```xml
<PropertyGroup Label="UserMacros" />
```

`UserMacros`contient des propriétés vous créez en tant que variables qui sont utilisés pour personnaliser votre processus de génération. Par exemple, vous pouvez définir une macro utilisateur pour définir votre chemin d’accès de sortie personnalisée comme $(CustomOutputPath) et l’utiliser pour définir d’autres variables. Ce groupe de propriétés contient des propriétés. Notez que dans Visual Studio, ce groupe n’est pas rempli dans le fichier projet, car Visual C++ ne prend pas en charge les macros utilisateur pour les configurations. Macros utilisateur sont prises en charge dans les feuilles de propriétés.

### <a name="per-configuration-propertygroup-elements"></a>Éléments de PropertyGroup par configuration

```xml
<PropertyGroup />
```

Il existe plusieurs instances de ce groupe de propriétés, une par une configuration pour toutes les configurations de projet. Chaque groupe de la propriété doit avoir une condition de configuration attachée. Si toutes les configurations sont manquantes, la **propriétés du projet** boîte de dialogue ne fonctionne pas correctement. Contrairement aux groupes à la propriété ci-dessus, celle-ci n’a pas une étiquette. Ce groupe contient les paramètres de configuration au niveau du projet. Ces paramètres s’appliquent à tous les fichiers qui font partie du groupe d’éléments spécifié. Définition d’élément de personnalisation de build métadonnées sont initialisée ici.

Cet élément PropertyGroup doit être placée après `<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />` et il ne doit y avoir aucun autre PropertyGroup sans étiquette avant (sinon, la modification des propriétés du projet ne fonctionnera pas correctement).

### <a name="per-configuration-itemdefinitiongroup-elements"></a>Éléments ItemDefinitionGroup par configuration

```xml
 <ItemDefinitionGroup />
```

Contient les définitions d’élément. Ces derniers doivent respecter les mêmes règles de conditions que les éléments PropertyGroup sans étiquette par configuration.

### <a name="itemgroup-elements"></a>Éléments ItemGroup

```xml
<ItemGroup />
```

Contient les éléments (fichiers sources, etc.) dans le projet. Conditions ne sont pas prises en charge pour les éléments de projet (les types d’éléments qui sont considérées comme des éléments de projet par les définitions de règles, autrement dit,).

Les métadonnées doivent avoir des conditions de configuration pour chaque configuration, même si elles sont identiques. Exemple :

   ```xml
   <ItemGroup>
     <ClCompile Include="stdafx.cpp">
       <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">true</TreatWarningAsError>
       <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|x64’">true</TreatWarningAsError>
     </ClCompile>
   </ItemGroup>
   ```

Le système de projet Visual C++ actuellement ne prend pas en charge les caractères génériques dans les éléments de projet.

   ```xml
   <ItemGroup>
     <ClCompile Include="*.cpp"> <!--Error-->
   </ItemGroup>
   ```

Le système de projet Visual C++ actuellement ne prend pas en charge les macros dans les éléments de projet.

   ```xml
   <ItemGroup>
     <ClCompile Include="$(IntDir)\generated.cpp"> <!--not guaranteed to work in all scenarios-->
   </ItemGroup>
   ```

Les références sont spécifiées dans un ItemGroup, et ils ont ces limitations :

- Références ne prennent pas en charge les conditions.
- Référence les métadonnées ne prennent pas en charge les conditions.

### <a name="microsoftcpptargets-import-element"></a>Microsoft.Cpp.targets Import, élément

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
```

Définit (directement ou via des importations) Visual C++ cibles permettant notamment la génération, nettoyer, etc.

### <a name="extensiontargets-importgroup-element"></a>Élément ImportGroup de ExtensionTargets

```xml
<ImportGroup Label="ExtensionTargets" />
```

Ce groupe contient des importations pour les fichiers de cible de personnalisation de Build.

## <a name="impact-of-incorrect-ordering"></a>Impact de classement incorrect

L’IDE de Visual Studio dépend du fichier projet ayant que l’ordre décrit ci-dessus. Par exemple, lorsque vous définissez une valeur de propriété dans les pages de propriétés, l’IDE généralement place la définition de propriété dans le groupe de propriétés avec l’étiquette vide. Cela garantit que les valeurs par défaut dans les feuilles de propriétés système sont remplacées par les valeurs définies par l’utilisateur. De même, les fichiers cibles sont importés à la fin, car ils utilisent les propriétés définies ci-dessus et dans la mesure où ils ne définissent généralement pas de propriétés elles-mêmes. De même, les feuilles de propriétés utilisateur sont importées après les feuilles de propriétés système (inclus par **Microsoft.Cpp.props**). Cela garantit que l’utilisateur peut remplacer les valeurs par défaut introduits par les feuilles de propriétés système.

Si un fichier .vcxproj ne suit pas cette mise en page, les résultats de build peut-être pas ce que vous attendez. Par exemple, si vous importez accidentellement une feuille de propriétés système après les feuilles de propriétés définies par l’utilisateur, les paramètres utilisateur seront remplacées par les feuilles de propriétés système.

L’expérience au moment du design IDE même dépend dans une certaine mesure le classement correct des éléments. Par exemple, si votre fichier .vcxproj n’est pas le `PropertySheets` groupe d’importation, l’IDE n’est peut-être pas en mesure de déterminer où placer une nouvelle feuille de propriétés que l’utilisateur a créé dans **Gestionnaire de propriétés**. Cela peut entraîner une feuille de l’utilisateur en cours de substitution par une feuille de système. Bien que l’heuristique utilisée par l’IDE peut tolérer des incohérences mineures dans la mise en page du fichier .vcxproj, il est fortement recommandé de ne pas dévier de la structure indiquée plus haut dans cet article.

## <a name="how-the-ide-uses-element-labels"></a>Comment l’IDE utilise des étiquettes d’élément

Dans l’IDE, lorsque vous définissez la **UseOfAtl** propriété dans la page Propriétés générales, il est écrit pour le groupe de propriétés de Configuration dans le fichier projet, tandis que la **TargetName** propriété dans la même page de propriétés est écrit dans le groupe de propriétés de configuration par sans étiquette. Visual Studio recherche au fichier xml de la page propriété pour obtenir les informations sur l’emplacement de l’écriture de chaque propriété. Pour le **général** page de propriétés (en supposant que vous avez une version anglaise de Visual Studio Enterprise Edition), si le fichier est `%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033\general.xml`. Le fichier de règle de propriété page XML définit les informations statiques sur une règle et toutes ses propriétés. Une telle information est la position par défaut d’une propriété de règle dans le fichier de destination (le fichier où sera écrit sa valeur). La position par défaut est spécifiée par l’attribut de l’étiquette sur les éléments du fichier projet.

## <a name="property-sheet-layout"></a>Mise en page de feuille de propriétés

L’extrait de code XML suivant est une disposition minimale d’un fichier de feuille (.props) de propriété. Il est similaire à un fichier .vcxproj, et les fonctionnalités des éléments .props peuvent être déduite à partir de la discussion précédente.

```xml
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ImportGroup Label="PropertySheets" />
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup />
  <ItemDefinitionGroup />
  <ItemGroup />
</Project>
```

Pour rendre votre propre feuille de propriétés, copiez, parmi les fichiers .props dans le dossier VCTargets et modifiez-le selon vos besoins. Pour l’édition de Visual Studio 2017 Enterprise, le chemin d’accès de VCTargets par défaut est `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets`.

## <a name="see-also"></a>Voir aussi

[Utilisation des propriétés de projet](working-with-project-properties.md)  
[Fichiers XML de la page de propriétés](property-page-xml-files.md)  
