---
title: "Erreur du compilateur C3374 | Microsoft Docs"
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
  - "C3374"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3374"
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3374
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de récupérer l'adresse de 'function' à moins de créer une instance de délégué  
  
 L'adresse d'une fonction a été récupérée dans un autre contexte que la création d'une instance de délégué.  
  
 L'exemple suivant génère l'erreur C3374 :  
  
```  
// C3374.cpp  
// compile with: /clr  
public delegate void MyDel(int i);  
  
ref class A {  
public:  
   void func1(int i) {  
      System::Console::WriteLine("in func1 {0}", i);  
   }  
};  
  
int main() {  
   &A::func1;   // C3374  
  
   // OK  
   A ^ a = gcnew A;  
   MyDel ^ StaticDelInst = gcnew MyDel(a, &A::func1);  
}  
```  
  
## Voir aussi  
 [Comment : définir et utiliser des délégués](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)