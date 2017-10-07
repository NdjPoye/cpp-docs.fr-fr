---
title: "Opérateur de Conversion de Type explicite : () | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- explicit data type conversion operator
- conversions [C++], explicit
- operators [C++], explicit type conversion
- data type conversion [C++], explicit
- type conversion [C++], explicit conversions
ms.assetid: 54272006-5ffb-45ed-8283-27152ab97529
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 09afbed7f5a399b9ca192ff57be1c866baf59626
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="explicit-type-conversion-operator-"></a>Opérateur de conversions de type explicite : ()
C++ permet de convertir en type explicite à l'aide d'une syntaxe similaire à la syntaxe de l'appel de fonction.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
simple-type-name ( expression-list )  
```  
  
## <a name="remarks"></a>Remarques  
 A *simple-type-name* suivie d’une *expression-list* placé entre parenthèses construit un objet du type spécifié à l’aide d’expressions spécifiées. L'exemple suivant montre une conversion de type explicite en type int :  
  
```  
int i = int( d );  
```  
  
 L’exemple suivant montre un `Point` classe.  
  
## <a name="example"></a>Exemple  
  
```  
// expre_Explicit_Type_Conversion_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class Point  
{  
public:  
    // Define default constructor.  
    Point() { _x = _y = 0; }  
    // Define another constructor.  
    Point( int X, int Y ) { _x = X; _y = Y; }  
  
    // Define "accessor" functions as  
    // reference types.  
    unsigned& x() { return _x; }  
    unsigned& y() { return _y; }  
    void Show()   { cout << "x = " << _x << ", "  
                         << "y = " << _y << "\n"; }  
private:  
    unsigned _x;  
    unsigned _y;  
};  
  
int main()  
{  
    Point Point1, Point2;  
  
    // Assign Point1 the explicit conversion  
    //  of ( 10, 10 ).  
    Point1 = Point( 10, 10 );  
  
    // Use x() as an l-value by assigning an explicit  
    //  conversion of 20 to type unsigned.  
    Point1.x() = unsigned( 20 );  
    Point1.Show();  
  
    // Assign Point2 the default Point object.  
    Point2 = Point();  
    Point2.Show();  
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
x = 20, y = 10  
x = 0, y = 0  
```  
  
 Bien que l'exemple précédent montre la conversion de type explicite à l'aide de constantes, la même technique fonctionne pour exécuter ces conversions sur des objets. Le fragment de code suivant illustre ceci :  
  
```  
int i = 7;  
float d;  
  
d = float( i );  
```  
  
 Les conversions de types explicites peuvent également être spécifiées en utilisant la syntaxe du cast. L'exemple précédent, réécrit à l'aide de la syntaxe du cast, est :  
  
```  
d = (float)i;  
```  
  
 Les conversions de style cast et fonction ont les mêmes résultats en convertissant à partir de valeurs uniques. Toutefois, dans la syntaxe de style fonction, vous pouvez spécifier plusieurs arguments pour la conversion. Cette différence est importante pour les types définis par l'utilisateur. Prenons une classe `Point` et ses conversions :  
  
```  
struct Point  
{  
    Point( short x, short y ) { _x = x; _y = y; }  
    ...  
    short _x, _y;  
};  
...  
Point pt = Point( 3, 10 );  
```  
  
 L’exemple précédent, qui utilise la conversion de style fonction, montre comment convertir des valeurs de deux (une pour *x* et l’autre pour *y*) pour le type défini par l’utilisateur `Point`.  
  
> [!CAUTION]
>  Utilisez les conversions de type explicites avec précaution, car elles remplacent la vérification de type intégrée du compilateur C++.  
  
 Le [cast](../cpp/cast-operator-parens.md) notation doit être utilisée pour les conversions de types qui n’ont pas un *simple-type-name* (types pointeur ou référence, par exemple). Conversion des types qui peuvent être exprimées avec un *simple-type-name* peuvent être écrites dans un formulaire. Consultez [spécificateurs de Type](http://msdn.microsoft.com/en-us/34b6c737-0ef1-4470-9b77-b26e46c0bbd4) pour plus d’informations sur ce qui constitue une *simple-type-name*.  
  
 La définition de type avec des casts n'est pas conforme.  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions suffixées](../cpp/postfix-expressions.md)   
 [Opérateurs intégrés, priorité et associativité C++](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
