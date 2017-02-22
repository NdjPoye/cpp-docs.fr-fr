---
title: "Comment&#160;: d&#233;tecter une compilation /clr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr (option du compilateur C++), détecter l'utilisation de"
  - "compilation, détecter /clr"
ms.assetid: a9310045-4810-4637-a64a-0b31a08791c1
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Comment&#160;: d&#233;tecter une compilation /clr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez la macro `_MANAGED` ou `_M_CEE` pour déterminer si un module est compilé avec **\/clr**.  Pour plus d'informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Pour plus d'informations sur les macros, consultez [Macros prédéfinies](../preprocessor/predefined-macros.md).  
  
## Exemple  
  
```  
// detect_CLR_compilation.cpp  
// compile with: /clr  
#include <stdio.h>  
  
int main() {  
   #if (_MANAGED == 1) || (_M_CEE == 1)  
      printf_s("compiling with /clr\n");  
   #else  
      printf_s("compiling without /clr\n");  
   #endif  
}  
```  
  
## Voir aussi  
 [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)