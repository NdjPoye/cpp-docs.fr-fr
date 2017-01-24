---
title: "/MAPINFO (Inclure des informations dans le fichier de mappage) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.MapLines"
  - "VC.Project.VCLinkerTool.MapInfoFixups"
  - "VC.Project.VCLinkerTool.MapExports"
  - "/mapinfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MAPINFO (option de l'éditeur de liens)"
  - "MAPINFO (option de l'éditeur de liens)"
  - "-MAPINFO (option de l'éditeur de liens)"
ms.assetid: 533d2bce-f9b7-4fea-ae1c-0b4864c9d10b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /MAPINFO (Inclure des informations dans le fichier de mappage)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MAPINFO:EXPORTS  
```  
  
## Notes  
 L'option \/MAPINFO indique à l'éditeur de liens d'inclure des informations spécifiées dans un fichier de mappage, créé si vous spécifiez l'option [\/MAP](../../build/reference/map-generate-mapfile.md).  EXPORTS indique à l'Éditeur de liens d'inclure les fonctions exportées.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Déboguer**.  
  
4.  Modifiez une des propriétés **Mappage des exportations** :  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapExports%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)