---
title: "Op&#233;rateur de conversions de type explicite&#160;: () | Microsoft Docs"
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
  - "conversions (C++), explicites"
  - "conversion de type de données (C++), explicites"
  - "opérateur de conversions de types de données explicites"
  - "opérateurs (C++), conversion de type explicite"
  - "conversion de type (C++), conversions explicites"
ms.assetid: 54272006-5ffb-45ed-8283-27152ab97529
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateur de conversions de type explicite&#160;: ()
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ permet de convertir en type explicite à l'aide d'une syntaxe similaire à la syntaxe de l'appel de fonction.  
  
## Syntaxe  
  
```  
  
simple-type-name ( expression-list )  
```  
  
## Notes  
 *simple\-type\-name* suivi d'un *expression\-list* placé entre parenthèses construit un objet du type spécifié à l'aide des expressions spécifiées.  L'exemple suivant montre une conversion de type explicite en type int :  
  
```  
int i = int( d );  
```  
  
 L'exemple suivant utilise une version modifiée de la classe `Point` définie dans [Résultats de l'appel de fonction](../misc/function-call-results.md).  
  
## Exemple  
  
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
  
## Sortie  
  
```  
x = 20, y = 10  
x = 0, y = 0  
```  
  
 Bien que l'exemple précédent montre la conversion de type explicite à l'aide de constantes, la même technique fonctionne pour exécuter ces conversions sur des objets.  Le fragment de code suivant illustre ceci :  
  
```  
int i = 7;  
float d;  
  
d = float( i );  
```  
  
 Les conversions de types explicites peuvent également être spécifiées en utilisant la syntaxe du cast.  L'exemple précédent, réécrit à l'aide de la syntaxe du cast, est :  
  
```  
d = (float)i;  
```  
  
 Les conversions de style cast et fonction ont les mêmes résultats en convertissant à partir de valeurs uniques.  Toutefois, dans la syntaxe de style fonction, vous pouvez spécifier plusieurs arguments pour la conversion.  Cette différence est importante pour les types définis par l'utilisateur.  Prenons une classe `Point` et ses conversions :  
  
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
  
 L'exemple précédent, qui utilise la conversion de style fonction, montre comment convertir deux valeurs \(une pour *x* et une pour *y\)* vers le type `Point` défini par l'utilisateur.  
  
> [!CAUTION]
>  Utilisez les conversions de type explicites avec précaution, car elles remplacent la vérification de type intégrée du compilateur C\+\+.  
  
 La notation [cast](../cpp/cast-operator-parens.md) doit être utilisée pour les conversions vers les types qui n'ont pas de *simple\-type\-name* \(types pointeur ou référence, par exemple\).  La conversion en types qui peut être exprimée avec un *simple\-type\-name* peut être écrite sous l'une des deux formes.  Consultez [Spécificateurs de type](http://msdn.microsoft.com/fr-fr/34b6c737-0ef1-4470-9b77-b26e46c0bbd4) pour plus d'informations sur ce qui constitue un *simple\-type\-name*.  
  
 La définition de type avec des casts n'est pas conforme.  
  
## Voir aussi  
 [Expressions suffixées](../cpp/postfix-expressions.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)