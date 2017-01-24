---
title: "How to: Overload Functions with Interior Pointers and Native Pointers (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Functions with interior and native pointers, overloading"
ms.assetid: d70df625-4aad-457c-84f5-70a0a290cc1f
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Overload Functions with Interior Pointers and Native Pointers (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fonctions peuvent être surchargées selon que le type de paramètre soit un pointeur intérieur ou un pointeur natif.  
  
> [!IMPORTANT]
>  Cette fonctionnalité des langues est prise en charge par l'option du compilateur **\/clr**, mais pas par l'option du compilateur **\/ZW**.  
  
## Exemple  
  
### Code  
  
```  
// interior_ptr_overload.cpp  
// compile with: /clr  
using namespace System;  
  
// C++ class  
struct S {  
   int i;  
};  
  
// managed class  
ref struct G {  
   int i;  
};  
  
// can update unmanaged storage  
void f( int* pi ) {  
   *pi = 10;  
   Console::WriteLine("in f( int* pi )");  
}  
  
// can update managed storage  
void f( interior_ptr<int> pi ) {  
   *pi = 10;   
   Console::WriteLine("in f( interior_ptr<int> pi )");  
}  
  
int main() {  
   S *pS = new S;   // C++ heap  
   G ^pG = gcnew G;   // common language runtime heap  
   f( &pS->i );  
   f( &pG->i );  
};  
```  
  
### Sortie  
  
```  
in f( int* pi )  
in f( interior_ptr<int> pi )  
```  
  
## Voir aussi  
 [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)