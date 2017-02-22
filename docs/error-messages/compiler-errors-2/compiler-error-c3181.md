---
title: "Erreur du compilateur C3181 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3181"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3181"
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur du compilateur C3181
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : opérande non valide pour opérateur  
  
 Un paramètre non valide a été passé à l'opérateur [\_\_typeof](../../misc/typeof.md) ou [typeid](../../windows/typeid-cpp-component-extensions.md).  Le paramètre doit être un type managé.  
  
 Notez que le compilateur emploie des alias pour les types natifs qui renvoient aux types dans le Common Language Runtime.  
  
 L'exemple suivant génère l'erreur C3181 :  
  
```  
// C3181a.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181  
   Type ^pType2 = int::typeid;   // OK  
}  
```  
  
 L'exemple suivant génère l'erreur C3181 :  
  
```  
// C3181b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
int main() {  
   Type *pType1 = __typeof(int __gc*);   // C3181  
   Type *pType2 = __typeof(int*);   // OK  
}  
```