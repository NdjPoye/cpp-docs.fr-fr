---
title: "1.4 Conformit&#233; | Microsoft Docs"
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
ms.assetid: 662ad260-b9a1-43b7-b269-ef6ff0714e05
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1.4 Conformit&#233;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Est une implémentation de l’API C/C++ OpenMP *compatibles OpenMP* si elle reconnaît et conserve la sémantique de tous les éléments de cette spécification, tel qu’indiqué dans les chapitres 1, 2, 3, 4, et l’annexe c annexes A, B, D, E et F sont à titre d’information uniquement et ne font pas partie de la spécification. Les implémentations qui incluent uniquement un sous-ensemble de l’API ne sont pas compatibles OpenMP.  
  
 OpenMP C et C++ API est une extension de la langue de base qui est pris en charge par une implémentation. Si la langue de base ne prend pas en charge une construction de langage ou une extension qui s’affiche dans ce document, l’implémentation OpenMP n’est pas obligée de prendre en charge.  
  
 Toutes les fonctions intégrées et les fonctions de bibliothèque standard C et C++ (autrement dit, les fonctions dont le compilateur a connaissance spécifique) doit être thread-safe. Non synchronisée utilisation des fonctions de thread-safe par différents threads à l’intérieur d’une région parallèle ne produit pas un comportement non défini. Toutefois, le comportement peut être pas le même que dans une région de série. (Une fonction de génération de nombres aléatoires est un exemple.)  
  
 L’API C/C++ OpenMP Spécifie que certains comportements *défini par l’implémentation.* Une implémentation conforme de OpenMP est nécessaire pour définir et documenter son comportement dans ces cas. Consultez [annexe E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md), 97, pour obtenir la liste de comportements définis par l’implémentation de la page.