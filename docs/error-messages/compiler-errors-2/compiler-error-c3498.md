---
title: "Compiler Error C3498 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3498"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3498"
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compiler Error C3498
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : vous ne pouvez pas capturer une variable dotée d'un type managé ou WinRT  
  
 Vous ne pouvez pas capturer une variable dotée d'un type managé ou d'un type Windows Runtime dans une expression lambda.  
  
### Pour corriger cette erreur  
  
-   Transmettez la variable managée ou de Windows Runtime dans la liste des paramètres de l'expression lambda.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3498, car une variable dotée d'un type managé figure dans la liste de capture d'une expression lambda :  
  
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
  
## Exemple  
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
  
## Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)