---
title: "Évaluateur d’expression, erreur CXX0021 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0021
dev_langs:
- C++
helpviewer_keywords:
- CXX0021
- CAN0021
ms.assetid: d6c0c35a-16c2-42c0-a7d2-e910350a47f0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 475074acf4a01c60fc1108910d5eb41c54b48923
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0021"></a>Évaluateur d'expression, erreur CXX0021
struct ou union utilisé comme scalaire  
  
 Une structure ou une union a été utilisée dans une expression, mais aucun élément n’a été spécifié.  
  
 Lors de la manipulation d’une structure ou une variable d’union, le nom de la variable peut apparaître de lui-même, sans qualificateur de champ. Si une structure ou une union est utilisée dans une expression, il doit être qualifié avec l’élément spécifique que vous le souhaitez.  
  
 Spécifiez l’élément dont la valeur doit être utilisé dans l’expression.  
  
 Cette erreur est identique à CAN0021.