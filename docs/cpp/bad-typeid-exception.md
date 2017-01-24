---
title: "bad_typeid, exception | Microsoft Docs"
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
  - "bad_typeid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_typeid (exception)"
  - "exceptions, bad_typeid"
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# bad_typeid, exception
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exception `bad_typeid` est levée par l'[opérateur de typeid](../cpp/typeid-operator.md) lorsque l'opérande de `typeid` est un pointeur NULL.  
  
## Syntaxe  
  
```  
  
      catch (bad_typeid)  
   statement  
```  
  
## Notes  
 L'interface de `bad_typeid` est :  
  
```  
class bad_typeid : public exception  
{  
public:  
   bad_typeid(const char * _Message = "bad typeid");  
   bad_typeid(const bad_typeid &);  
   virtual ~bad_typeid();  
};  
```  
  
 L'exemple suivant montre l'opérateur `typeid` levant une exception `bad_typeid`.  
  
```  
// expre_bad_typeid.cpp  
// compile with: /EHsc /GR  
#include <typeinfo.h>  
#include <iostream>  
  
class A{  
public:  
   // object for class needs vtable  
   // for RTTI  
   virtual ~A();  
};  
  
using namespace std;  
int main() {  
A* a = NULL;  
  
try {  
   cout << typeid(*a).name() << endl;  // Error condition  
   }  
catch (bad_typeid){  
   cout << "Object is NULL" << endl;  
   }  
}  
```  
  
## Sortie  
  
```  
Object is NULL  
```  
  
## Voir aussi  
 [Informations de type au moment de l'exécution](../cpp/run-time-type-information.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)