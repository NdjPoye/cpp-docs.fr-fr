---
title: Compilateur avertissement (niveau 3) C4290 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4290
dev_langs:
- C++
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f70a278cb3e660e89e1aba067cab9c20aacf8f62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4290"></a>Avertissement du compilateur (niveau 3) C4290
Spécification d’exception C++ ignorée sauf to indiquer qu’une fonction n’est pas __declspec (nothrow)  
  
 Une fonction est déclarée à l’aide de la spécification d’exception, lequel Visual C++ accepte mais n’implémente pas. Avec l’exception peuvent doivent être recompilés spécifications qui sont ignorées lors de la compilation de code et lié pour être réutilisées dans les futures versions prenant en charge les spécifications d’exceptions.  
  
 Pour plus d’informations, consultez [spécifications d’Exception (throw)](../../cpp/exception-specifications-throw-cpp.md) .  
  
 Vous pouvez éviter cet avertissement à l’aide de la [avertissement](../../preprocessor/warning.md) pragma :  
  
```  
#pragma warning( disable : 4290 )  
```  
  
 L’exemple de code suivant génère C4290 :  
  
```  
// C4290.cpp  
// compile with: /EHs /W3 /c  
void f1(void) throw(int) {}   // C4290  
  
// OK  
void f2(void) throw() {}  
void f3(void) throw(...) {}  
```