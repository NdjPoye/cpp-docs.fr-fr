---
title: "/Q (Op&#233;rations de bas niveau), options | Microsoft Docs"
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
  - "/q"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Q (option du compilateur C++)"
  - "-Q (option du compilateur C++)"
  - "/Q (option du compilateur C++)"
ms.assetid: 9fa738b9-630a-4bde-bc87-bdfa30552be4
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Q (Op&#233;rations de bas niveau), options
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez les options du compilateur **\/Q** pour exécuter les opérations de compilateur de bas niveau suivantes :  
  
-   [\/Qfast\_transcendentals \(Force Fast Transcendentals\)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md) : génère des fonctions transcendantes rapides.  
  
-   [\/QIfist \(Supprimer \_ftol\)](../../build/reference/qifist-suppress-ftol.md) : supprime `_ftol` lorsque la conversion d'un type à virgule flottante vers un type d'entier est requise \(x86 uniquement\).  
  
-   [\/Qimprecise\_fwaits \(Remove fwaits Inside Try Blocks\)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md) : supprime les commandes `fwait` dans les blocs `try`.  
  
-   [\/Qpar \(paralléliseur automatique\)](../../build/reference/qpar-auto-parallelizer.md): Active la parallélisation automatique des boucles marquées avec la directive [\#pragma loop\(\)](../../preprocessor/loop.md).  
  
-   [\/Qpar\-report \(Niveau de rapport du paralléliseur automatique\)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): Active les niveaux de création de rapports pour la parallélisation automatique.  
  
-   [\/Qsafe\_fp\_loads](../../build/reference/qsafe-fp-loads.md): Supprime les optimisations pour les chargements de registres à virgule flottante et pour les déplacements entre la mémoire et MMX de registres.  
  
-   [\/Qvec\-report \(Niveau de rapport du vectoriseur automatique\)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): Active les niveaux de création de rapports pour le vectorisation automatique.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)