---
title: Instruction d’expression | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e627e107df850f31a9cf04981795edd1185c0ce5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-statement"></a>Instruction d'expression
Les instructions d'expression entraînent des expressions à évaluer. Aucun transfert de contrôle ou d'itération n'a lieu à la suite d'une instruction d'expression.  
  
 La syntaxe de l'instruction d'expression est simplement  
  
## <a name="syntax"></a>Syntaxe  
  
```  
[expression ] ;  
```  
  
## <a name="remarks"></a>Notes  
 Toutes les expressions appartenant à une instruction d'expression sont évaluées et tous les effets secondaires sont terminés avant l'exécution de l'instruction suivante. Les instructions d'expression les plus courantes sont les assignations et les appels de fonction.  Étant donné que l’expression est facultative, seul un point-virgule est considéré comme une instruction d’expression vide, appelée le [null](../cpp/null-statement.md) instruction.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble des instructions C++](../cpp/overview-of-cpp-statements.md)