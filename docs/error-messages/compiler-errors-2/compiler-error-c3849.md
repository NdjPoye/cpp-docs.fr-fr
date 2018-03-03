---
title: Erreur du compilateur C3849 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3849
dev_langs:
- C++
helpviewer_keywords:
- C3849
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b310fce347423075b1c3d23244a5059151ac87fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3849"></a>Erreur du compilateur C3849
appel de style fonction sur une expression de type 'type' perdrait les qualificateurs const et/ou volatiles pour nombre de toutes les surcharges d’opérateur disponibles  
  
 Une variable avec un type const-volatile peut uniquement appeler des membres fonctions avec des qualifications const-volatile égales ou supérieures.  
  
 Pour corriger cette erreur, fournissez une fonction membre approprié. Impossible d’exécuter une conversion sur un objet const ou volatile complet lors de la conversion entraîne la perte de qualification. Vous pouvez obtenir des qualificateurs mais vous ne pouvez pas perdre de qualificateurs dans une conversion.  
  
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