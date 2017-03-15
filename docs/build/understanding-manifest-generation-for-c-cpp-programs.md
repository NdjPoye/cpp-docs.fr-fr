---
title: "Fonctionnement de la g&#233;n&#233;ration de manifestes pour les programmes&#160;C/C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "manifestes (C++)"
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
caps.latest.revision: 12
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fonctionnement de la g&#233;n&#233;ration de manifestes pour les programmes&#160;C/C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un [manifeste](http://msdn.microsoft.com/library/aa375365) est un document XML qui peut être un fichier XML externe ou une ressource incorporée dans une application ou un assembly.  Le manifeste d'une [application isolée](http://msdn.microsoft.com/library/aa375190) sert à gérer les noms et les versions des assemblys côte à côte partagés auxquels l'application doit être liée au moment de l'exécution.  Le manifeste d'un [assembly côte à côte](_win32_side_by_side_assemblies) spécifie ses dépendances vis\-à\-vis des noms, des versions, des ressources et des autres assemblys.  
  
 Il existe deux façons de créer un manifeste pour une application isolée ou un assembly côte à côte.  Tout d'abord, l'auteur de l'assembly peut créer manuellement un fichier manifeste conforme aux règles et aux obligations de dénomination.  En outre, si un programme dépend uniquement d'assemblys [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] tels que CRT, MFC, ATL, etc., un manifeste peut alors être généré automatiquement par l'éditeur de liens.  
  
 Les en\-têtes de bibliothèques [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] contiennent des informations sur les assemblys et, lorsque les bibliothèques sont incluses dans le code d'application, ces informations sont utilisées par l'éditeur de liens pour former un manifeste pour le fichier binaire final.  L'éditeur de liens n'incorpore pas le fichier manifeste au fichier binaire et ne peut générer le manifeste que sous forme de fichier externe.  Un manifeste sous forme de fichier externe peut ne pas être utilisé dans tous les scénarios.  Par exemple, il est recommandé que les assemblys privés aient des manifestes incorporés.  Dans les générations de ligne de commande telles que celles qu'utilise nmake pour générer du code, un manifeste peut être incorporé à l'aide de l'outil de manifeste ; pour plus d'informations, consultez [Génération de manifeste au niveau de la ligne de commande](../build/manifest-generation-at-the-command-line.md).  Lors d'une construction dans [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], il est possible d'incorporer un manifeste en définissant une propriété de l'outil de manifeste dans la boîte de dialogue **Propriétés du projet** ; consultez [Génération de manifeste dans Visual Studio](../build/manifest-generation-in-visual-studio.md).  
  
## Voir aussi  
 [Concepts d'applications isolées et d'assemblys côte à côte](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [Génération d'applications isolées C\/C\+\+ et d'assemblys côte à côte](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)