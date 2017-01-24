---
title: "Op&#233;rateurs de pointeur vers membre&#160;: .* et -&gt;* | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - ".*"
  - "->*"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".* (opérateur)"
  - "->* (opérateur)"
  - "expressions (C++), opérateurs"
  - "expressions (C++), pointeur"
  - "opérateurs pointeur vers membre"
ms.assetid: 2632be3f-1c81-4523-b56c-982a92a68688
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs de pointeur vers membre&#160;: .* et -&gt;*
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
      expression .* expression  
expression –>* expression  
```  
  
## Notes  
 Les opérateurs de pointeur vers membre, .\* et –\>\*, retournent la valeur d'un membre de classe spécifique pour l'objet spécifié à gauche de l'expression.  Le côté droit doit spécifier un membre de la classe.  L'exemple ci\-dessous illustre l'utilisation de ces opérateurs :  
  
```  
// expre_Expressions_with_Pointer_Member_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
class Testpm {  
public:  
   void m_func1() { cout << "m_func1\n"; }  
   int m_num;  
};  
  
// Define derived types pmfn and pmd.  
// These types are pointers to members m_func1() and  
// m_num, respectively.  
void (Testpm::*pmfn)() = &Testpm::m_func1;  
int Testpm::*pmd = &Testpm::m_num;  
  
int main() {  
   Testpm ATestpm;  
   Testpm *pTestpm = new Testpm;  
  
// Access the member function  
   (ATestpm.*pmfn)();  
   (pTestpm->*pmfn)();   // Parentheses required since * binds  
                        // less tightly than the function call.  
  
// Access the member data  
   ATestpm.*pmd = 1;  
   pTestpm->*pmd = 2;  
  
   cout  << ATestpm.*pmd << endl  
         << pTestpm->*pmd << endl;  
   delete pTestpm;  
}  
```  
  
## Sortie  
  
```  
m_func1  
m_func1  
1  
2  
```  
  
 Dans l'exemple précédent, un pointeur vers un membre, `pmfn`, est utilisé pour appeler la fonction membre `m_func1`.  Un autre pointeur vers un membre, `pmd`, est utilisé pour accéder au membre `m_num`.  
  
 L'opérateur binaire .\* associe son premier opérande, qui doit être un objet de type classe, avec son second opérande, qui doit être un type pointeur vers membre.  
  
 L'opérateur binaire –\>\* associe son premier opérande, qui doit être un pointeur désignant un objet de type classe, avec son second opérande, qui doit être un type pointeur vers membre.  
  
 Dans une expression contenant l'opérateur .\*, le premier opérande doit être du type classe du pointeur vers le membre spécifié dans le second opérande, et accessible à ce dernier, ou d'un type accessible clairement dérivé de cette classe et accessible à cette dernière.  
  
 Dans une expression contenant l'opérateur –\>\*, le premier opérande doit être de type « pointeur vers le type classe » du type spécifié dans le second opérande, ou il doit être d'un type clairement dérivé de cette classe.  
  
## Exemple  
 Considérez les classes et le fragment de programme suivants :  
  
```  
// expre_Expressions_with_Pointer_Member_Operators2.cpp  
// C2440 expected  
class BaseClass {  
public:  
   BaseClass(); // Base class constructor.  
   void Func1();  
};  
  
// Declare a pointer to member function Func1.  
void (BaseClass::*pmfnFunc1)() = &BaseClass::Func1;  
  
class Derived : public BaseClass {  
public:  
   Derived();  // Derived class constructor.  
   void Func2();  
};  
  
// Declare a pointer to member function Func2.  
void (Derived::*pmfnFunc2)() = &Derived::Func2;  
  
int main() {  
   BaseClass ABase;  
   Derived ADerived;  
  
   (ABase.*pmfnFunc1)();   // OK: defined for BaseClass.  
   (ABase.*pmfnFunc2)();   // Error: cannot use base class to  
                           // access pointers to members of  
                           // derived classes.   
  
   (ADerived.*pmfnFunc1)();   // OK: Derived is unambiguously  
                              // derived from BaseClass.   
   (ADerived.*pmfnFunc2)();   // OK: defined for Derived.  
}  
```  
  
 Le résultat des opérateurs de pointeur vers membre .\* ou –\>\* est un objet ou une fonction du type spécifié dans la déclaration du pointeur vers membre.  Ainsi, dans l'exemple précédent, le résultat de l'expression `ADerived.*pmfnFunc1()` est un pointeur vers une fonction qui retourne void.  Ce résultat est une l\-value si le second opérande est une l\-value.  
  
> [!NOTE]
>  Si le résultat d'un des opérateurs de pointeur vers membre est une fonction, le résultat peut être utilisé uniquement comme opérande pour l'opérateur d'appel de fonction.  
  
## Voir aussi  
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)