---
title: 2.6.3 Directive barrier | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d9c64787d9c6cc2dd0809f75f8f9db9819174d0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="263-barrier-directive"></a>2.6.3 Directive barrier
Le **barrière** directive synchronise tous les threads dans une équipe. En cas, chaque thread dans l’équipe attend jusqu'à ce que toutes les autres ont atteint ce point. La syntaxe de la **barrière** la directive est la suivante :  
  
```  
#pragma omp barrier new-line  
```  
  
 Une fois que tous les threads de l’équipe ont rencontré le cloisonnement, chaque thread dans l’équipe commence l’exécution des instructions après la directive de cloisonnement en parallèle. Étant donné que la **barrière** directive n’a pas d’une instruction de langage C dans le cadre de sa syntaxe, il existe certaines restrictions sur son positionnement dans un programme. Consultez [annexe C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) pour la grammaire formelle. L’exemple ci-dessous illustre ces restrictions.  
  
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