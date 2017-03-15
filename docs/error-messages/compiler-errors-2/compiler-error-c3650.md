---
title: "Erreur du compilateur C3650 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3650"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3650"
ms.assetid: ca4d8de4-b027-4d13-9b9f-03ca62905c33
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C3650
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'méthode\_interface' : ne peut pas être utilisé comme substitution explicite, doit être une fonction membre virtuelle d'une classe de base  
  
 Une tentative d'exécution d'une substitution explicite sur un membre non virtuel a été effectuée.  
  
 Pour plus d'informations, consultez [Substitutions explicites](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
 L'exemple suivant génère l'erreur C3650 :  
  
```  
// C3650.cpp  
// compile with: /clr  
public interface struct I {  
   void a();  
};  
  
public ref class S {  
public:  
   static int f() { return 0; }  
   static int g() { return 0; }  
};  
  
public ref struct T1 : public S, I {  
   virtual int f() new sealed = S::f;   // C3650  
   virtual int g() { return 0; }   // OK does not override S::g  
   virtual void a() new sealed = I::a {}   // OK  
};  
```