---
title: "Erreur du compilateur C2248 | Microsoft Docs"
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
  - "C2248"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2248"
ms.assetid: 7a3ba0e8-d3b9-4bb9-95db-81ef17e31d23
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2248
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'membre' : impossible d'accéder au membre 'accès' déclaré dans la classe 'classe'  
  
 Les membres d'une classe dérivée ne peuvent pas accéder aux membres déclarés `private` d'une classe de base.  Vous ne pouvez pas accéder aux membres `private` ou `protected` d'instances de classe.  
  
 Consultez l'article 243351 de la Base de connaissances Microsoft pour plus d'informations sur l'erreur C2248.  
  
 L'exemple suivant génère l'erreur C2248 :  
  
```  
// C2248.cpp  
#include <stdio.h>  
class X {  
public:  
   int  m_pubMemb;  
   void setPrivMemb( int i ) {  
      m_privMemb = i;  
      printf_s("\n%d", m_privMemb);  
   }  
protected:  
   int  m_protMemb;  
  
private:  
   int  m_privMemb;  
} x;  
  
int main() {  
   x.m_pubMemb = 4;  
   printf_s("\n%d", x.m_pubMemb);  
   x.m_protMemb = 2;   // C2248 m_protMemb is protected  
   x.m_privMemb = 3;   // C2248  m_privMemb is private  
   x.setPrivMemb(0);   // OK uses public access function  
}  
```  
  
 Un autre problème de conformité qui déclenche l'erreur C2248 est l'utilisation de friends et d'une spécialisation de modèle.  Pour plus d'informations, consultez l'[Erreur des outils Éditeur de liens LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md).  
  
```  
// C2248_b.cpp  
template<class T>  
void f(T t) {  
   t.i;   // C2248  
}  
  
struct S {  
private:  
   int i;  
  
public:  
   S() {}  
   // Delete the following line to resolve.  
   friend void f(S);   // refer to the non-template function void f(S)  
  
   // Uncomment the following line to resolve.  
   // friend void f<S>(S);  
};  
  
int main() {  
   S s;  
   f<S>(s);  
}  
```  
  
 Un autre problème de conformité générant l'erreur C2248 est une tentative de déclaration d'un friend d'une classe et lorsque la classe n'est pas visible à la déclaration friend dans la portée de la classe.  Dans ce cas, accordez l'amitié à la classe englobante pour résoudre l'erreur.  
  
```  
// C2248_c.cpp  
// compile with: /c  
class T {  
   class S {  
      class E {};  
   };  
   friend class S::E;   // C2248  
};  
  
class A {  
   class S {  
      class E {};  
      friend class A;   // grant friendship to enclosing class  
   };  
   friend class S::E;   // OK  
};  
```