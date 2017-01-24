---
title: "/Qimprecise_fwaits (Remove fwaits Inside Try Blocks) | Microsoft Docs"
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
  - "/Qimprecise_fwaits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Qimprecise_fwaits (option du compilateur C++)"
  - "-Qimprecise_fwaits (option du compilateur C++)"
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Qimprecise_fwaits (Remove fwaits Inside Try Blocks)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Supprime les commandes internes `fwait` des blocs `try` lors de l'utilisation de l'option du compilateur [\/fp:except](../../build/reference/fp-specify-floating-point-behavior.md).  
  
## Syntaxe  
  
```  
/Qimprecise_fwaits  
```  
  
## Notes  
 Cette option n'a aucun effet si **\/fp:except** n'est pas également spécifié.  Si vous spécifiez l'option **\/fp:except**, le compilateur insère une commande `fwait` autour de chaque ligne de code d'un bloc `try`.  De cette façon, le compilateur peut identifier la ligne spécifique de code qui produit une exception.  **\/Qimprecise\_fwaits** supprime les instructions `fwait` internes et ne conserve que les attentes autour du bloc `try`.  Cela permet d'améliorer les performances, mais le compilateur peut indiquer uniquement le bloc `try` qui génère une exception et non pas la ligne.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [\/Q \(Opérations de bas niveau\), options](../../build/reference/q-options-low-level-operations.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)