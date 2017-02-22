---
title: "Erreur du compilateur C2743 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2743"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2743"
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2743
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : impossible d'intercepter un type natif avec le destructeur \_\_clrcall ou le constructeur de copie  
  
 Un module compilé avec **\/clr** \(et non avec **\/clr:pure**\) a essayé d'intercepter une exception de type natif où le destructeur du type ou le constructeur de copie utilise la convention d'appel \_`_clrcall`.  
  
 En cas de compilation avec **\/clr** \(et non avec **\/clr:pure**\), la gestion des exceptions s'attend à ce que les fonctions membre dans un type natif soient [\_\_cdecl](../../cpp/cdecl.md) et non [\_\_clrcall](../../cpp/clrcall.md).  Les types natifs possédant des fonctions membre qui utilisent la convention d'appel `__clrcall` ne peuvent pas être interceptés dans un module compilé avec **\/clr**.  
  
 Pour plus d'informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C2743 :  
  
```  
// C2743.cpp  
// compile with: /clr  
public struct S {  
   __clrcall ~S() {}  
};  
  
public struct T {  
   ~T() {}  
};  
  
int main() {  
   try {}  
   catch(S) {}   // C2743  
   // try the following line instead  
   // catch(T) {}  
  
   try {}  
   catch(S*) {}   // OK  
}  
```