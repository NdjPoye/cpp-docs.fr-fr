---
title: "2.1 Directive Format | Microsoft Docs"
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
ms.assetid: 918b6445-d35e-4176-9565-b045be941b4d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.1 Directive Format
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la syntaxe d'une directive d'OpenMP est formellement spécifiée par la grammaire dans [annexe C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md), et officieusement comme suit :  
  
```  
#pragma omp directive-name  [clause[ [,] clause]...] new-line  
```  
  
 Démarrage de chaque directive avec **omp \#pragma**, de réduire le risque pour le conflit avec d'autres \(extensions de non\-OpenMP ou de fournisseur à OpenMP\) directives pragma portant le même nom.  Le reste de la directive suit les conventions de C et C\+\+ standard pour les directives de compilateur.  en particulier, l'espace blanc peut être utilisé avant et après **\#**, et parfois l'espace blanc doit être utilisé pour séparer les mots dans une directive.  Les jetons de prétraitement suivant **omp \#pragma** sont soumis à un remplacement.  
  
 Les directives respectent la casse.  L'ordre dans lequel les clauses apparaissent dans les directives n'a pas d'importance.  Les clauses sur les directives peuvent être répétées si nécessaire, en fonction de les restrictions répertoriées dans la description de chaque clause.  Si *la variable\-liste* apparaît dans une clause, elle doit spécifier uniquement des variables.  Un seul *directive\-nom* peut être spécifié pour chaque directive.  Par exemple, vous ne pouvez pas utiliser la directive suivante :  
  
```  
/* ERROR - multiple directive names not allowed */  
#pragma omp parallel barrier  
```  
  
 Une directive d'OpenMP s'applique à au plus une instruction suivante sera, qui doit être un bloc structuré.