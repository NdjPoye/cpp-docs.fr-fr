---
title: "Évaluateur d’expression, erreur CXX0024 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0024
dev_langs:
- C++
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c96bd943719afb0d974a5c4386742bea24396fd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0024"></a>Évaluateur d'expression, erreur CXX0024
l’opération requiert l-value  
  
 Une expression qui ne correspond pas à une l-value a été spécifiée pour une opération qui requiert une l-value.  
  
 Une l-value (appelée ainsi parce qu’elle apparaît sur le côté gauche d’une instruction d’assignation) est une expression qui fait référence à un emplacement de mémoire.  
  
 Par exemple, `buffer[count]` est une l-value valide car elle pointe vers un emplacement mémoire spécifique. La comparaison logique `zed != 0` n’est pas une l-value valide, car il prend la valeur TRUE ou FALSE, pas une adresse mémoire.  
  
 Cette erreur est identique à CAN0024.