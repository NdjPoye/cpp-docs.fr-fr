---
title: "Erreur du compilateur C2694 | Microsoft Docs"
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
  - "C2694"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2694"
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2694
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'substitution' : la fonction virtuelle de substitution a moins de spécifications d'exception restrictives que la fonction membre virtuelle de classe de base 'base'  
  
 Une fonction virtuelle a été substituée, mais sous [\/Za](../../build/reference/za-ze-disable-language-extensions.md), la fonction de substitution a une [spécification d'exception](../../cpp/exception-specifications-throw-cpp.md) moins restrictive.  
  
 L'exemple suivant génère l'erreur C2694 :  
  
```  
// C2694.cpp  
// compile with: /Za /c  
class MyBase {  
public:  
   virtual void f(void) throw(int) {  
   }  
};  
  
class Derived : public MyBase {  
public:  
   void f(void) throw(...) {}   // C2694  
   void f2(void) throw(int) {}   // OK  
};  
```