---
title: 2.1 Format des directives | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 918b6445-d35e-4176-9565-b045be941b4d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c3ff4e0078ffd086ce3b62d8927184188f0ebdd8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="21-directive-format"></a>2.1 Format des directives
La syntaxe d’une directive OpenMP est bonne et due forme spécifiée par la grammaire dans [annexe C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)et de manière informelle comme suit :  
  
```  
#pragma omp directive-name  [clause[ [,] clause]...] new-line  
```  
  
 Chaque directive commence par **#pragma omp**afin de réduire le risque potentiel de conflit avec d’autres directives de pragma (non-OpenMP ou fournisseur extensions OpenMP) portant le même nom. Le reste de la directive suit les conventions des normes pour les directives du compilateur C et C++. En particulier, un espace blanc peut être utilisé avant et après le  **#** , et parfois un espace blanc doit être utilisé pour séparer les mots dans une directive. Prétraitement des jetons après la **#pragma omp** sont soumises à remplacement de macro.  
  
 Directives respectent la casse. L’ordre dans lequel les clauses apparaissent dans les directives n’est pas significatif. Clauses sur les directives peuvent être répétés si nécessaire, soumis aux restrictions répertoriées dans la description de chaque clause. Si *variable-list* s’affiche dans une clause, il doit spécifier uniquement les variables. Seul *nom de la directive* peut être spécifiée par la directive.  Par exemple, la directive suivante n’est pas autorisée :  
  
```  
/* ERROR - multiple directive names not allowed */  
#pragma omp parallel barrier  
```  
  
 Une directive OpenMP s’applique à tout au plus un suivante instruction, qui doit être un bloc structuré.