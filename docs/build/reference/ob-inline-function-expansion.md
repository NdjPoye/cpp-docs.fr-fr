---
title: "/Ob (Expansion des fonctions Inline) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.InlineFunctionExpansion"
  - "VC.Project.VCCLCompilerTool.InlineFunctionExpansion"
  - "/ob"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Ob (option du compilateur C++)"
  - "/Ob0 (option du compilateur C++)"
  - "/Ob1 (option du compilateur C++)"
  - "/Ob2 (option du compilateur C++)"
  - "toute option appropriée au compilateur C++"
  - "désactiver (option du compilateur C++)"
  - "expansion inline, option du compilateur"
  - "fonctions inline, expansion des fonctions (option du compilateur C++)"
  - "Ob (option du compilateur C++)"
  - "-Ob (option du compilateur C++)"
  - "Ob0 (option du compilateur C++)"
  - "-Ob0 (option du compilateur C++)"
  - "Ob1 (option du compilateur C++)"
  - "-Ob1 (option du compilateur C++)"
  - "Ob2 (option du compilateur C++)"
  - "-Ob2 (option du compilateur C++)"
  - "only __inline (option du compilateur C++)"
ms.assetid: f134e6df-e939-4980-a01d-47425dbc562a
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Ob (Expansion des fonctions Inline)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Contrôle l'expansion inline des fonctions.  
  
## Syntaxe  
  
```  
/Ob{0|1|2}  
```  
  
## Arguments  
 **0**  
 Désactive les expansions inline.  Par défaut, l'expansion se produit à la discrétion du compilateur sur toutes les fonctions, et est souvent appelée *auto\-inlining*.  
  
 **1**  
 Permet uniquement l'expansion de fonctions marquées [inline](../../misc/inline-inline-forceinline.md), [\_\_inline](../../misc/inline-inline-forceinline.md) ou [\_\_forceinline](../../misc/inline-inline-forceinline.md), ou dans une fonction membre C\+\+ définie dans une déclaration de classe.  
  
 **2**  
 Valeur par défaut.  Autorise l'expansion des fonctions marquées comme `inline`, `__inline`, ou `__forceinline`, et toute autre fonction choisie par le compilateur.  
  
 **\/Ob2** est appliqué quand [\/O1, \/O2 \(Réduire la taille, augmenter la vitesse\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) ou [\/Ox \(Optimisation complète\)](../../build/reference/ox-full-optimization.md) est utilisé.  
  
 Cette option nécessite que vous activiez des optimisations à l'aide de **\/O1**, **\/O2**, **\/Ox** ou **\/Og**.  
  
## Notes  
 Le compilateur traite les options d'expansion inline et les mots clés comme des suggestions.  Il n'existe aucune garantie que toutes les fonctions seront développées inline.  Vous pouvez désactiver les expansions inline, mais vous ne pouvez pas forcer le compilateur à insérer une fonction particulière, même si vous utilisez le mot clé `__forceinline`.  
  
 Vous pouvez utiliser la directive `#pragma` [auto\_inline](../../preprocessor/auto-inline.md) pour qu'une fonction ne soit pas éligible à l'expansion inline.  Consultez également la directive `#pragma` [intrinsic](../../preprocessor/intrinsic.md) .  
  
> [!NOTE]
>  Les informations collectées à partir des séries de tests de profilage remplacent les optimisations qui seraient en vigueur si vous spécifiiez **\/Ob**, **\/Os** ou **\/Ot**.  Pour plus d'informations, consultez [Optimisations guidées par profil](../../build/reference/profile-guided-optimizations.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Développez **Propriétés de configuration**, **C\/C\+\+**, puis sélectionnez **Optimisation**.  
  
3.  Modifiez la propriété **Expansion des fonctions inline**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.InlineFunctionExpansion%2A>.  
  
## Voir aussi  
 [\/O \(Optimiser le code\), options](../../build/reference/o-options-optimize-code.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)