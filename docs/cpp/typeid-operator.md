---
title: typeid (opérateur) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- typeid operator
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b27f3bcb7358b3ea05907df1a4372c107538dfb4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="typeid-operator"></a>typeid, opérateur
## <a name="syntax"></a>Syntaxe  
  
```  
  
      typeid(   
      type-id  
       )  
typeid( expression )  
```  
  
## <a name="remarks"></a>Notes  
 L'opérateur `typeid` permet de déterminer le type d'un objet au moment de l'exécution.  
  
 Le résultat de `typeid` est un **const type_info &**. La valeur est une référence à un **type_info** objet qui représente soit le *id de type* ou le type de la *expression*, en fonction de la forme de `typeid` est utilisé . Consultez [classe type_info](../cpp/type-info-class.md) pour plus d’informations.  
  
 Le `typeid` opérateur ne fonctionne pas avec les types managés (déclarateurs abstraits ou instances), consultez [typeid](../windows/typeid-cpp-component-extensions.md) pour plus d’informations sur l’obtention de la <xref:System.Type> d’un type spécifié.  
  
 L'opérateur `typeid` effectue un contrôle à l'exécution lorsqu'il est appliqué à une l-value d'un type de classe polymorphe, où le type réel de l'objet ne peut pas être déterminé par les informations statiques fournies. Dans les cas suivants par exemple :  
  
-   Une référence à une classe  
  
-   Un pointeur, déréférencé avec *  
  
-   Un pointeur indicé ([ ] par exemple). (Notez qu'il n'est généralement pas possible d'utiliser un indice avec un pointeur vers un type polymorphe.)  
  
 Si le *expression* pointe vers un type de classe de base, l’objet est réellement d’un type dérivé de cette classe de base, un **type_info** référence de la classe dérivée est le résultat. Le *expression* doit pointer vers un type polymorphe (une classe avec des fonctions virtuelles). Dans le cas contraire, le résultat est le **type_info** pour la classe statique référencée dans le *expression*. De plus, le pointeur doit être déréférencé afin que l'objet qu'il pointe soit utilisé. Sans le déréférencement du pointeur, le résultat sera le **type_info** du pointeur, pas à ce qu’il pointe vers. Exemple :  
  
```  
// expre_typeid_Operator.cpp  
// compile with: /GR /EHsc  
#include <iostream>  
#include <typeinfo.h>  
  
class Base {  
public:  
   virtual void vvfunc() {}  
};  
  
class Derived : public Base {};  
  
using namespace std;  
int main() {  
   Derived* pd = new Derived;  
   Base* pb = pd;  
   cout << typeid( pb ).name() << endl;   //prints "class Base *"  
   cout << typeid( *pb ).name() << endl;   //prints "class Derived"  
   cout << typeid( pd ).name() << endl;   //prints "class Derived *"  
   cout << typeid( *pd ).name() << endl;   //prints "class Derived"  
   delete pd;  
}  
```  
  
 Si le *expression* la référence à un pointeur, et que la valeur du pointeur est égal à zéro, **typeid** lève une [bad_typeid (exception)](../cpp/bad-typeid-exception.md). Si le pointeur ne pointe pas vers un objet valide, un `__non_rtti_object` exception est levée, indiquant une tentative d’analyse du RTTI qui a déclenché une erreur (telles que la violation d’accès), car l’objet n’est pas valide d’une certaine manière (pointeur incorrect ou le code n’a pas été compilé avec [/GR](../build/reference/gr-enable-run-time-type-information.md)).  
  
 Si le *expression* n’est ni un pointeur ni une référence à une classe de base de l’objet, le résultat est un **type_info** référence qui représente le type statique de la *expression*. Le *type statique* d’une expression désigne le type d’une expression telle qu’il est connu au moment de la compilation. Les sémantiques d'exécution sont ignorées en évaluant le type statique d'une expression. De plus, les références sont ignorées si possible lors de la détermination du type statique d'une expression :  
  
```  
// expre_typeid_Operator_2.cpp  
#include <typeinfo>  
  
int main()  
{  
   typeid(int) == typeid(int&); // evaluates to true  
}  
```  
  
 **typeid** peut également être utilisé dans les modèles de pour déterminer le type d’un paramètre de modèle :  
  
```  
// expre_typeid_Operator_3.cpp  
// compile with: /c  
#include <typeinfo>  
template < typename T >   
T max( T arg1, T arg2 ) {  
   cout << typeid( T ).name() << "s compared." << endl;  
   return ( arg1 > arg2 ? arg1 : arg2 );  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de type au moment de l’exécution](../cpp/run-time-type-information.md)   
 [Mots clés](../cpp/keywords-cpp.md)