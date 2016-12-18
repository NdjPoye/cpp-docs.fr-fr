---
title: "/LIBPATH (Autre chemin de biblioth&#232;que) | Microsoft Docs"
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
  - "/libpath"
  - "VC.Project.VCLinkerTool.AdditionalLibraryDirectories"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LIBPATH (option de l'éditeur de liens)"
  - "Additional Libpath (option de l'éditeur de liens)"
  - "substitution du chemin d'accès de la bibliothèque d'environnement"
  - "LIBPATH (option de l'éditeur de liens)"
  - "-LIBPATH (option de l'éditeur de liens)"
  - "chemin de bibliothèque (option de l'éditeur de liens)"
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /LIBPATH (Autre chemin de biblioth&#232;que)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LIBPATH:dir  
```  
  
## Notes  
 où :  
  
 `dir`  
 désigne un chemin d'accès que l'éditeur de liens va rechercher avant de rechercher le chemin spécifié dans l'option d'environnement LIB.  
  
## Notes  
 Utilisez l'option \/LIBPATH pour substituer le chemin d'accès de la bibliothèque d'environnement.  L'éditeur de liens recherche d'abord dans le chemin d'accès spécifié par cette option, puis dans le chemin d'accès spécifié dans la variable d'environnement LIB.  Vous ne pouvez spécifier qu'un seul répertoire pour chaque option \/LIBPATH entrée.  Si vous souhaitez spécifier plusieurs répertoires, vous devez spécifier plusieurs options \/LIBPATH.  L'éditeur de liens recherche alors les répertoires spécifiés dans l'ordre.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Général**.  
  
4.  Modifiez la propriété **Répertoires de bibliothèques supplémentaires.**  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)