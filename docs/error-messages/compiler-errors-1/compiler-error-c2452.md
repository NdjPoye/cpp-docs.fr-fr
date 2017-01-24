---
title: "Erreur du compilateur C2452 | Microsoft Docs"
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
  - "C2452"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2452"
ms.assetid: a4ec7642-6660-4c7a-9866-853d1cc67daf
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2452
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : type source non valide pour safe\_cast  
  
 Le type de source de [safe\_cast](../../windows/safe-cast-cpp-component-extensions.md) n'était pas valide.  Par exemple, tous les types d'une opération `safe_cast` doivent être des types CLR.  
  
 L'exemple suivant génère l'erreur C2452 :  
  
```  
// C2452.cpp  
// compile with: /clr  
  
struct A {};  
struct B : public A {};  
  
ref struct C {};  
ref struct D : public C{};  
  
int main() {  
   A a;  
   safe_cast<B*>(&a);   // C2452  
  
   // OK  
   C ^ c = gcnew C;  
   safe_cast<D^>(c);  
}  
```