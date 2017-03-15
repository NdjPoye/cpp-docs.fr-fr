---
title: "/O (Optimiser le code), options | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.Optimization"
  - "/o"
  - "VC.Project.VCCLWCECompilerTool.Optimization"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compilateur cl.exe, performances"
  - "performances, cle.exe (compilateur)"
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /O (Optimiser le code), options
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les options **\/O** gèrent diverses optimisations qui vous aident à créer du code pour obtenir une vitesse maximale ou une taille minimale.  
  
-   [\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) optimise le code pour une taille minimale.  
  
-   [\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md) optimise le code pour une vitesse maximale.  
  
-   [\/Ob](../../build/reference/ob-inline-function-expansion.md) commande l'expansion des fonctions inline.  
  
-   [\/Od](../../build/reference/od-disable-debug.md) désactive l'optimisation, en accélérant la compilation et en simplifiant le débogage.  
  
-   [\/Og](../../build/reference/og-global-optimizations.md) active les optimisations globales.  
  
-   [\/Oi](../../build/reference/oi-generate-intrinsic-functions.md) génère des fonctions intrinsèques pour des appels de fonction appropriés.  
  
-   [\/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) indique au compilateur de favoriser les optimisations de taille par rapport aux optimisations de vitesse.  
  
-   [\/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) \(paramètre par défaut\) indique au compilateur de favoriser les optimisations de vitesse par rapport aux optimisations de taille.  
  
-   [\/Ox](../../build/reference/ox-full-optimization.md) sélectionne l'optimisation complète.  
  
-   [\/Oy](../../build/reference/oy-frame-pointer-omission.md) supprime la création de pointeurs de frame sur la pile des appels pour des appels de fonction plus rapides.  
  
## Remarques  
 Vous pouvez également combiner plusieurs options **\/O** en une seule instruction d'option.  Par exemple, `/Odi` est identique à `/Od /Oi`.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)