---
title: "/Qpar (parall&#233;liseur automatique) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration"
dev_langs: 
  - "C++"
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /Qpar (parall&#233;liseur automatique)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Active la fonctionnalité [AUTO\-Parallelizer](../../parallel/auto-parallelization-and-auto-vectorization.md) du compilateur pour paralléliser automatiquement des boucles dans votre code.  
  
## Syntaxe  
  
```  
/Qpar  
```  
  
## Notes  
 Lorsque le compilateur parallélise automatiquement des boucles dans le code, il répartit le calcul à travers plusieurs noyaux du processeur.  Une boucle est parallélisée uniquement si le compilateur détermine qu'il est légal de procéder ainsi et que la parallélisation améliorerait les performances.  
  
 Les directives de `#pragma loop()` sont disponibles pour aider l'optimiseur à paralléliser des boucles spécifiques.  Pour plus d'informations, consultez [boucle](../../preprocessor/loop.md).  
  
 Pour plus d'informations sur l'activation des messages de sortie pour auto\-parallelizer, consultez [\/Qpar\-report \(Niveau de rapport du paralléliseur automatique\)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md).  
  
### Pour définir l'option \/Qpar de compilateur dans Visual Studio  
  
1.  Dans l'**Explorateur de solutions**, ouvrez le menu contextuel du projet et choisissez **Propriétés**.  
  
2.  Dans la boîte de dialogue **Pages de propriétés**, sous **C\/C\+\+**, sélectionnez **Ligne de commande**.  
  
3.  Dans la zone **Options supplémentaires**, entrez `/Qpar`.  
  
### Pour définir l'option \/Qpar du compilateur par programmation  
  
-   Utilisez l'exemple de code dans <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [\/Q \(Opérations de bas niveau\), options](../../build/reference/q-options-low-level-operations.md)   
 [\/Qpar\-report \(Niveau de rapport du paralléliseur automatique\)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [\#pragma loop\(\)](../../preprocessor/loop.md)   
 [Programmation parallèle en code natif](http://go.microsoft.com/fwlink/?LinkId=263662)