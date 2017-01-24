---
title: "/FORCE (Forcer la sortie d&#39;un fichier) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.ForceLink"
  - "/force"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FORCE (option de l'éditeur de liens)"
  - "sortie de fichier dans l'éditeur de liens"
  - "FORCE (option de l'éditeur de liens)"
  - "-FORCE (option de l'éditeur de liens)"
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FORCE (Forcer la sortie d&#39;un fichier)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/FORCE:[MULTIPLE|UNRESOLVED]  
```  
  
## Notes  
 L'option \/FORCE indique à l'éditeur de liens de créer un fichier .exe ou une DLL valide, même si un symbole est référencé, mais non défini ou s'il est défini plusieurs fois.  
  
 Cette option peut prendre un argument facultatif :  
  
-   L'option \/FORCE:MULTIPLE crée un fichier de sortie même si LINK trouve plusieurs définitions pour un symbole.  
  
-   L'option \/FORCE:UNRESOLVED crée un fichier de sortie même si LINK trouve un symbole non défini. \/FORCE:UNRESOLVED est ignorée si le symbole de point d'entrée n'est pas résolu.  
  
 L'option \/FORCE sans argument prend en compte les symboles multiples et non résolus.  
  
 Un fichier créé avec cette option peut ne pas s'exécuter comme prévu.  L'éditeur de liens ne fera pas de liaison incrémentielle lorsque l'option \/FORCE est spécifiée.  
  
 Si un module est compilé avec **\/clr**, **\/FORCE** ne crée pas d'image.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Tapez l'option dans la zone **Options supplémentaires**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)