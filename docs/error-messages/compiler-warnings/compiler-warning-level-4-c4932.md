---
title: Compilateur avertissement (niveau 4) C4932 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4932
dev_langs:
- C++
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d99fc58f9e6208db9aaeb8689e8be8b49f9aaea4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4932"></a>Avertissement du compilateur (niveau 4) C4932
__identifier (identifier) et \__identifier(identifier) sont impossibles à distinguer  
  
 Le compilateur ne peut pas faire la distinction entre **_finally** et `__finally` ou `__try` et **_try** en tant que paramètre passé à [__identifier](../../windows/identifier-cpp-cli.md). Vous ne devez pas essayer de les utiliser tous les deux en tant qu’identificateurs dans le même programme, car cela se traduit par une erreur [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) .  
  
 L’exemple suivant génère l’erreur C4932 :  
  
```  
// C4932.cpp  
// compile with: /clr /W4 /WX  
int main() {  
   int __identifier(_finally) = 245;   // C4932  
   int __identifier(__finally) = 25;   // C4932  
}  
```