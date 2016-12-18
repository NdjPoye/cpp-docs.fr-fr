---
title: "/DEF (Sp&#233;cifier le fichier de d&#233;finition de module) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.ModuleDefinitionFile"
  - "/def"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DEF (option de l'éditeur de liens)"
  - "DEF (option de l'éditeur de liens)"
  - "-DEF (option de l'éditeur de liens)"
  - "fichiers de définition de module"
  - "fichiers de définition de module, spécifier"
ms.assetid: 6497fa68-65f0-48ca-8f66-b87166fc631a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DEF (Sp&#233;cifier le fichier de d&#233;finition de module)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DEF:filename  
```  
  
## Notes  
 où :  
  
 *filename*  
 désigne le nom d'un fichier de définition de module \(.def\) à passer à l'éditeur de liens.  
  
## Notes  
 L'option \/DEF passe un fichier de définition de module \(.def\) à l'Éditeur de liens.  Un seul fichier .def peut être passé à LINK.  Pour plus d'informations sur les fichiers .def, consultez [Fichiers de définition de module](../../build/reference/module-definition-dot-def-files.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Entrée**.  
  
4.  Modifiez la propriété **Fichier de définition de module.**  
  
 Pour spécifier un fichier .def dans l'environnement de développement, vous devez l'ajouter au projet parallèlement aux autres fichiers et spécifier le fichier à l'option \/DEF.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)