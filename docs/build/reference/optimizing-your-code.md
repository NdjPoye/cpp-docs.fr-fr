---
title: "Optimisation du code | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compilateur cl.exe, performances"
  - "code, optimiser"
  - "optimisation"
  - "optimisation, code C++"
  - "performances, compilateur"
  - "performances, optimiser le code"
ms.assetid: 4f33e6c7-9870-43b3-9c2f-d7e44f764971
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Optimisation du code
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

En optimisant un fichier exécutable, vous pouvez atteindre un équilibre entre vitesse d'exécution et taille de code minime.  Cette rubrique décrit certains mécanismes fournis par Visual C\+\+ pour vous aider à optimiser le code.  
  
## Fonctionnalités de langage  
 Les rubriques suivantes décrivent certaines des fonctionnalités d'optimisation des langages C\/C\+\+.  
  
 [Pragmas et mots clés de l'optimisation](../../build/reference/optimization-pragmas-and-keywords.md)  
 Liste de mots clés et pragmas que vous pouvez utiliser dans votre code pour améliorer les performances.  
  
 [Options du compilateur classées par catégorie](../../build/reference/compiler-options-listed-by-category.md)  
 Liste d'options du compilateur **\/O** qui affectent spécifiquement la vitesse d'exécution ou la taille du code.  
  
 [Déclarateur de référence Rvalue : &&](../../cpp/rvalue-reference-declarator-amp-amp.md)  
 Les références rvalue prennent en charge l'implémentation de la *sémantique de déplacement*.  Si la sémantique de déplacement est utilisée pour implémenter des bibliothèques de modèles, les performances des applications utilisant ces modèles peuvent être considérablement améliorées.  
  
### Pragma optimize  
 Si une section de code optimisée provoque des erreurs ou un ralentissement, vous pouvez utiliser le pragma [optimize](../../preprocessor/optimize.md) pour désactiver l'optimisation de cette section.  
  
 Incluez le code entre deux pragmas, comme suit.  
  
```  
#pragma optimize("", off)  
// some code here   
#pragma optimize("", on)  
```  
  
## Méthodes de programmation  
 Vous pouvez remarquer des messages d'avertissement supplémentaires lorsque vous compilez votre code avec l'optimisation.  Ce comportement est normal car certains avertissements concernent uniquement le code optimisé.  Vous pouvez éviter de nombreux problèmes d'optimisation en tenant compte de ces avertissements.  
  
 Paradoxalement, l'optimisation d'un programme pour gagner en vitesse peut provoquer un ralentissement de l'exécution du code.  Ceci s'explique parce que certaines optimisations destinées à gagner de la vitesse augmentent la taille du code.  Par exemple, l'incorporation de fonctions éliminent les charges mémoire des appels de fonction.  Toutefois, l'incorporation de fonctions sur une trop grande quantité de code peut augmenter la taille de votre programme, et avec, le nombre d'erreurs de page de la mémoire virtuelle.  Par conséquent, le gain obtenu en termes de vitesse par l'élimination des appels aux fonctions peut être annulé par le phénomène d'échange de mémoire.  
  
 Les rubriques suivantes décrivent les meilleures pratiques de programmation.  
  
 [Conseils pour l'amélioration du code à durée critique](../../build/reference/tips-for-improving-time-critical-code.md)  
 De meilleures techniques de codage peuvent produire de meilleures performances.  Cette rubrique propose des techniques de codage qui peuvent vous aider à garantir que les parties à durée critique de votre code s'exécutent correctement.  
  
 [Meilleures pratiques pour l’optimisation](../../build/reference/optimization-best-practices.md)  
 Fournit des recommandations générales pour une bonne optimisation de votre application.  
  
## Débogage de code optimisé  
 Dans la mesure où l'optimisation peut modifier le code créé par le compilateur, nous vous recommandons de déboguer votre application et de mesurer ses performances, puis d'optimiser votre code.  
  
 Les rubriques suivantes fournissent des informations de base sur le débogage.  
  
-   [Débogage dans Visual Studio](../Topic/Debugging%20in%20Visual%20Studio.md)  
  
-   [Problèmes courants lors de la création d'une version release](../../build/reference/common-problems-when-creating-a-release-build.md)  
  
 Les rubriques suivantes fournissent des informations plus approfondies sur le débogage.  
  
-   [Comment : déboguer le code optimisé](../Topic/How%20to:%20Debug%20Optimized%20Code.md)  
  
-   [Pourquoi les nombres à virgule flottante peuvent manquer de précision](../../build/reference/why-floating-point-numbers-may-lose-precision.md)  
  
 La série de rubriques suivantes fournit des informations sur l'optimisation de la génération, du chargement et de l'exécution de votre code.  
  
-   [Amélioration du débit du compilateur](../../build/reference/improving-compiler-throughput.md)  
  
-   [L'utilisation d'un nom de fonction sans \(\) ne génère pas de code](../../build/reference/using-function-name-without-parens-produces-no-code.md)  
  
-   [Optimisation de l'assembly inline](../../assembler/inline/optimizing-inline-assembly.md)  
  
-   [Spécification de l'optimisation du compilateur pour un projet ATL](../../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)  
  
-   [Quelles techniques d'optimisation dois\-je utiliser pour améliorer les performances de l'application cliente lors du chargement ?](../../build/what-optimization-techniques-should-i-use.md)  
  
-   [!INCLUDE[crabout](../../build/reference/includes/crabout_md.md)] la réduction du temps de chargement des méthodes DLL, consultez les détails relatifs à l'optimisation des performances du temps de chargement des DLL dans la rubrique « Sous le capot » \(éventuellement en anglais\) de « MSDN Magazine » sur le site Web [MSDN Library \(éventuellement en anglais\)](http://go.microsoft.com/fwlink/?linkid=556).  
  
-   [!INCLUDE[crabout](../../build/reference/includes/crabout_md.md)] la réduction de la pagination dans les applications, consultez les détails \(en deux parties\) relatifs à l'amélioration des performances d'exécution grâce à l'outil Smooth Working Set dans la rubrique « Tueur de bogues » \(éventuellement en anglais\) de « MSDN Magazine » sur le site Web [MSDN Library \(éventuellement en anglais\)](http://go.microsoft.com/fwlink/?linkid=556).  
  
## Voir aussi  
 [Référence à la génération C\/C\+\+](../../build/reference/c-cpp-building-reference.md)