---
title: Compilateur avertissement (niveau 4) C4932 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4932
dev_langs:
- C++
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 6b479121e325035a2bf90bd239812613b73343ea
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4932"></a>Avertissement du compilateur (niveau 4) C4932
__identifier (identifier) et \__identifier(identifier) sont impossibles à distinguer  
  
 Le compilateur est incapable de faire la distinction entre **_finally** et `__finally` ou `__try` et **_try** comme un paramètre passé à [__identifier](../../windows/identifier-cpp-cli.md). Vous devez tenter pas les utiliser à la fois en tant qu’identificateurs dans le même programme, car cela entraînerait un [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) erreur.  
  
 L’exemple suivant génère l’erreur C4932 :  
  
```  
// C4932.cpp  
// compile with: /clr /W4 /WX  
int main() {  
   int __identifier(_finally) = 245;   // C4932  
   int __identifier(__finally) = 25;   // C4932  
}  
```
