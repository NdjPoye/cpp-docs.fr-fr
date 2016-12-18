---
title: "2.6.3 barrier Directive | Microsoft Docs"
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
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.3 barrier Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La directive de **cloisonnement** synchronise tous les threads dans une équipe.  Une fois atteint, chaque thread dans l'équipe attend que tous les autres aient atteint ce point.  La syntaxe de la directive de **cloisonnement** est la suivante :  
  
```  
#pragma omp barrier new-line  
```  
  
 Lorsque tous les threads dans l'équipe ont atteint le cloisonnement, chaque thread dans l'équipe commence à exécuter les instructions après la directive de cloisonnement en parallèle.  Étant donné que la directive de **cloisonnement** n'a pas d'instructions de langage c dans le cadre de sa syntaxe, il existe des limites à son positionnement à l'intérieur d'un programme.  Consultez l' [annexe C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) pour la grammaire formels.  L'exemple suivant illustre ces restrictions.  
  
```  
/* ERROR - The barrier directive cannot be the immediate  
*          substatement of an if statement  
*/  
if (x!=0)  
   #pragma omp barrier  
...  
  
/* OK - The barrier directive is enclosed in a  
*      compound statement.  
*/  
if (x!=0) {  
   #pragma omp barrier  
}  
```