---
title: "Modifications du syst&#232;me de g&#233;n&#233;ration | Microsoft Docs"
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
  - "vc.msbuild.changes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "modifications du système de génération, $(Inherit)"
  - "modifications du système de génération, $(NoInherit)"
  - "modifications du système de génération, .vsprops"
  - "modifications du système de génération, règles de génération personnalisée"
  - "modifications du système de génération, MSBuild"
  - "modifications du système de génération, fichier projet (.vcxprog)"
  - "MSBuild, modifications du système de génération"
ms.assetid: e564d95f-a6cc-4d97-b57e-1a71daf66f4a
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Modifications du syst&#232;me de g&#233;n&#233;ration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le système MSBuild est utilisé pour générer les projets Visual C\+\+.  Toutefois, dans Visual Studio 2008 et ses versions antérieures, le système de VCBuild a été utilisé.  Certains types de fichiers et concepts qui dépendaient de VCBuild n'existent plus ou sont représentés différemment dans le système actuel.  Ce document présente les différences du système de génération actuel.  
  
## .vcproj est désormais .vcxproj  
 Les fichiers projet n'utilisent plus l'extension de nom de fichier .vcproj.  Visual Studio convertit automatiquement les fichiers projet créés avec une version antérieure de Visual C\+\+ au format utilisé par le système actuel.  Pour plus d'informations sur la mise à niveau manuelle d'un projet, consultez [\/Upgrade](../Topic/-Upgrade%20\(devenv.exe\).md).  
  
 Dans la version actuelle, l'extension de nom de fichier des fichiers projet est .vcxproj.  
  
## .vsprops est désormais .props  
 Dans les versions antérieures, une *feuille de propriétés de projet* est un fichier XML dont l'extension de nom de fichier est .vsprops.  Une feuille de propriétés de projet vous permet de spécifier des commutateurs pour les outils de génération tels que le compilateur ou l'éditeur de liens et de créer des macros définies par l'utilisateur.  
  
 Dans la version actuelle, l'extension de nom de fichier d'une feuille de propriété de projet est .props.  
  
## Règles de génération personnalisée et fichiers .rules  
 Dans les versions antérieures, un *fichier de règles* est un fichier XML dont l'extension de nom de fichier est .rules.  Un fichier de règles vous permet de définir des règles de génération personnalisée et de les incorporer au processus de génération d'un projet Visual C\+\+.  Une règle de génération personnalisée, qui peut être associée à une ou plusieurs extensions de nom de fichier, vous permet de passer des fichiers d'entrée à un outil qui crée un ou plusieurs fichiers de sortie.  
  
 Dans cette version, les règles de génération personnalisée sont représentées par trois types de fichier, à savoir .xml, .props et .targets, au lieu d'un fichier .rules.  Lorsqu'un fichier .rules créé à l'aide d'une version antérieure de Visual C\+\+ est migré vers la version actuelle, les fichiers .xml, .props et .targets correspondants sont créés et stockés dans votre projet avec le fichier .rules d'origine.  
  
> [!IMPORTANT]
>  Dans la version actuelle, le [!INCLUDE[TLA2#tla_ide](../build/includes/tla2sharptla_ide_md.md)] ne prend pas en charge la création de nouvelles règles.  Pour cette raison, la façon la plus simple d'utiliser un fichier de règle d'un projet créé à l'aide d'une version antérieure de Visual C\+\+ est de migrer le projet vers la version actuelle.  
  
## Macros d'héritage  
 Dans les versions antérieures, la macro **$\(Inherit\)** spécifie l'ordre dans lequel les propriétés héritées s'affichent sur la ligne de commande, qui est composée par le système de génération de projet.  Avec la macro **$\(NoInherit\)**, toutes les occurrences de $\(Inherit\) sont ignorées et toutes les propriétés devant être héritées ne sont pas héritées.  Par exemple, la macro $\(Inherit\) entraîne par défaut l'ajout des fichiers spécifiés à l'aide de l'option du compilateur [\/I \(Autres répertoires Include\)](../build/reference/i-additional-include-directories.md) à la ligne de commande.  
  
 Dans la version actuelle, l'héritage est pris en charge en spécifiant la valeur d'une propriété sous la forme d'une concaténation d'une ou plusieurs valeurs littérales et macros de propriété.  Les macros **$\(Inherit\)** et **$\(NoInherit\)** ne sont pas prises en charge.  
  
 Dans l'exemple suivant, une liste délimitée par des points\-virgules est assignée à une propriété dans une page de propriétés.  La liste se compose de la concaténation du littéral *\<value\>* et de la valeur de la propriété `MyProperty`, accessible à l'aide de la notation macro **$\(***MyProperty***\)**.  
  
```  
Property=<value>;$(MyProperty)  
```  
  
## Fichiers .vcxproj.user  
 Par exemple, un fichier utilisateur \(.vcxproj.user\) stocke des propriétés spécifiques à l'utilisateur telles que les paramètres de débogage et de déploiement.  Le fichier vcxproj.user s'applique à tous les projets d'un utilisateur particulier.  
  
## Fichier .vcxproj.filters  
 Lorsque l'**Explorateur de solutions** est utilisé pour ajouter un fichier à un projet, le fichier de filtre \(.vcxproj.filters\) définit l'emplacement auquel le fichier est ajouté dans l'arborescence **Explorateur de solutions**, en fonction de son extension de nom de fichier.  
  
## Paramètres de répertoires VC\+\+  
 Les paramètres de répertoires Visual C\+\+ sont spécifiés dans la [Page de propriétés Répertoires VC\+\+](../ide/vcpp-directories-property-page.md).  Dans les versions antérieures de Visual Studio, les paramètres de répertoires s'appliquent par utilisateur et la liste de répertoires exclus est spécifiée dans le fichier sysincl.dat.  
  
 Vous ne pouvez pas modifier les paramètres de répertoires VC\+\+ si vous exécutez [devenv \/resetsettings](../Topic/-ResetSettings%20\(devenv.exe\).md) à la ligne de commande.  De la même façon, il n'est pas possible de modifier les paramètres lorsque vous ouvrez le menu **Outils**, cliquez sur **Importation et exportation de paramètres**, puis sélectionnez l'option **Réinitialiser tous les paramètres**.  
  
 Migrez les paramètres de répertoires VC\+\+ à partir d'un fichier .vssettings créé dans une version antérieure de Visual C\+\+.  Ouvrez le menu **Outils**, cliquez sur **Importation et exportation de paramètres**, sélectionnez **Importer les paramètres d'environnement sélectionnés**, puis suivez les instructions de l'Assistant.  Ou, lorsque vous démarrez Visual Studio pour la première fois, dans la boîte de dialogue **Choisir les paramètres d'environnement par défaut**, sélectionnez **Migrer mes paramètres éligibles depuis une version précédente et les ajouter aux paramètres par défaut sélectionnés ci\-dessous**.  
  
## Voir aussi  
 [MSBuild \(Visual C\+\+\)](../build/msbuild-visual-cpp.md)