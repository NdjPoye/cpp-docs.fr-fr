---
title: "Comment&#160;: utiliser des &#233;v&#233;nements de build dans des projets MSBuild | Microsoft Docs"
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
  - "msbuild.cpp.howto.usebuildevents"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSBuild (C++), comment : utiliser des événements de build dans des projets"
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Comment&#160;: utiliser des &#233;v&#233;nements de build dans des projets MSBuild
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un événement de build est une commande exécutée par [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] à une étape particulière dans le processus de génération.  L'évènement *avant génération* se produit avant que la génération démarre ; l'évènement *avant l'édition de liens* se produit avant le démarrage de l'étape de lien ; et l'évènement *après génération* se produit une fois la construction exécutée avec succès.  Un événement de build se produit uniquement si l'étape de génération associée se produit.  Par exemple, l'événement avant l'édition des liens ne se produit pas si l'étape de liaison ne s'exécute pas.  
  
 Chacun des trois événements de build est représenté dans un groupe de définitions d'éléments par un élément de commande \(`<Command>`\) exécuté et un élément de message \(`<Message>`\) affiché lorsque **MSBuild** exécute l'événement de build.  Chaque élément est facultatif, et si vous spécifiez le même élément plusieurs fois, la dernière occurrence est prioritaire.  
  
 Un élément *utilisation dans la génération* facultatif \(`<`*build\-event***UseInBuild**`>`\)\) peut être spécifié dans un groupe de propriétés pour indiquer si l'événement de build est exécuté.  La valeur du contenu d'un élément *utilisation dans la génération* est `true` ou `false`.  Par défaut, un événement de build est exécuté à moins que son élément *utilisation dans la génération* correspondant n'ait la valeur `false`.  
  
 Le tableau suivant répertorie chaque élément XML d'événement de build :  
  
|XML \(élément\)|Description|  
|---------------------|-----------------|  
|`PreBuildEvent`|Cet événement s'exécute avant que la génération ne commence.|  
|`PreLinkEvent`|Cet événement s'exécute avant que l'étape de liaison ne commence.|  
|`PostBuildEvent`|Cet événement s'exécute une fois la génération terminée.|  
  
 Le tableau suivant répertorie chaque élément *utilisation dans la génération* :  
  
|XML \(élément\)|Description|  
|---------------------|-----------------|  
|`PreBuildEventUseInBuild`|Spécifie s'il faut exécuter l'événement *pré\-build*.|  
|`PreLinkEventUseInBuild`|Spécifie s'il faut exécuter l'événement *avant l'édition des liens*.|  
|`PostBuildEventUseInBuild`|Spécifie s'il faut exécuter l'événement *post\-build*.|  
  
## Exemple  
 L'exemple suivant peut être ajouté dans l'élément de projet du fichier myproject.vcxproj créé dans [Procédure pas à pas : utilisation de MSBuild pour créer un projet Visual C\+\+](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md).  Un événement *pré\-build* effectue une copie de main.cpp, un événement *avant l'édition des liens* effectue une copie de main.obj et un événement *post\-build* effectue une copie de myproject.exe.  Si le projet est généré à l'aide d'une configuration Release, les événements de build sont exécutés.  Si le projet est généré à l'aide d'une configuration Debug, les événements de build ne sont pas exécutés.  
  
```  
<ItemDefinitionGroup>  
  <PreBuildEvent>  
    <Command>copy $(ProjectDir)main.cpp $(ProjectDir)copyOfMain.cpp</Command>  
    <Message>Making a copy of main.cpp </Message>  
  </PreBuildEvent>  
  <PreLinkEvent>  
 <Command>copy $(ProjectDir)$(Configuration)\main.obj $(ProjectDir)$(Configuration)\copyOfMain.obj</Command>  
    <Message>Making a copy of main.obj</Message>  
  </PreLinkEvent>  
  <PostBuildEvent>  
 <Command>copy $(ProjectDir)$(Configuration)\$(TargetFileName) $(ProjectDir)$(Configuration)\copyOfMyproject.exe</Command>  
    <Message>Making a copy of myproject.exe</Message>  
  </PostBuildEvent>  
</ItemDefinitionGroup>  
  
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">  
  <PreBuildEventUseInBuild>true</PreBuildEventUseInBuild>  
  <PreLinkEventUseInBuild>true</PreLinkEventUseInBuild>  
  <PostBuildEventUseInBuild>true</PostBuildEventUseInBuild>  
</PropertyGroup>  
  
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">  
  <PreBuildEventUseInBuild>false</PreBuildEventUseInBuild>  
  <PreLinkEventUseInBuild>false</PreLinkEventUseInBuild>  
  <PostBuildEventUseInBuild>false</PostBuildEventUseInBuild>  
</PropertyGroup>  
```  
  
## Voir aussi  
 [MSBuild \(Visual C\+\+\)](../build/msbuild-visual-cpp.md)   
 [Procédure pas à pas : utilisation de MSBuild pour créer un projet Visual C\+\+](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)