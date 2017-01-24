---
title: "Erreur du compilateur C2512 | Microsoft Docs"
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
  - "C2512"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2512"
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2512
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : aucun constructeur par défaut approprié disponible  
  
 Aucun constructeur par défaut n'est disponible pour la classe, la structure ou l'union spécifiée.  Le compilateur fournit un constructeur par défaut seulement si aucun constructeur défini par l'utilisateur n'est fourni.  
  
 Si vous fournissez un constructeur qui accepte un paramètre non void et que vous souhaitez autoriser la création de votre classe sans paramètre \(comme, par exemple, les éléments d'un tableau\), vous devez également fournir un constructeur par défaut.  Le constructeur par défaut peut être un constructeur avec des valeurs par défaut pour tous les paramètres.  
  
 L'exemple suivant génère l'erreur C2512 et montre comment la corriger :  
  
```  
// C2512.cpp  
// C2512 expected  
struct B {  
   B (char *);  
   // Uncomment the following line to fix.  
   // B() {};  
};  
  
int main() {  
   B b;   
}  
```  
  
 L'exemple suivant montre une erreur C2512 plus subtile.  Pour corriger cette erreur, réorganisez le code pour définir la classe avant le référencement de son constructeur :  
  
```  
// C2512b.cpp  
// compile with: /c  
struct S {  
   struct X;  
  
   void f() {  
      X *x = new X();   // C2512 X not defined yet  
   }  
  
};  
  
struct S::X {};  
  
struct T {  
   struct X;  
   void f();  
};  
  
struct T::X {};  
  
void T::f() {  
   X *x = new X();  
}  
```  
  
 L'erreur C2512 peut également être provoquée par un appel à default\-construct, une classe qui contient un const ou des données membres de référence.  Ces membres doivent être initialisés dans une liste d'initialiseurs de constructeur, ce qui empêche le compilateur de générer un constructeur par défaut.  
  
 L'exemple suivant génère l'erreur C2512 et montre comment la corriger :  
  
```  
// C2512c.cpp  
// Compile by using: cl /c /W3 C2512c.cpp  
struct S {  
   const int i_;  
   int &r_;   
};   
  
int SumS() {  
   const int ci = 7;  
   int ir = 42;  
  
   S s1; // C2512 - no default constructor available  
   S s2{ci, ir};  // Fix - initialize const and reference members   
   return s2.i_ + s2.r_;  
}  
```