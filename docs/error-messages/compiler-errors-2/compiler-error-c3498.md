---
title: Erreur du compilateur C3498 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3498
dev_langs: C++
helpviewer_keywords: C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d895c0dc40d94d6a8fcd567173e2d596e68e333
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3498"></a>Erreur du compilateur C3498
'var' : vous ne pouvez pas capturer une variable qui a géré ou un WinRTtype  
  
 Vous ne pouvez pas capturer une variable dotée d'un type managé ou d'un type Windows Runtime dans une expression lambda.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Transmettez la variable managée ou de Windows Runtime dans la liste des paramètres de l’expression lambda.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3498, car une variable dotée d’un type managé figure dans la liste de capture d’une expression lambda :  
  
```  
// C3498a.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String ^ s = "Hello";  
   [&s](String ^ r)   
      { return String::Concat(s, r); } (", World!"); // C3498  
}  
```  
  
## <a name="example"></a>Exemple  
 L'exemple suivant résout l'erreur C3498 en transmettant la variable managée `s` à la liste des paramètres de l'expression lambda :  
  
```  
// C3498b.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String ^ s = "Hello";  
   [](String ^ s, String ^ r)   
      { return String::Concat(s, r); } (s, ", World!");  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)