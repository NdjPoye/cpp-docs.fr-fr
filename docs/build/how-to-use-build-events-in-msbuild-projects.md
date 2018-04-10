---
title: 'Comment : utiliser des événements de Build dans des projets MSBuild | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- msbuild.cpp.howto.usebuildevents
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cc8b3b21cdc9aad183f39bf709f93e022e790eef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>Comment : utiliser des événements de build dans des projets MSBuild
Un événement de build est une commande qui [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] exécute à un stade particulier dans le processus de génération. Le *pré-build* événement se produit avant le démarrage de la build ; le *avant lien* événement se produit avant le démarrage d’étape de liaison ; et le *post-build* événement se produit après la génération termine correctement. Un événement de build se produit uniquement si l’étape de génération associé se produit. Par exemple, l’événement avant lien n’a pas lieu si l’étape de liaison ne s’exécute pas.  
  
 Chacun des trois événements de build est représenté dans un groupe de définitions d’élément par un élément de commande (`<Command>`) qui est exécuté et un élément de message (`<Message>`) qui est affiché lorsque **MSBuild** exécute l’événement de build. Chaque élément est facultatif, et si vous spécifiez le même élément plusieurs fois, la dernière occurrence est prioritaire.  
  
 Facultatif *utilisation dans la génération* élément (`<`*événement de build***UseInBuild**`>`) peuvent être spécifiés dans un groupe de propriétés pour indiquer si le événement de build est exécuté. La valeur du contenu d’un *utilisation dans la génération* est le `true` ou `false`. Par défaut, un événement de build est exécuté, sauf si le correspondant *utilisation dans la génération* a la valeur `false`.  
  
 Le tableau suivant répertorie chaque élément XML d’événement de build :  
  
|Élément XML|Description|  
|-----------------|-----------------|  
|`PreBuildEvent`|Cet événement s’exécute avant le début de la build.|  
|`PreLinkEvent`|Cet événement s’exécute avant le début de l’étape de liaison.|  
|`PostBuildEvent`|Cet événement s’exécute une fois la build terminée.|  
  
 Le tableau suivant répertorie chaque *utilisation dans la génération* élément :  
  
|Élément XML|Description|  
|-----------------|-----------------|  
|`PreBuildEventUseInBuild`|Spécifie s’il faut exécuter le *pré-build* événement.|  
|`PreLinkEventUseInBuild`|Spécifie s’il faut exécuter le *avant* événements.|  
|`PostBuildEventUseInBuild`|Spécifie s’il faut exécuter le *post-build* événement.|  
  
## <a name="example"></a>Exemple  
 L’exemple suivant peut être ajouté à l’intérieur de l’élément de projet du fichier myproject.vcxproj créé dans [procédure pas à pas : utilisation de MSBuild pour créer un projet Visual C++](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md). A *pré-build* événement effectue une copie de main.cpp ; un *avant lien* événement effectue une copie de main.obj ; et un *post-build* événement effectue une copie de myproject.exe. Si le projet est généré à l’aide d’une configuration release, les événements de build sont exécutées. Si le projet est généré à l’aide d’une configuration debug, les événements de build ne sont pas exécutées.  
  
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
  
## <a name="see-also"></a>Voir aussi  
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)   
 [Procédure pas à pas : utilisation de MSBuild pour créer un projet Visual C++](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)