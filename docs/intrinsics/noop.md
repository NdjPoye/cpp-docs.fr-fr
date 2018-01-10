---
title: __noop | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __noop_cpp
- __noop
dev_langs: C++
helpviewer_keywords: __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 348dc23e5ef3744ef1a3f152bf4d4fc5a22d2222
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="noop"></a>__noop
**Section spécifique à Microsoft**  
  
 Le `__noop` intrinsèque Spécifie qu’une fonction doit être ignorée et d’analyser la liste d’arguments, mais aucun code généré pour les arguments. Il est prévu pour une utilisation dans les fonctions globales de débogage qui prennent un nombre variable d’arguments.  
  
 Le compilateur convertit le `__noop` intrinsèque à 0 au moment de la compilation.  
  
## <a name="example"></a>Exemple  
 Le code suivant montre comment utiliser `__noop`.  
  
```  
// compiler_intrinsics__noop.cpp  
// compile with or without /DDEBUG  
#include <stdio.h>  
  
#if DEBUG  
   #define PRINT   printf_s  
#else  
   #define PRINT   __noop  
#endif  
  
int main() {  
   PRINT("\nhello\n");  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Intrinsèques du compilateur](../intrinsics/compiler-intrinsics.md)   
 [Mots clés](../cpp/keywords-cpp.md)