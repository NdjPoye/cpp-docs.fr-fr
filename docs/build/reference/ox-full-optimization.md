---
title: "/Ox (Optimisation compl&#232;te) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.ToolOptimization"
  - "/ox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Ox (option du compilateur C++)"
  - "code rapide"
  - "optimisation complète"
  - "Ox (option du compilateur C++)"
  - "-Ox (option du compilateur C++)"
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /Ox (Optimisation compl&#232;te)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'option du compilateur **\/Ox** génère du code qui favorise la vitesse d'exécution par rapport à la réduction de la taille du code.  
  
## Syntaxe  
  
```  
/Ox  
```  
  
## Notes  
 La spécification de l'option du compilateur **\/Ox** a le même effet que celui de l'utilisation des options suivantes :  
  
-   [\/Ob \(Expansion des fonctions Inline\)](../../build/reference/ob-inline-function-expansion.md), où l'option de paramètre est 2 \(**\/Ob2**\)  
  
-   [\/Og \(Optimisations globales\)](../../build/reference/og-global-optimizations.md)  
  
-   [\/Oi \(Générer des fonctions intrinsèques\)](../../build/reference/oi-generate-intrinsic-functions.md)  
  
-   [\/Ot \(Favoriser la vitesse du code\)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)  
  
-   [\/Oy \(Omission du pointeur frame\)](../../build/reference/oy-frame-pointer-omission.md)  
  
 **\/Ox** et les options ci\-dessous s'excluent mutuellement :  
  
-   [\/O1 \(Réduire la taille\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)  
  
-   [\/O2 \(Augmenter la vitesse\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)  
  
-   [\/Od \(Désactiver \(Débogage\)\)](../../build/reference/od-disable-debug.md)  
  
 L'option du compilateur **\/Ox** active également l'optimisation de valeur de retour nommée, qui élimine le constructeur de copie et le destructeur d'une valeur de retour basée sur la pile.  Pour plus d'informations, consultez [\/O1, \/O2 \(Réduire la taille, augmenter la vitesse\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md).  
  
 Vous pouvez annuler l'option du compilateur **\/Ox** si vous spécifiez **\/Oxs**, qui combine l'option du compilateur avec **\/Ox**[\/Os \(Favoriser la taille du code\)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md).  Les options combinées favorisent la réduction de la taille du code.  
  
 En général, spécifiez [\/O2 \(Augmenter la vitesse\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) au lieu de **\/Ox** et [\/O1 \(Réduire la taille\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) au lieu de **\/Oxs**.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Optimisation**.  
  
4.  Modifiez la propriété **Optimisation**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.  
  
## Voir aussi  
 [\/O \(Optimiser le code\), options](../../build/reference/o-options-optimize-code.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)