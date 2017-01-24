---
title: "Op&#233;rateur d&#39;appel de fonction&#160;: () | Microsoft Docs"
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
  - "( ) appel de fonction (opérateur)"
  - "() appel de fonction (opérateur)"
  - "appel de fonction ( ) (opérateur)"
  - "appels de fonction, fonctions C++"
  - "appels de fonction, d'opérateur"
  - "fonctions (C++), opérateur d'appel de fonction"
  - "opérateurs suffixés"
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateur d&#39;appel de fonction&#160;: ()
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une expression suffixée suivie de l'opérateur d'appel de fonction, **\( \)**, spécifie un appel de fonction.  
  
## Syntaxe  
  
```  
  
postfix-expression   
( [argument-expression-list ] )  
```  
  
## Notes  
 Les arguments de l'opérateur d'appel de fonction sont zéro expression ou plus séparées par des virgules, les arguments réels de la fonction.  
  
 *postfix\-expression* doit prendre la valeur d'une adresse de fonction \(par exemple, un identificateur de fonction ou la valeur d'un pointeur fonction\), et *argument\-expression\-list* est une liste d'expressions \(séparées par des virgules\) dont les valeurs \(les arguments\) sont passées à la fonction.  L'argument *argument\-expression\-list* peut être vide.  
  
 *postfix\-expression* doit être un des types suivants :  
  
-   Fonction retournant le type `T`.  Voici un exemple de déclaration  
  
    ```  
    T func( int i )  
    ```  
  
-   Pointeur d'une fonction qui retourne le type `T`.  Voici un exemple de déclaration  
  
    ```  
    T (*func)( int i )  
    ```  
  
-   Référence à une fonction qui retourne le type `T`.  Voici un exemple de déclaration  
  
    ```  
    T (&func)(int i)  
    ```  
  
-   Déréférencement de fonction de pointeur de membre qui retourne le type `T`.  Voici des exemples d'appels de fonction  
  
    ```  
    (pObject->*pmf)();  
    (Object.*pmf)();  
    ```  
  
## Exemple  
 L'exemple suivant appelle la fonction de bibliothèque standard `strcat_s` avec trois arguments :  
  
```  
// expre_Function_Call_Operator.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string>  
  
// STL name space  
using namespace std;  
  
int main()  
{  
    enum  
    {  
        sizeOfBuffer = 20  
    };  
  
    char s1[ sizeOfBuffer ] = "Welcome to ";  
    char s2[ ] = "C++";  
  
    strcat_s( s1, sizeOfBuffer, s2 );  
  
    cout << s1 << endl;  
}  
```  
  
  **Bienvenue dans C\+\+**   
## Résultats de l'appel de fonction  
 Un appel de fonction prend une r\-value, sauf si la fonction est déclarée en tant que type de référence.  Les fonctions avec type de retour de référence ont des l\-values et peuvent être utilisées à gauche d'une instruction d'assignation, comme suit :  
  
```  
// expre_Function_Call_Results.cpp  
// compile with: /EHsc  
#include <iostream>  
class Point  
{  
public:  
    // Define "accessor" functions as  
    // reference types.  
    unsigned& x() { return _x; }  
    unsigned& y() { return _y; }  
private:  
    unsigned _x;  
    unsigned _y;  
};  
  
using namespace std;  
int main()  
{  
    Point ThePoint;  
  
    ThePoint.x() = 7;           // Use x() as an l-value.  
    unsigned y = ThePoint.y();  // Use y() as an r-value.  
  
    // Use x() and y() as r-values.  
    cout << "x = " << ThePoint.x() << "\n"  
         << "y = " << ThePoint.y() << "\n";  
}  
```  
  
 Le code précédent définit une classe appelée `Point`, qui contient les objets de données privés qui représentent les coordonnées *x* et *y*.  Ces objets de données doivent être modifiés et leurs valeurs, récupérées.  Ce programme n'est qu'une des nombreuses conceptions de ce type de classe ; l'utilisation des fonctions `GetX` et `SetX` ou `GetY` et `SetY` est une autre conception possible.  
  
 Les fonctions qui retournent des types de classe, des pointeurs vers des types de classe ou des références à des types de classe peuvent être utilisées comme opérande gauche pour les opérateurs de sélection de membres.  Par conséquent, le code suivant est conforme :  
  
```  
// expre_Function_Results2.cpp  
class A {  
public:  
   A() {}  
   A(int i) {}  
   int SetA( int i ) {  
      return (I = i);  
   }  
  
   int GetA() {  
      return I;  
   }  
  
private:  
   int I;  
};  
  
A func1() {  
   A a = 0;  
   return a;  
}  
  
A* func2() {  
   A *a = new A();  
   return a;  
}  
  
A& func3() {  
   A *a = new A();  
   A &b = *a;  
   return b;  
}  
  
int main() {  
   int iResult = func1().GetA();  
   func2()->SetA( 3 );  
   func3().SetA( 7 );  
}  
```  
  
 Les fonctions peuvent être appelées de manière récursive.  Pour plus d'informations sur les déclarations de fonction, consultez [Spécificateurs de fonction](../misc/function-specifiers.md) et [Fonctions membres](../misc/member-functions-cpp.md).  La documentation connexe est disponible dans [Programme et liaison](../cpp/program-and-linkage-cpp.md).  
  
## Voir aussi  
 [Expressions suffixées](../cpp/postfix-expressions.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Appel de fonction](../c-language/function-call-c.md)   
 [\(NOTINBUILD\) Function Declarations](http://msdn.microsoft.com/fr-fr/3f9b4e14-60d2-47c1-acd8-4fa8fc988be7)