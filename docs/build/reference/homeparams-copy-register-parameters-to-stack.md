---
title: "/Homeparams (Copier les param&#232;tres des registres vers la pile) | Microsoft Docs"
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
  - "/homeparams"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/homeparams (option du compilateur C++)"
  - "-homeparams (option du compilateur C++)"
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Homeparams (Copier les param&#232;tres des registres vers la pile)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Force l'écriture des paramètres passés dans les registres vers leurs emplacements sur la pile lors de l'entrée de la fonction.  
  
## Syntaxe  
  
```  
/homeparams  
```  
  
## Notes  
 Cette option du compilateur est uniquement destinée aux compilateurs [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] \(compilation native et croisée\).  
  
 Lorsque les paramètres sont passés dans une compilation [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], les conventions d'appel requièrent un espace de pile pour les paramètres, même pour ceux qui sont passés dans les registres.  Pour plus d'informations, consultez [Passage de paramètres](../../build/parameter-passing.md).  Toutefois, dans une version release, il est convenu par défaut que les paramètres des registres ne sont pas écrits dans la pile, dans l'espace déjà fourni pour les paramètres.  Cela rend difficile le débogage d'une génération optimisée \(version release\) de votre programme.  
  
 Pour une version Release, utilisez **\/homeparams** afin d'être sûr de pouvoir déboguer votre application.  L'option **\/homeparams** présente un inconvénient en termes de performances étant donné qu'elle requiert un cycle pour le chargement des paramètres de registre sur la pile.  
  
 Dans une version debug, la pile est toujours remplie avec les paramètres passés dans les registres.  
  
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