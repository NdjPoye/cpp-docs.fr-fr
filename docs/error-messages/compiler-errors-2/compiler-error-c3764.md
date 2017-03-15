---
title: "Erreur du compilateur C3764 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3764"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3764"
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3764
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction\_substitution' : impossible de se substituer à la méthode de la classe de base 'fonction\_classe\_base'  
  
 Le compilateur a détecté une substitution incorrecte.  Par exemple, la fonction de la classe de base n'était pas `virtual`.  Pour plus d'informations, consultez [override](../../windows/override-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3764 :  
  
```  
// C3764.cpp  
// compile with: /clr /c  
public ref struct A {  
   void g(int);  
   virtual void h(int);  
};  
  
public ref struct B : A {  
   virtual void g(int) override {}   // C3764  
   virtual void h(int) override {}   // OK  
};  
```  
  
## Exemple  
 L'erreur C3764 peut également se produire lorsqu'une méthode de classe de base est à la fois substituée explicitement et nommée.  L'exemple suivant génère l'erreur C3764 :  
  
```  
// C3764_b.cpp  
// compile with: /clr /c  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : public A {  
   virtual void Test() override {}  
   virtual void Test2() = A::Test {}   // C3764  
};  
```