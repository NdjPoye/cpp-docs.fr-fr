---
title: bad_typeid, Exception | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bad_typeid
- bad_typeid_cpp
dev_langs:
- C++
helpviewer_keywords:
- bad_typeid exception
- exceptions [C++], bad_typeid
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: ea7dc85862622180038cf520ef92b752b65eba84
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="badtypeid-exception"></a>bad_typeid, exception
Le `bad_typeid` exception est levée par le [opérateur typeid](../cpp/typeid-operator.md) lorsque l’opérande de `typeid` est un pointeur NULL.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      catch (bad_typeid)  
   statement  
```  
  
## <a name="remarks"></a>Remarques  
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
  
## <a name="output"></a>Sortie  
  
```  
Object is NULL  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de type au moment de l’exécution](../cpp/run-time-type-information.md)   
 [Mots clés](../cpp/keywords-cpp.md)
