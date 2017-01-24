---
title: "Comment&#160;: ajouter des outils de g&#233;n&#233;ration personnalis&#233;e &#224; des projets MSBuild | Microsoft Docs"
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
  - "msbuild.cpp.howto.addcustombuildtools"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSBuild (C++), comment : ajouter des outils de génération personnalisée"
ms.assetid: de03899a-371d-4396-9bf9-34f45a65e909
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Comment&#160;: ajouter des outils de g&#233;n&#233;ration personnalis&#233;e &#224; des projets MSBuild
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un outil de génération personnalisée est un outil en ligne de commande défini par l'utilisateur, associé à un fichier particulier.  
  
 Pour un fichier particulier, spécifiez, dans le fichier projet \(.vcxproj\), la ligne de commande à exécuter, tout fichier d'entrée ou de sortie supplémentaire et un message à afficher.  Si **MSBuild** détermine que vos fichiers de sortie sont obsolètes par rapport à vos fichiers d'entrée, il affiche le message et exécute l'outil en ligne de commande.  
  
 Pour spécifier à quel moment l'outil de génération personnalisée doit s'exécuter, utilisez un ou les deux éléments XML `CustomBuildAfterTargets` et `CustomBuildBeforeTargets` dans le fichier projet.  Par exemple, vous pouvez spécifier que votre outil de génération personnalisée s'exécute après le compilateur MIDL et avant le compilateur C\/C\+\+.  Spécifiez l'élément `CustomBuildBeforeTargets` pour exécuter l'outil avant l'exécution d'une cible particulière, l'élément `CustomBuildAfterTargets` pour exécuter l'outil après une cible particulière ou les deux éléments pour exécuter l'outil entre l'exécution de deux cibles.  Si aucun élément n'est spécifié, votre outil de génération personnalisée s'exécute à son emplacement par défaut, qui se trouve avant la cible **MIDL**.  
  
 Les étapes et les outils de génération personnalisée partagent les informations spécifiées dans les éléments XML `CustomBuildAfterTargets` et `CustomBuildBeforeTargets`.  Spécifiez ces cibles une fois dans votre fichier projet.  
  
### Pour ajouter un outil de génération personnalisée  
  
1.  Ajoutez un groupe d'éléments au fichier projet et ajoutez un élément pour chaque fichier d'entrée.  Spécifiez la commande, les entrées et sorties supplémentaires, et un message comme métadonnées d'élément, comme indiqué ici.  Cet exemple suppose qu'il existe un fichier "faq.txt" dans le même répertoire que celui de votre projet.  
  
    ```  
    <ItemGroup>  
      <CustomBuild Include="faq.txt">  
        <Message>Copying readme...</Message>  
        <Command>copy %(Identity) $(OutDir)%(Identity)</Command>  
        <Outputs>$(OutDir)%(Identity)</Outputs>  
      </CustomBuild>  
    </ItemGroup>  
    ```  
  
### Pour définir l'emplacement dans lequel les outils de génération personnalisée s'exécuteront dans la génération  
  
1.  Ajoutez le groupe de propriétés suivant au fichier projet.  Vous devez spécifier au moins l'une des cibles, mais vous pouvez omettre l'autre si vous souhaitez uniquement que votre étape de génération s'exécute avant \(ou après\) une cible particulière.  Cet exemple exécute l'étape personnalisée après la compilation mais avant la liaison.  
  
    ```  
    <PropertyGroup>  
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>  
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>  
    </PropertyGroup>  
    ```  
  
## Voir aussi  
 [Procédure pas à pas : utilisation de MSBuild pour créer un projet Visual C\+\+](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)   
 [Comment : utiliser des événements de build dans des projets MSBuild](../build/how-to-use-build-events-in-msbuild-projects.md)   
 [Comment : ajouter une étape de génération personnalisée à des projets MSBuild](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)