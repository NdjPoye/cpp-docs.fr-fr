---
title: "/FUNCTIONPADMIN (Cr&#233;ation d&#39;une image corrigeable en m&#233;moire) | Microsoft Docs"
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
  - "/functionpadmin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FUNCTIONPADMIN (option de l'éditeur de liens)"
  - "-FUNCTIONPADMIN (option de l'éditeur de liens)"
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FUNCTIONPADMIN (Cr&#233;ation d&#39;une image corrigeable en m&#233;moire)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prépare une image corrigeable en mémoire.  
  
## Syntaxe  
  
```  
/FUNCTIONPADMIN[:space]  
```  
  
## Notes  
 où,  
  
 `space` \(facultatif\)  
 La quantité de remplissage à ajouter au début de chaque fonction, 5, 6 ou 16. Les images x86 requièrent cinq octets de remplissage, les images x64 requièrent 6 octets, et les images créées pour la famille de processeurs Itanium requièrent 16 octets de remplissage au début de chaque fonction.  
  
 Par défaut, le compilateur ajoute la quantité d'espace correcte à l'image, selon le type d'ordinateur de celle\-ci.  
  
 Pour que l'éditeur de liens produise une image corrigeable en mémoire, les fichiers .obj doivent avoir été compilés avec [\/hotpatch \(Créer une image corrigeable en mémoire\)](../../build/reference/hotpatch-create-hotpatchable-image.md).  
  
 Lorsque vous compilez et liez une image à l'aide d'un appel unique de cl.exe, **\/hotpatch** implique **\/functionpadmin**.  
  
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