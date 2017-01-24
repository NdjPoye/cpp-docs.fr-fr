---
title: "Comment&#160;: ajouter une &#233;tape de g&#233;n&#233;ration personnalis&#233;e &#224; des projets MSBuild | Microsoft Docs"
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
  - "msbuild.cpp.howto.addcustombuildstep"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSBuild (C++), comment : ajouter une étape de génération personnalisée"
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Comment&#160;: ajouter une &#233;tape de g&#233;n&#233;ration personnalis&#233;e &#224; des projets MSBuild
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une étape de génération personnalisée est une étape définie par l'utilisateur dans une génération.  Une étape de génération personnalisée se comporte comme toute autre étape d'*outil de commande*, telle que l'étape de compilation standard ou l'étape de l'outil de liaison.  
  
 Spécifiez une étape de génération personnalisée dans le fichier projet \(.vcxproj\).  L'étape peut spécifier une ligne de commande à exécuter, n'importe quel fichier d'entrée ou de sortie supplémentaire et un message à afficher.  Si **MSBuild** détermine que vos fichiers de sortie sont obsolètes par rapport à vos fichiers d'entrée, il affiche le message et exécute la commande.  
  
 Pour spécifier l'emplacement de l'étape de génération personnalisée dans la séquence des cibles de génération, utilisez un ou les deux éléments XML `CustomBuildBeforeTargets` et `CustomBuildAfterTargets` dans le fichier projet.  Par exemple, vous pourriez spécifier que l'étape de génération personnalisée s'exécute après la cible de l'outil de liaison et avant la cible de l'outil Manifeste.  Le jeu réel de cibles disponibles dépend de votre génération particulière.  
  
 Spécifiez l'élément `CustomBuildBeforeTargets` pour exécuter l'étape de génération personnalisée avant l'exécution d'une cible particulière, l'élément `CustomBuildAfterTargets` pour exécuter l'étape après l'exécution d'une cible particulière, ou les deux éléments pour exécuter l'étape entre deux cibles adjacentes.  Si aucun élément n'est spécifié, votre outil de génération personnalisée s'exécute à son emplacement par défaut, qui se trouve après la cible **Link**.  
  
 Les étapes et les outils de génération personnalisée partagent les informations spécifiées dans les éléments XML `CustomBuildAfterTargets` et `CustomBuildBeforeTargets`.  Par conséquent, ne spécifiez ces cibles qu'une seule fois dans votre fichier projet.  
  
### Pour définir ce qui est exécuté par l'étape de génération personnalisée  
  
1.  Ajoutez un groupe de propriétés au fichier de projet.  Dans ce groupe de propriétés, spécifiez la commande, ses entrées et sorties et un message, comme indiqué dans l'exemple suivant.  Cet exemple crée un fichier .cab à partir du fichier main.cpp que vous avez créé dans [Procédure pas à pas : utilisation de MSBuild pour créer un projet Visual C\+\+](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md).  
  
    ```  
    <ItemDefinitionGroup>  
      <CustomBuildStep>  
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>  
        <Outputs>$(TargetName).cab</Outputs>  
        <Inputs>$(TargetFileName)</Inputs>  
      </CustomBuildStep>  
    </ItemDefinitionGroup>  
    ```  
  
### Pour définir l'emplacement dans lequel l'étape de génération personnalisée s'exécutera dans la génération  
  
1.  Ajoutez le groupe de propriétés suivant au fichier projet.  Vous pouvez spécifier les deux cibles, ou vous pouvez en omettre une si vous souhaitez simplement que l'étape personnalisée s'exécute avant ou après une cible particulière.  Cet exemple indique à **MSBuild** d'exécuter l'étape personnalisée après l'étape de compilation mais avant l'étape de liaison.  
  
    ```  
    <PropertyGroup>  
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>  
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>  
    </PropertyGroup>  
    ```  
  
## Voir aussi  
 [Procédure pas à pas : utilisation de MSBuild pour créer un projet Visual C\+\+](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)   
 [Comment : utiliser des événements de build dans des projets MSBuild](../build/how-to-use-build-events-in-msbuild-projects.md)   
 [Comment : ajouter des outils de génération personnalisée à des projets MSBuild](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)