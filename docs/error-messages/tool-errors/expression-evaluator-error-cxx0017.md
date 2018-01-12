---
title: "Évaluateur d’expression, erreur CXX0017 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0017
dev_langs: C++
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e769e9886168c9f19ad110c48d848a9b84ab8aac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0017"></a>Évaluateur d'expression, erreur CXX0017
symbole introuvable  
  
 Impossible de trouver un symbole spécifié dans une expression.  
  
 Une des causes possibles de cette erreur est une incompatibilité de cas dans le nom du symbole. Étant donné que C et C++ sont des langages qui respecte la casse, un nom de symbole doit figurer dans la casse exacte dans laquelle il est défini dans la source.  
  
 Cette erreur peut se produire lorsque vous tentez de convertir une variable afin de surveiller la variable pendant le débogage. Le `typedef` déclare un nouveau nom pour un type, mais il ne définit pas un nouveau type. La conversion de type tentée dans le débogueur exige que le nom d’un type défini.  
  
 Cette erreur est identique à CAN0017.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Assurez-vous que le symbole est déjà déclaré au niveau du point du programme où il est utilisé.  
  
2.  Pour effectuer un cast de variables dans le débogueur, utilisez un nom de type réel plutôt qu’un `typedef`-nom défini.