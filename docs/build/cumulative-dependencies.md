---
title: "Dépendances cumulatives | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 40811087cedd83bcd34745be7f1d5a404f4bb628
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cumulative-dependencies"></a>Dépendances cumulatives
Les dépendances sont cumulées dans un bloc de description si la cible se répète.  
  
 Par exemple, cet ensemble de règles,  
  
```Output  
bounce.exe : jump.obj  
bounce.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 est évalué comme ceci :  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 Cibles multiples dans plusieurs lignes de dépendance dans un bloc de description unique sont évaluées comme si chacune était spécifiée dans un bloc de description distinct, mais les cibles qui ne sont pas dans la dernière ligne de dépendance n’utilisent pas le bloc de commandes. NMAKE tente d’utiliser une règle d’inférence pour ces cibles.  
  
 Par exemple, cet ensemble de règles,  
  
```Output  
leap.exe bounce.exe : jump.obj  
bounce.exe climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 est évalué comme ceci :  
  
```Output  
  
leap.exe : jump.obj  
# invokes an inference rule  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Targets (Cibles MSBuild)](../build/targets.md)