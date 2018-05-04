---
title: bad_cast, Exception | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bad_cast
- bad_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c09754e44b2cf1d7bda4bde35b8d76335d96711
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="badcast-exception"></a>bad_cast, exception
L'exception `bad_cast` est levée par l'opérateur `dynamic_cast` suite à un échec de cast vers un type référence.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
catch (bad_cast)  
   statement  
```  
  
## <a name="remarks"></a>Notes  
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
  
 L'exception est levée car l'objet du cast (Shape) n'est pas dérivé du type de cast spécifié (Circle). Pour éviter l'exception, ajoutez les déclarations ci-dessous à `main` :  
  
```  
Circle circle_instance;  
Circle& ref_circle = circle_instance;  
```  
  
 Ensuite, changez le sens du cast dans le bloc `try`, comme suit :  
  
```  
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);  
```  
  
## <a name="see-also"></a>Voir aussi  
 [dynamic_cast, opérateur](../cpp/dynamic-cast-operator.md)   
 [Mots clés](../cpp/keywords-cpp.md)   
 [Gestion d’exceptions C++](../cpp/cpp-exception-handling.md)