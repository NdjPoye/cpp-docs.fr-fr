---
title: Fonction d’appel (C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function calls, C++ functions
- functions [C++], calling
- operator overloading [C++], function calls
- function overloading [C++], function-call operator
- function calls, operator
- operators [C++], overloading
- operator overloading [C++], examples
- function call operator ()
ms.assetid: 5094254a-045b-46f7-8653-69bc91e80dce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85e7a752630b391d09140fa7552a452b3d2b751a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="function-call-c"></a>Appel de fonction (C++)
L'opérateur d'appel de fonction, invoqué à l'aide de parenthèses, est un opérateur binaire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
primary-expression ( expression-list )  
```  
  
## <a name="remarks"></a>Notes  
 Dans ce contexte, `primary-expression` est le premier opérande et `expression-list`, une liste d'arguments éventuellement vide, est le deuxième opérande. L'opérateur d'appel de fonction est utilisé pour les opérations nécessitant un certain nombre de paramètres. Cela fonctionne car `expression-list` est une liste et non un opérande unique. L'opérateur d'appel de fonction doit être une fonction membre non statique.  
  
 L'opérateur d'appel de fonction, quand il est surchargé, ne modifie pas la façon dont les fonctions sont appelées, mais la façon dont l'opérateur doit être interprété quand il est appliqué aux objets d'un type de classe donné. Par exemple, le code suivant n'a généralement pas de signification :  
  
```  
Point pt;  
pt( 3, 2 );  
```  
  
 Toutefois, pour un opérateur d'appel de fonction surchargé approprié donné, cette syntaxe peut être utilisée pour décaler de 3 unités la coordonnée `x` et de 2 unités la coordonnée `y`. Le code suivant illustre ce type de définition :  
  
```  
// function_call.cpp  
class Point  
{  
public:  
    Point() { _x = _y = 0; }  
    Point &operator()( int dx, int dy )  
        { _x += dx; _y += dy; return *this; }  
private:  
    int _x, _y;  
};  
  
int main()  
{  
   Point pt;  
   pt( 3, 2 );  
}  
```  
  
 Notez que l'opérateur d'appel de fonction est appliqué au nom d'un objet et non à celui d'une fonction.  
  
 Vous pouvez aussi surcharger l'opérateur d'appel de fonction à l'aide d'un pointeur vers une fonction (et non la fonction elle-même).  
  
```cpp  
typedef void(*ptf)();  
void func()  
{  
}  
struct S  
{  
   operator ptf()  
   {  
      return func;  
   }  
};  
  
int main()  
{  
   S s;  
   s();//operates as s.operator ptf()()  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Surcharge d'opérateur](../cpp/operator-overloading.md)