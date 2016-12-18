---
title: "Erreur du compilateur C3255 | Microsoft Docs"
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
  - "C3255"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3255"
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3255
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type valeur' : impossible d'allouer dynamiquement cet objet de type valeur sur un tas natif  
  
 Les instances d'un type valeur \(voir [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)\) qui contient des membres managés peuvent être créées sur la pile, mais pas sur le tas.  
  
 L'exemple suivant génère l'erreur C3255 :  
  
```  
// C3255.cpp  
// compile with: /clr  
using namespace System;  
value struct V {  
   Object^ o;  
};  
  
value struct V2 {  
   int i;  
};  
  
int main() {  
   V* pv = new V;   // C3255  
   V2* pv2 = new V2;  
   V v2;  
}  
```  
  
 **Extensions managées pour C\+\+**  
  
 L'exemple suivant génère l'erreur C3255 :  
  
```  
// C3255b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__value struct V {  
   Object* o;  
};  
  
__value struct V2 {  
   int i;  
};  
  
int main() {  
   V* pv = __nogc new V;   // C3255  
   V2* pv2 = __nogc new V2;   // OK  
}  
```