---
title: "Avertissement du compilateur (niveau 1) C4382 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4382"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4382"
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4382
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

levée de 'type' : un type avec le constructeur de copie ou le destructeur \_\_clrcall ne peut être intercepté que dans le module \/clr:pure  
  
 En cas de compilation avec **\/clr** \(et non avec **\/clr:pure**\), la gestion des exceptions s'attend à ce que les fonctions membre dans un type natif soient [\_\_cdecl](../../cpp/cdecl.md) et non [\_\_clrcall](../../cpp/clrcall.md).  Les types natifs possédant des fonctions membre qui utilisent la convention d'appel `__clrcall` ne peuvent pas être interceptés dans un module compilé avec **\/clr**.  
  
 Si l'exception est interceptée dans un module compilé avec **\/clr:pure**, vous pouvez ignorer cet avertissement.  
  
 Pour plus d'informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4382 :  
  
```  
// C4382.cpp  
// compile with: /clr /W1 /c  
struct S {  
   __clrcall ~S() {}  
};  
  
struct T {  
   ~T() {}  
};  
  
int main() {  
   S s;  
   throw s;   // C4382  
  
   S * ps = &s;  
   throw ps;   // OK  
  
   T t;  
   throw t;   // OK  
}  
```