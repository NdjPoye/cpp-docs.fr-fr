---
title: "bad_cast, exception | Microsoft Docs"
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
  - "bad_cast"
  - "bad_cast_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_cast (mot clé) (C++)"
  - "exceptions, bad_cast"
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# bad_cast, exception
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exception `bad_cast` est levée par l'opérateur `dynamic_cast` suite à un échec de cast vers un type référence.  
  
## Syntaxe  
  
```  
catch (bad_cast)  
   statement  
```  
  
## Notes  
 L'interface de `bad_cast` est :  
  
```  
class bad_cast : public exception {  
public:  
   bad_cast(const char * _Message = "bad cast");  
   bad_cast(const bad_cast &);  
   virtual ~bad_cast();  
};  
```  
  
 Le code suivant contient un exemple de cast `dynamic_cast` qui échoue et qui lève l'exception `bad_cast`.  
  
```  
// expre_bad_cast_Exception.cpp  
// compile with: /EHsc /GR  
#include <typeinfo.h>  
#include <iostream>  
  
class Shape {  
public:  
   virtual void virtualfunc() const {}  
};  
  
class Circle: public Shape {  
public:  
   virtual void virtualfunc() const {}  
};  
  
using namespace std;  
int main() {  
   Shape shape_instance;  
   Shape& ref_shape = shape_instance;  
   try {  
      Circle& ref_circle = dynamic_cast<Circle&>(ref_shape);   
   }  
   catch (bad_cast b) {  
      cout << "Caught: " << b.what();  
   }  
}  
```  
  
 L'exception est levée car l'objet du cast \(Shape\) n'est pas dérivé du type de cast spécifié \(Circle\).  Pour éviter l'exception, ajoutez les déclarations ci\-dessous à `main` :  
  
```  
Circle circle_instance;  
Circle& ref_circle = circle_instance;  
```  
  
 Ensuite, changez le sens du cast dans le bloc `try`, comme suit :  
  
```  
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);  
```  
  
## Voir aussi  
 [dynamic\_cast, opérateur](../cpp/dynamic-cast-operator.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Gestion d'exceptions C\+\+](../cpp/cpp-exception-handling.md)