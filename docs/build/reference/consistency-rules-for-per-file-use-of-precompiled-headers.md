---
title: "R&#232;gles de coh&#233;rence pour l&#39;utilisation d&#39;en-t&#234;tes pr&#233;compil&#233;s par fichier | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .pch, règles de cohérence"
  - "fichiers PCH, règles de cohérence"
  - "fichiers d'en-tête précompilés, règles de cohérence"
ms.assetid: afd49365-48bc-41f4-b700-fe8297b944a1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# R&#232;gles de coh&#233;rence pour l&#39;utilisation d&#39;en-t&#234;tes pr&#233;compil&#233;s par fichier
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'option de compilation [\/Yu](../../build/reference/yu-use-precompiled-header-file.md) permet de spécifier le fichier d'en\-tête précompilé \(PCH\) à utiliser.  
  
 Lorsque vous faites appel à un fichier PCH, le compilateur suppose qu'il s'agit du même environnement de compilation \(cohérence des options de compilation, des pragmas, etc.\) que celui qui était en vigueur lors de la création du fichier PCH, sauf indication contraire.  Si le compilateur détecte une incohérence, il émet un avertissement et identifie l'incohérence quand c'est possible.  De tels avertissements n'indiquent pas nécessairement un problème au niveau du fichier PCH ; ils signalent simplement des conflits éventuels.  Les critères de cohérence des fichiers PCH sont décrits dans les sections suivantes.  
  
## Cohérence des options de compilation  
 Les options de compilation suivantes peuvent déclencher un avertissement d'incohérence lors de l'utilisation d'un fichier PCH :  
  
-   Les macros créées à l'aide de l'option du préprocesseur \(\/D\) doivent rester identiques entre la compilation ayant créé le fichier PCH et la compilation en cours.  L'état des constantes définies n'étant pas vérifié, des résultats imprévisibles peuvent apparaître en cas de modification de ces constantes.  
  
-   Les fichiers PCH ne fonctionnent pas avec les options \/E et \/EP.  
  
-   Les fichiers PCH doivent être créés à l'aide de l'option \/FR \(générer des infos du navigateur\) ou \/Fr \(exclure les variables locales\) avant que toute compilation ultérieure utilisant le fichier PCH puisse se servir de ces options.  
  
## Compatibilité C 7.0 \(\/Z7\)  
 Si cette option est activée lors de la création du fichier PCH, les compilations ultérieures utilisant le fichier PCH peuvent exploiter les informations de débogage.  
  
 Si l'option \/Z7 \(compatible C 7.0\) n'est pas activée lors de la création du fichier PCH, les compilations ultérieures utilisant le fichier PCH et \/Z7 déclenchent un avertissement.  Les informations de débogage sont placées dans le fichier .obj en cours, et les symboles locaux définis dans le fichier PCH ne sont pas disponibles pour le débogueur.  
  
## Cohérence du chemin d'accès Include  
 Un fichier PCH ne contient pas d'informations sur le chemin d'accès include qui était en vigueur lors de sa création.  Quand vous avez recours à un fichier .pch, le compilateur utilise toujours le chemin d'accès include spécifié dans la compilation en cours.  
  
## Cohérence du fichier source  
 Lorsque vous spécifiez l'option \/Yu \(utiliser le fichier d'en\-tête précompilé\), le compilateur ignore toutes les directives du préprocesseur \(y compris les pragmas\) figurant dans le code source qui sera précompilé.  La compilation spécifiée par ces directives du préprocesseur doit être identique à celle qui est utilisée pour l'option \/Yc \(créer un fichier d'en\-tête précompilé\).  
  
## Cohérence des pragmas  
 Les pragmas traités pendant la création d'un fichier PCH affectent généralement le fichier avec lequel le fichier PCH est utilisé ultérieurement.  Les pragmas de type comment et message n'affectent pas le reste de la compilation.  
  
 Les pragmas suivants, qui sont conservés en tant qu'éléments constitutifs d'un fichier PCH, affectent le reste d'une compilation utilisant le fichier PCH.  
  
||||  
|-|-|-|  
|alloc\_text|include\_alias|pack|  
|auto\_inline|init\_seg|pointers\_to\_members|  
|check\_stack|inline\_depth|setlocale|  
|code\_seg|inline\_recursion|vtordisp|  
|data\_seg|intrinsic|warning|  
|function|optimize||  
  
## Voir aussi  
 [Règles de cohérence s'appliquant aux en\-têtes précompilés](../../build/reference/precompiled-header-consistency-rules.md)   
 [\/Yu \(Utiliser un fichier d'en\-tête précompilé\)](../../build/reference/yu-use-precompiled-header-file.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)