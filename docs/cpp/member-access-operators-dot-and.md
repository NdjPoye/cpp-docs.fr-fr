---
title: "Opérateurs d’accès au membre :. et -&gt; | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- .
- ->
dev_langs:
- C++
helpviewer_keywords:
- member access, expressions
- operators [C++], member access
- dot operator (.)
- -> operator
- member access, operators
- postfix operators [C++]
- . operator
- member access
ms.assetid: f8fc3df9-d728-40c5-b384-276927f5f1b3
caps.latest.revision: 11
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
ms.openlocfilehash: 7c4e69727c474cb89f931832da2dbde6e20c16b9
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="member-access-operators--and--gt"></a>Opérateurs d’accès au membre :. et -&gt;
## <a name="syntax"></a>Syntaxe  
  
```  
postfix-expression . name  
postfix-expression -> name  
```  
  
## <a name="remarks"></a>Remarques  
 Les opérateurs d’accès au membre **.** et ** -> ** sont utilisés pour faire référence aux membres de classes, structures et unions. Les expressions d’accès au membre ont la valeur et le type du membre sélectionné.  
  
 Il existe deux formes d’expressions d’accès au membre :  
  
1.  Dans la première forme, *postfix-expression* représente une valeur de type d’union, classe ou struct et *nom* désigne un membre de la structure spécifiée, union ou classe. La valeur de l’opération est celle de *nom* et est une l-value Si *postfix-expression* est une l-value.  
  
2.  Dans la deuxième forme *postfix-expression* représente un pointeur vers une structure, union ou classe, et *nom* désigne un membre de la structure spécifiée, union ou classe. La valeur est celle de *nom* et est une l-value. Le ** -> ** opérateur de déréférence le pointeur. Par conséquent, les expressions *e* ** -> ** `member` et **(\****e***)**.`member` (où *e* représente un pointeur) produisent des résultats identiques (sauf lorsque les opérateurs ** -> ** ou ** \* ** sont surchargées).  
  
## <a name="example"></a>Exemple  
 L'exemple suivant illustre les deux formes de l'opérateur d'accès aux membres.  
  
```  
// expre_Selection_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct Date {  
   Date(int i, int j, int k) : day(i), month(j), year(k){}  
   int month;  
   int day;  
   int year;  
};  
  
int main() {  
   Date mydate(1,1,1900);  
   mydate.month = 2;     
   cout  << mydate.month << "/" << mydate.day  
         << "/" << mydate.year << endl;  
  
   Date *mydate2 = new Date(1,1,2000);  
   mydate2->month = 2;  
   cout  << mydate2->month << "/" << mydate2->day  
         << "/" << mydate2->year << endl;  
   delete mydate2;  
}  
```  
  
```Output  
2/1/1900  
2/1/2000  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions suffixées](../cpp/postfix-expressions.md)   
 [Les opérateurs C++ intégrés, priorité et associativité](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Classes et structs](../cpp/classes-and-structs-cpp.md)   
 [Structure et membres d’union](../c-language/structure-and-union-members.md)
