---
title: "Erreur du compilateur C3849 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3849"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3849"
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3849
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

un appel de style fonction sur une expression de type 'type' perdrait les qualificateurs const et\/ou volatile pour l'ensemble des 'nombre' surcharges d'opérateur disponibles  
  
 Une variable de type const\-volatile peut uniquement appeler des fonctions membre définies avec des qualifications const\-volatile égales ou supérieures.  
  
 Pour remédier à cette erreur, fournissez une fonction membre appropriée.  Vous ne pouvez pas exécuter une conversion sur un objet qualifié const ou volatile lorsque la conversion entraîne une perte de qualification.  Vous pouvez obtenir des qualificateurs mais vous ne pouvez pas perdre de qualificateurs dans une conversion.  
  
 Les exemples suivants génèrent C3849 :  
  
```  
// C3849.cpp  
void glbFunc3(int i, char c)  
{  
   i;  
}  
typedef void (* pFunc3)(int, char);  
  
void glbFunc2(int i)  
{  
   i;  
}  
  
typedef void (* pFunc2)(int);  
  
void glbFunc1()  
{  
}  
typedef void (* pFunc1)();  
  
struct S4  
{  
   operator ()(int i)  
   {  
      i;  
   }  
  
   operator pFunc1() const  
   {  
      return &glbFunc1;  
   }  
  
   operator pFunc2() volatile  
   {  
      return &glbFunc2;  
   }  
  
   operator pFunc3()  
   {  
      return &glbFunc3;  
   }  
  
   // operator pFunc1() const volatile  
   // {  
   //    return &glbFunc1;  
   // }  
};  
  
int main()  
{  
   // Cannot call any of the 4 overloads of "operator ()(.....)" and   
   // "operator pFunc()" because none is declared as "const volatile"  
   const volatile S4 s4;  // can only call cv member functions of S4  
   s4();   // C3849 to resolve, uncomment member function  
}  
```