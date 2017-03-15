---
title: "typeid, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "typeid (opérateur)"
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# typeid, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
      typeid(   
      type-id  
       )  
typeid( expression )  
```  
  
## Notes  
 L'opérateur `typeid` permet de déterminer le type d'un objet au moment de l'exécution.  
  
 Le résultat de `typeid` est **const type\_info&**.  La valeur est une référence à un objet **type\_info** qui représente soit l'*ID type* soit le type de l'*expression*, selon la forme de `typeid` utilisée.  Consultez [classe type\_info](../cpp/type-info-class.md) pour plus d'informations.  
  
 L'opérateur `typeid` ne fonctionne pas avec les types managés \(les déclarateurs abstraits ou les instances\), consultez [typeid](../windows/typeid-cpp-component-extensions.md) pour plus d'informations sur l'obtention de <xref:System.Type> d'un type spécifié.  
  
 L'opérateur `typeid` effectue un contrôle à l'exécution lorsqu'il est appliqué à une l\-value d'un type de classe polymorphe, où le type réel de l'objet ne peut pas être déterminé par les informations statiques fournies.  Dans les cas suivants par exemple :  
  
-   Une référence à une classe  
  
-   Un pointeur, déréférencé avec \*  
  
-   Un pointeur indicé \(\[ \] par exemple\). \(Notez qu'il n'est généralement pas possible d'utiliser un indice avec un pointeur vers un type polymorphe.\)  
  
 Si l'*expression* pointe vers un type classe de base, l'objet est en fait d'un type dérivé de cette classe de base, une référence **type\_info** de la classe dérivée est le résultat.  L'*expression* doit pointer vers un type polymorphe \(une classe avec des fonctions virtuelles\).  Sinon, le résultat est **type\_info** pour la classe statique référencée dans l'*expression*.  De plus, le pointeur doit être déréférencé afin que l'objet qu'il pointe soit utilisé.  Si le pointeur n'est pas déréférencé, le résultat sera le **type\_info** du pointeur, et pas ce qu'il désigne.  Par exemple :  
  
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
  
 Si l'*expression* déréférence un pointeur, et que cette valeur du pointeur est zéro, **typeid** lève une exception [bad\_typeid](../cpp/bad-typeid-exception.md).  Si le pointeur ne pointe par vers un objet valide, une exception `__non_rtti_object` est levée, indiquant une tentative d'analyse du RTTI qui a déclenché une erreur \(comme la violation d'accès\), car l'objet est d'une certaine façon non valide \(le pointeur incorrect ou le code n'a pas été compilé avec [\/GR](../build/reference/gr-enable-run-time-type-information.md)\).  
  
 Si l'*expression* n'est ni un pointeur ni une référence à une classe de base de l'objet, le résultat est une référence **type\_info** représentant le type statique de l'*expression*.  *Le type statique* d'une expression fait référence au type d'une expression telle qu'elle est connue au moment de la compilation.  Les sémantiques d'exécution sont ignorées en évaluant le type statique d'une expression.  De plus, les références sont ignorées si possible lors de la détermination du type statique d'une expression :  
  
```  
// expre_typeid_Operator_2.cpp  
#include <typeinfo>  
  
int main()  
{  
   typeid(int) == typeid(int&); // evaluates to true  
}  
```  
  
 **typeid** peut également être utilisé dans des modèles pour déterminer le type d'un paramètre de modèle :  
  
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
  
## Voir aussi  
 [Informations de type au moment de l'exécution](../cpp/run-time-type-information.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)