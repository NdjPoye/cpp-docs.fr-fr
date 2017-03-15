---
title: "/bigobj (Augmenter le nombre de sections dans le fichier .obj) | Microsoft Docs"
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
  - "/bigobj"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/bigobj (option du compilateur C++)"
  - "bigobj (option du compilateur C++)"
  - "-bigobj (option du compilateur C++)"
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /bigobj (Augmenter le nombre de sections dans le fichier .obj)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/bigobj** augmente le nombre des sections qu'un fichier objet peut contenir.  
  
## Syntaxe  
  
```  
/bigobj  
```  
  
## Notes  
 Par défaut, un fichier objet peut contenir jusqu'à 65 536 \(2^16\) sections adressables.  C'est le cas quelque soit la plateforme cible spécifiée.  **\/bigobj** augmente cette capacité d'adressage jusqu'à 4 294 967 296 \(2^32\).  
  
 La plupart des modules ne génèrent jamais de fichier .obj contenant plus de 65 536 sections.  Toutefois,le code généré par l'ordinateur ou le code qui utilise intensivement les bibliothèques de modèles peuvent exiger des fichiers .obj pouvant contenir davantage de sections.  **\/bigobj** est activé par défaut dans les projets Windows Store car le code XAML produit par la machine inclut un grand nombre d'en\-têtes.  Si vous désactivez cette option sur un projet d'application du Windows Store vous êtes susceptible de rencontrer l'erreur C1128 du compilateur.  
  
 Les éditeurs de liens qui étaient disponibles avant Visual C\+\+ 2005 ne peuvent pas lire les fichiers .obj produits avec **\/bigobj**.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)