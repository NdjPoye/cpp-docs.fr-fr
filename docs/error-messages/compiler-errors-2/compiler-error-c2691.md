---
title: "Erreur du compilateur C2691 | Microsoft Docs"
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
  - "C2691"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2691"
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2691
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type de données' : un tableau managé ou WinRT ne peut pas avoir ce type d'élément  
  
 Le type d'un élément de tableau managé ou WinRT peut être un type valeur ou un type référence.  
  
 L'exemple suivant génère l'erreur C2691 :  
  
```  
// C2691a.cpp  
// compile with: /clr  
class A {};  
  
int main() {  
   array<A>^ a1 = gcnew array<A>(20);   // C2691  
   array<int>^ a2 = gcnew array<int>(20);   // value type OK  
}  
```  
  
 L'exemple suivant génère l'erreur C2691 :  
  
```  
// C2691b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
int main() {  
   int * a1 __gc[];   // C2691  
   int * a1 = new int [20];   // OK  
}  
```  
  
 L'erreur C2691 peut également se produire si vous essayez de définir un tableau en escalier à l'aide des extensions managées pour C\+\+.  Les tableaux en escalier sont pris en charge dans la syntaxe actuelle. Consultez [Arrays](../../windows/arrays-cpp-component-extensions.md) pour plus d'informations.  
  
 L'exemple suivant génère l'erreur C2691 :  
  
```  
// C2691c.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
int main() {  
   Int32 myJaggedArray[][] = new Int32 [50][];   // C2691  
}  
```