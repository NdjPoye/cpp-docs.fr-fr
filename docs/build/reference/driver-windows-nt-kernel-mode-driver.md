---
title: "/DRIVER (Pilote Windows&#160;NT en mode noyau) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.driver"
  - "/driver"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DRIVER (option de l'éditeur de liens)"
  - "DRIVER (option de l'éditeur de liens)"
  - "-DRIVER (option de l'éditeur de liens)"
  - "pilote en mode noyau"
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DRIVER (Pilote Windows&#160;NT en mode noyau)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DRIVER[:UPONLY | :WDM]  
```  
  
## Notes  
 L'option \/DRIVER de l'Éditeur de liens vous permet de générer un pilote en mode noyau Windows NT.  
  
 **\/DRIVER:UPONLY** force l'éditeur de liens à ajouter le bit **IMAGE\_FILE\_UP\_SYSTEM\_ONLY** aux caractéristiques figurant dans l'en\-tête de sortie pour spécifier qu'il s'agit d'un pilote uniprocesseur \(UP\).  Le système d'exploitation n'autorise pas le chargement d'un pilote monoprocesseur sur un système multiprocesseur.  
  
 **\/DRIVER:WDM** force l'éditeur de liens à définir le bit **IMAGE\_DLLCHARACTERISTICS\_WDM\_DRIVER** dans le champ DllCharacteristics facultatif de l'en\-tête.  
  
 Si **\/DRIVER** n'est pas spécifié, ces bits ne sont pas définis par l'éditeur de liens.  
  
 Si **\/DRIVER** est spécifié :  
  
-   \/FIXE:NO est appliqué \([\/FIXED \(Adresse de base fixe\)](../../build/reference/fixed-fixed-base-address.md)\).  
  
-   L'extension du fichier de sortie est .sys.  Utilisez **\/OUT** pour modifier le nom de fichier et l'extension par défaut \([\/OUT \(Nom du fichier de sortie\)](../../build/reference/out-output-file-name.md)\).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Système**.  
  
4.  Modifiez la propriété **Pilote**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez `P:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.driver`.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)