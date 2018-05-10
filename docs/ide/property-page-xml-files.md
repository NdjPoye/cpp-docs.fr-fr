---
title: Fichiers de règles XML de la Page de propriété | Documents Microsoft
ms.custom: ''
ms.date: 04/27/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property page XML files
ms.assetid: dd9d9734-4387-4098-8ba6-85b93507731d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fcee2c416fba6a959785826781aefd96b0d06d75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="property-page-xml-rule-files"></a>Fichiers de règles XML de la Page de propriété
Les pages de propriétés de projet dans l’IDE sont configurés par les fichiers XML dans le dossier VCTargets. Le chemin d’accès exact varie selon les edition(s) de Visual Studio est installés et que la langue du produit. Pour Visual Studio 2017 Enterprise Edition, en anglais, le chemin d’accès est `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`. Les fichiers XML décrivent les noms des règles, les catégories et chacune de ces propriétés, leur type de données, les valeurs par défaut, et comment ils doivent être affichés. Lorsque vous définissez une propriété dans l’IDE, la nouvelle valeur est stockée dans le fichier projet.

Les seuls scénarios dans lesquels vous devez comprendre que le fonctionnement interne de ces fichiers et de l’IDE de Visual Studio est (a) vous souhaitant créer une page de propriétés personnalisées, ou (b) vous souhaitez personnaliser les propriétés de votre projet par un moyen autre que via l’IDE de Visual Studio. 

Tout d’abord, nous allons ouvrir les pages de propriétés pour un projet (cliquez avec le bouton droit sur le nœud de projet dans **l’Explorateur de solutions** et choisissez Propriétés) :
   
![Propriétés de projet Visual C++](media/cpp-property-page-2017.png)

Chaque nœud sous **propriétés de Configuration** est appelée une règle. Une règle représente parfois un seul outil comme le compilateur, mais en général, le terme fait référence à un élément qui a des propriétés, qui s’exécute et qui peut produire une sortie. Chaque règle est remplie à partir d’un fichier xml dans le dossier VCTargets. Par exemple, la règle de C/C++ qui est indiquée ci-dessus est remplie par 'cl.xml'.

Comme indiqué ci-dessus, chaque règle a un jeu de propriétés qui sont organisées en catégories. Chaque sous-nœud sous une règle représente une catégorie. Par exemple, le nœud optimisation sous C/C++ contient toutes les propriétés de l’optimisation de l’outil du compilateur. Les propriétés et leurs valeurs elles-mêmes sont rendus sous forme de grille dans le volet droit.

Vous pouvez ouvrir cl.xml dans le bloc-notes ou n’importe quel éditeur XML (voir ci-dessous d’instantané). Vous verrez un nœud racine appelé règle qui possède la même liste de propriétés définies dans cette section comme s’affiche dans l’interface utilisateur, ainsi que des métadonnées supplémentaires.

```xml  
<?xml version="1.0" encoding="utf-8"?>
<!--Copyright, Microsoft Corporation, All rights reserved.-->
<Rule Name="CL" PageTemplate="tool" DisplayName="C/C++" SwitchPrefix="/" Order="10" xmlns="http://schemas.microsoft.com/build/2009/properties" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Rule.Categories>
    <Category Name="General" DisplayName="General" />
    <Category Name="Optimization" DisplayName="Optimization" />
    <Category Name="Preprocessor" DisplayName="Preprocessor" />
    <Category Name="Code Generation" DisplayName="Code Generation" />
    <Category Name="Language" DisplayName="Language" />
    <Category Name="Precompiled Headers" DisplayName="Precompiled Headers" />
    <Category Name="Output Files" DisplayName="Output Files" />
    <Category Name="Browse Information" DisplayName="Browse Information" />
    <Category Name="Advanced" DisplayName="Advanced" />
    <Category Name="All Options" DisplayName="All Options" Subtype="Search" />
    <Category Name="Command Line" DisplayName="Command Line" Subtype="CommandLine" />
  </Rule.Categories>
...
``` 

Il existe un fichier XML correspondant à chaque nœud sous propriétés de Configuration dans les pages de propriétés de l’interface utilisateur. Vous pouvez ajouter ou supprimer des règles dans l’interface utilisateur en incluant ou en supprimant des emplacements de fichiers XML correspondants dans le projet. Il s’agit par exemple, comment Microsoft.CppBuild.targets (un niveau au-dessus du dossier 1033) inclut cl.xml :

```xml  
<PropertyPageSchema Condition="'$(ConfigurationType)' != 'Utility'" Include="$(VCTargetsPath)$(LangID)\cl.xml"/>

``` 
Si vous supprimez cl.xml de toutes les données, vous obtiendrez avec la structure suivante :
```xml  
<?xml version="1.0" encoding="utf-8"?>
<Rule>
  <Rule.DataSource />
  <Rule.Categories>
    <Category />
        ...
  </Rule.Categories>
  <BoolProperty />
  <EnumProperty />
  <IntProperty />
  <StringProperty />
  <StringListProperty />
</Rule>
``` 

La section suivante décrit les principaux éléments de votre choix et certaines métadonnées pouvant être attachés à ceux-ci.

1. **La règle :** règle est généralement le nœud racine dans le fichier xml ; il peut avoir de nombreux attributs :

```xml    
<Rule Name="CL" PageTemplate="tool" SwitchPrefix="/" Order="10"
          xmlns="http://schemas.microsoft.com/build/2009/properties"
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
          xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Rule.DisplayName>
    <sys:String>C/C++</sys:String>
  </Rule.DisplayName>
```  

   a. **Nom :** l’attribut Name est un id de la règle. Il doit être unique parmi toutes les propriétés xml fichiers de la page pour un projet.

   b. **PageTemplate :** la valeur de cet attribut est utilisée par l’interface utilisateur de choisir à partir d’une collection de modèles d’interface utilisateur. Le modèle « tool » affiche les propriétés dans un format de grille standard. D’autres valeurs intégré de cet attribut sont « débogueur » et « générique ». Consultez le nœud débogage et le nœud général, respectivement, pour afficher le format de l’interface utilisateur qui résulte de la spécification de ces valeurs. L’interface utilisateur pour le modèle de page « débogueur » utilise une zone de liste déroulante pour basculer entre les propriétés des différents débogueurs tandis que le modèle « générique » affiche les catégories de propriété différente dans une page au lieu de plusieurs sous-nœuds catégorie sous la règle nœud. Cet attribut est simplement une suggestion de l’interface utilisateur ; le fichier xml est conçu pour être indépendantes de l’interface utilisateur. Une interface utilisateur différents peut-être utiliser cet attribut à des fins différentes.

  c. **SwitchPrefix :** Ceci est le préfixe utilisé dans la ligne de commande pour les commutateurs. La valeur « / » aurait pour résultat commutateurs ressembler à/Zi, /nologo, /W3, etc.

  d. **Commande :** il s’agit d’une suggestion à un client potentiel de l’interface utilisateur sur l’emplacement relatif de cette règle par rapport à toutes les autres règles du système.

  e. **xmlns :** il s’agit d’un élément XAML standard. Vous pouvez voir les trois espaces de noms répertoriés. Ces éléments correspondent aux espaces de noms pour la désérialisation XAML des classes, système et schéma espace de noms XAML, respectivement.

  f. **Nom d’affichage :** c’est le nom qui s’affiche sur la page de propriété pour le nœud de règle. Cette valeur est localisée. Nous avons créé DisplayName comme un élément enfant de la règle plutôt que comme un attribut (par exemple, le nom ou SwitchPrefix) interne de localisation en raison d’exigences de l’outil. Du point de vue XAML, les deux sont équivalentes. Par conséquent, vous pouvez simplement permettre un attribut pour réduire l’encombrement ou la laisser car il s’agit.

  g. **Source de données :** il s’agit d’une propriété très importante qui indique le système de projet, l’emplacement à partir duquel la valeur de propriété doit lues et écrites à et son regroupement (voir ci-après). Pour cl.xml, ces valeurs sont :

```xml  
       <DataSource Persistence="ProjectFile" ItemType="ClCompile" Label="" HasConfigurationCondition="true" />
```  
   - `Persistence="ProjectFile` Indique si le système de projet toutes les propriétés de la règle doivent être écrite dans le fichier de projet ou le fichier de feuille de propriétés (selon les nœud a été utilisé pour générer les pages de propriétés). L’autre valeur possible est « Fichier liste des utilisateurs » qui écrivent la valeur dans le fichier .user.

   - `ItemType="ClCompile"` Indique que les propriétés seront stockées en tant que ItemDefinition métadonnées ou des métadonnées d’élément (ce dernier uniquement si les pages de propriétés ont été générées à partir d’un nœud de fichier dans l’Explorateur de solutions) de ce type d’élément. Si ce champ n’est pas défini, la propriété est écrite comme une propriété commune dans un élément PropertyGroup.

   - `Label=""` Indique que lorsque les propriétés sont écrites en tant que `ItemDefinition` métadonnées, l’étiquette du parent ItemDefinitionGroup sera vide (tous les éléments MSBuild peuvent avoir une étiquette). Visual Studio 2017 utilise des groupes étiquetés pour naviguer dans le fichier projet .vcxproj. Notez que les groupes qui contiennent la plupart des propriétés de la règle ont une chaîne vide en tant qu’étiquette.

   - `HasConfigurationCondition="true"` Indique au système de projet d’apposer une condition de configuration à la valeur afin qu’elle s’applique uniquement pour la configuration de projet actuelle (la condition peut être apposée au groupe parent ou à la valeur elle-même). Par exemple, ouvrez les pages de propriétés du nœud de projet et définissez la valeur de la propriété **considérer les avertissements comme des erreurs** sous **propriétés de Configuration > générales de C/C++** sur « Oui ». La valeur suivante est écrite dans le fichier projet. Notez que la condition de configuration associé au parent ItemDefinitionGroup.

```xml  
     <ItemDefinitionGroup Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">
        <ClCompile>
           <TreatWarningAsError>true</TreatWarningAsError>
        </ClCompile>
     </ItemDefinitionGroup>
 ```
   Si cette valeur a été définie dans la page de propriétés pour un fichier spécifique, tel que stdafx.cpp, puis la valeur de propriété est écrit sous l’élément stdafx.cpp dans le fichier de projet, comme indiqué ci-dessous. Notez comment la condition de la configuration est directement attachée aux métadonnées lui-même.

 ```xml  
<ItemGroup>
   <ClCompile Include="stdafx.cpp">
      <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">true</TreatWarningAsError>
   </ClCompile>
</ItemGroup>
 ```
   Un autre attribut de **DataSource** non répertoriées ci-dessus est **PersistedName**. Vous pouvez utiliser cet attribut pour représenter une propriété dans le fichier de projet à l’aide d’un autre nom. Par défaut, cet attribut est défini pour la propriété **nom**. 

   Une propriété individuelle peut remplacer la source de données de son parent règle. Dans ce cas, l’emplacement de la valeur de cette propriété sera différent d’autres propriétés dans la règle.

   h. Il existe des autres attributs d’une règle, tels que la Description, SupportsFileBatching, etc. qui ne sont pas affichés ici. L’ensemble des attributs applicables à une règle ou sur les autres éléments peut être obtenue en parcourant la documentation pour ces types. Ou bien, vous pouvez examiner les propriétés publiques sur les types dans les `Microsoft.Build.Framework.XamlTypes` espace de noms dans le `Microsoft.Build.Framework .dll` assembly.

   i. **DisplayName**, **PageTemplate**, et **commande** ne sont autres propriétés de l’interface utilisateur qui sont présentes dans ce modèle de données indépendant de l’interface utilisateur. Ces propriétés sont presque certaines utilisable par toute interface utilisateur qui est utilisé pour afficher les pages de propriétés. **DisplayName** et **Description** sont deux propriétés qui sont présents sur presque tous les éléments dans le fichier xml. Et ce sont les deux seules propriétés qui sont localisées (localisation de ces chaînes est expliquée dans une publication ultérieure).

2.  **Catégorie :** une règle peut avoir plusieurs catégories. L’ordre dans lequel les catégories sont répertoriées dans le fichier xml est une suggestion à l’interface utilisateur pour afficher les catégories dans le même ordre. Par exemple, l’ordre des catégories sous le nœud C/C++, comme indiqué dans l’interface utilisateur – général, l’optimisation, le préprocesseur,...  – est identique à ce cl.xml dans. Une catégorie exemple ressemble à ceci :

```xml  
 <Category Name="Optimization">
    <Category.DisplayName>
        <sys:String>Optimization</sys:String>
    </Category.DisplayName>
 </Category>
```
Le montre l’extrait de code ci-dessus le **nom** et **DisplayName** les attributs qui ont été décrit précédemment. Une fois encore, il existe des autres attributs un **catégorie** peut avoir qui ne sont pas utilisés ci-dessus. Vous pouvez savoir à leur sujet en lisant la documentation ou en consultant les assemblys en utilisant ildasm.exe.

3. **Propriétés :** cela correspond à l’essentiel du fichier xml et contient la liste de toutes les propriétés de cette règle. Chaque propriété peut être un des cinq types possibles indiqués dans le squelette XAML ci-dessus. Bien sûr, vous pourriez avoir que quelques exemples de ces types dans votre fichier. Une propriété a un nombre d’attributs qui lui permettent d’être décrit améliorées. Je vais expliquer seulement le **StringProperty** ici. Les autres sont très similaires.

```xml  
<StringProperty Subtype="file" Name="ObjectFileName" Category="Output Files" Switch="Fo">
  <StringProperty.DisplayName>
    <sys:String>Object File Name</sys:String>
  </StringProperty.DisplayName>
  <StringProperty.Description>
    <sys:String>Specifies a name to override the default object file name; can be file or directory name.(/Fo[name])</sys:String>
  </StringProperty.Description>
</StringProperty>
```
La plupart des attributs dans l’extrait de code a été décrit précédemment. Les nouveaux sont sous-type, catégorie et un commutateur.

   a. **Sous-type** n’est disponible uniquement pour un attribut **StringProperty** et **StringListProperty**; il donne des informations contextuelles. Par exemple, la valeur de « fichier » indique que la propriété représente un chemin d’accès de fichier. Ces informations contextuelles sont utilisées pour améliorer l’expérience d’édition en fournissant un Explorateur Windows en tant qu’éditeur de la propriété qui permet à l’utilisateur de choisir le fichier visuellement.

   b. **Catégorie :** cela déclare la catégorie sous laquelle cette propriété se situe. Essayez de trouver cette propriété sous la **fichiers de sortie** catégorie dans l’interface utilisateur.

   c. **Commutateur :** quand une règle représente un outil, tels que l’outil du compilateur dans ce cas, la plupart des propriétés de la règle sont passés en tant que les commutateurs à l’outil exécutable au moment de la build. La valeur de cet attribut indique le commutateur littéral à utiliser. La propriété ci-dessus spécifie que le commutateur doit être **Fo**. Combiné avec le **SwitchPrefix** attribut sur la règle, cette propriété parent est passé à l’exécutable en tant que **/Fo « déboguer\"**  (visible dans la ligne de commande pour C/C++ dans la page Propriétés de l’interface utilisateur).

   Autres attributs de propriété sont les suivantes :

   d. **Visible :** si pour une raison quelconque, vous ne souhaitez pas votre propriété apparaissent dans les pages de propriétés (mais probablement toujours disponible au moment de la build), cet attribut la valeur false.

   e. **En lecture seule :** si vous souhaitez fournir une vue en lecture seule de la valeur de cette propriété dans les pages de propriétés, définissez cet attribut sur true.

   f. **IncludeInCommandLine :** certaines propriétés n’ayez pas besoin d’être passées à un outil au moment de la build. Si cet attribut a pour valeur false empêche il passé.


