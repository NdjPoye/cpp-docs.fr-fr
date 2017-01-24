---
title: "/MANIFESTFILE (Nommer le fichier manifeste) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.ManifestFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFESTFILE (option de l'éditeur de liens)"
  - "MANIFESTFILE (option de l'éditeur de liens)"
  - "-MANIFESTFILE (option de l'éditeur de liens)"
ms.assetid: befa5ab2-a9cf-4c9b-969a-e7b4a930f08d
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /MANIFESTFILE (Nommer le fichier manifeste)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MANIFESTFILE:filename  
```  
  
## Notes  
 \/MANIFESTFILE permet de modifier le nom par défaut du fichier manifeste.  Le nom par défaut du fichier manifeste est le nom du fichier avec l'extension .manifest ajoutée.  
  
 \/MANIFESTFILE n'a aucun effet si vous ne liez pas également avec [\/MANIFEST](../../build/reference/manifest-create-side-by-side-assembly-manifest.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **Éditeur de liens**.  
  
4.  Sélectionnez la page de propriétés **Fichier manifeste**.  
  
5.  Modifiez la propriété **Fichier manifeste**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ManifestFile%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)