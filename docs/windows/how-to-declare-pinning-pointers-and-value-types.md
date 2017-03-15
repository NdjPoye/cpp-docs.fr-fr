---
title: "How to: Declare Pinning Pointers and Value Types | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value types, declaring"
  - "pinning pointers"
ms.assetid: 57c5ec8a-f85a-48c4-ba8b-a81268bcede0
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# How to: Declare Pinning Pointers and Value Types
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un type valeur peut être converti implicitement.  Vous pouvez déclarer un pointeur épingle vers l'objet de type de valeur lui\-même et utiliser **pin\_ptr** vers le type de valeur boxed.  
  
## Exemple  
  
### Code  
  
```  
// pin_ptr_value.cpp  
// compile with: /clr  
value struct V {  
   int i;  
};  
  
int main() {  
   V ^ v = gcnew V;   // imnplicit boxing  
   v->i=8;  
   System::Console::WriteLine(v->i);  
   pin_ptr<V> mv = &*v;  
   mv->i = 7;  
   System::Console::WriteLine(v->i);  
   System::Console::WriteLine(mv->i);  
}  
```  
  
### Sortie  
  
```  
8  
7  
7  
```  
  
## Voir aussi  
 [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)