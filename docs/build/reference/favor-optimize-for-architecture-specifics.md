---
title: "/favor (optimisation pour les particularit&#233;s d&#39;architecture) | Microsoft Docs"
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
  - "/favor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "-favor (option du compilateur C++)"
  - "/favor (option du compilateur C++)"
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
caps.latest.revision: 31
caps.handback.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /favor (optimisation pour les particularit&#233;s d&#39;architecture)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L' **\/favor:**`option` produit le code optimisé pour une architecture spécifique ou pour les caractéristiques des micro\-architectures à la fois dans les architectures AMD et Intel.  
  
## Syntaxe  
  
```  
/favor:{blend | ATOM | AMD64 | INTEL64}  
```  
  
## Notes  
 **\/favor:blend**  
 \(x86 and x64\) produit le code optimisé pour les caractéristiques des micro\-architectures à la fois dans les architectures AMD et Intel.  Même s'il est possible que **\/favor:blend** n'assure pas des performances optimales sur un processeur spécifique, cette option est conçue pour fournir les meilleures performances sur une vaste gamme de processeurs x86 and x64.  Par défaut, **\/favor:blend** est activée.  
  
 **\/favor:ATOM**  
 \(x86 et x64\) produit le code optimisé pour les caractéristiques des processeurs Intel Atom et Intel Centrino Atom Technology.  Le code qui est généré à l'aide de **\/favor:ATOM** peut également produire les instructions Intel SSSE3, SSE3, SSE2 et SSE pour les processeurs Intel.  
  
 **\/favor:AMD64**  
 \(x64 uniquement\) optimise le code généré pour l'AMD Opteron et les processeurs Athlon qui prennent en charge les extensions 64 bits.  Le code optimisé peut s'exécuter sur toutes les plateformes compatibles avec x64.  Le code généré à l'aide de **\/favor:AMD64** peut entraîner une dégradation des performances sur les processeurs Intel prenant en charge Intel64.  
  
 **\/favor:INTEL64**  
 \(x64 uniquement\) optimise le code généré pour les processeurs Intel prenant en charge Intel64, ce qui entraîne généralement de meilleures performances pour cette plateforme.  Le code résultant peut s'exécuter sur toute plateforme x64.  Le code généré avec **\/favor:INTEL64** peut entraîner une dégradation des performances sur les processeurs AMD Opteron et Athlon prenant en charge les extensions 64 bits.  
  
> [!NOTE]
>  L'architecture Intel64 était précédemment appelée EM64T \(Extended Memory 64 Technology\) et l'option du compilateur correspondante était **\/favor:EM64T**.  
  
 Pour plus d'informations sur la programmation pour l'architecture [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] , consultez [Conventions des logiciels x64](../../build/x64-software-conventions.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Sélectionnez le dossier **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Entrez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)