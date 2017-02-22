---
title: "/Oy (Omission du pointeur frame) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.OmitFramePointers"
  - "/oy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Oy (option du compilateur C++)"
  - "omission du pointeur frame (option du compilateur C++)"
  - "omission du pointeur frame"
  - "Oy (option du compilateur C++)"
  - "-Oy (option du compilateur C++)"
  - "pointeur de frame de pile (option du compilateur C++)"
  - "supprimer la création du pointeur frame"
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# /Oy (Omission du pointeur frame)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Empêche la création des pointeurs de frame sur la pile des appels.  
  
## Syntaxe  
  
```  
/Oy[-]  
```  
  
## Notes  
 Cette option accélère les appels de fonction, dans la mesure où aucun pointeur de frame n'a besoin d'être installé, puis supprimé.  Elle libère également un registre supplémentaire \(EBP sur l'architecture Intel 386 ou version ultérieure\) pour le stockage des variables et sous\-expressions fréquemment utilisées.  
  
 **\/Oy** active l'omission du pointeur de frame et **\/Oy\-** désactive l'omission. **\/Oy** n'est disponible que dans les compilateurs x86.  
  
 Si votre code requiert un adressage EBP, vous pouvez spécifier l'option **\/Oy–** après l'option **\/Ox**, ou utiliser [optimize](../../preprocessor/optimize.md) avec les arguments « **y** » et **off** pour obtenir une optimisation maximale en matière d'adressage EBP.  Le compilateur détecte la plupart des situations où l'adressage EBP est requis \(par exemple, avec les fonctions `_alloca` et `setjmp`, ainsi qu'avec la gestion des exceptions structurées\).  
  
 Les options [\/Ox \(Optimisation complète\)](../../build/reference/ox-full-optimization.md) et [\/O1, \/O2 \(Réduire la taille, augmenter la vitesse\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) impliquent **\/Oy**.  La spécification de **\/Oy–** après l'option **\/Ox**, **\/O1** ou **\/O2** désactive **\/Oy**, que ce soit explicite ou implicite.  
  
 L'option de compilateur **\/Oy** complique l'utilisation du débogueur, car le compilateur supprime les informations relatives aux pointeurs de frame.  Si vous spécifiez une option de débogage du compilateur \([\/Z7, \/Zi, \/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)\), nous vous conseillons de spécifier l'option **\/Oy\-** après toute autre option d'optimisation du compilateur.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Optimisation**.  
  
4.  Modifiez la propriété **Omission des pointeurs de frame**.  Cette propriété ajoute ou supprime uniquement l'option **\/Oy**.  Si vous voulez ajouter l'option **\/Oy\-**, cliquez sur **Ligne de commande** et modifiez **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>.  
  
## Voir aussi  
 [\/O \(Optimiser le code\), options](../../build/reference/o-options-optimize-code.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)