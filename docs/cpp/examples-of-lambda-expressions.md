---
title: "Exemples d&#39;expressions lambda | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "expressions lambda (C++), exemples"
ms.assetid: 52506b15-0771-4190-a966-2f302049ca86
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# Exemples d&#39;expressions lambda
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment utiliser des expressions lambda dans vos programmes.  Pour obtenir une présentation des expressions lambda, consultez [Expressions lambda](../cpp/lambda-expressions-in-cpp.md).  Pour plus d'informations sur la structure d'une expression lambda, consultez [Syntaxe d'expression lambda](../cpp/lambda-expression-syntax.md).  
  
##  <a name="top"></a> Dans cet article  
 [Déclaration d'expressions lambda](#declaringLambdaExpressions)  
  
 [Appel d'expressions lambda](#callingLambdaExpressions)  
  
 [Imbrication d'expressions lambda](#nestingLambdaExpressions)  
  
 [Fonctions lambda d'ordre supérieur](#higherOrderLambdaExpressions)  
  
 [Utilisation d'une expression lambda dans une fonction](#methodLambdaExpressions)  
  
 [Utilisation d'expressions lambda avec des modèles](#templateLambdaExpressions)  
  
 [Gestion des exceptions](#ehLambdaExpressions)  
  
 [Utilisation d'expressions lambda avec des types managés (C++/CLI)](#managedLambdaExpressions)  
  
##  <a name="declaringLambdaExpressions"></a> Déclaration d'expressions lambda  
  
### Exemple 1  
 Une expression lambda étant typée, vous pouvez l'affecter à une variable `auto` ou à un objet de [fonction](../standard-library/function-class.md), comme indiqué dans l'exemple suivant :  
  
### Code  
  
```cpp  
// declaring_lambda_expressions1.cpp  
// compile with: /EHsc /W4  
#include <functional>  
#include <iostream>  
  
int main()  
{  
  
    using namespace std;  
  
    // Assign the lambda expression that adds two numbers to an auto variable.  
    auto f1 = [](int x, int y) { return x + y; };  
  
    cout << f1(2, 3) << endl;  
  
    // Assign the same lambda expression to a function object.  
    function<int(int, int)> f2 = [](int x, int y) { return x + y; };  
  
    cout << f2(3, 4) << endl;  
}  
```  
  
### Sortie  
  **5**  
**7**   
### Notes  
 Pour plus d'informations, consultez [auto](../cpp/auto-cpp.md), [function, classe](../standard-library/function-class.md) et [Appel de fonction](../cpp/function-call-cpp.md).  
  
 Bien que les expressions lambda soient le plus souvent déclarées dans le corps d'une fonction, vous pouvez les déclarer partout où vous pouvez initialiser une variable.  
  
### Exemple 2  
 Le compilateur Visual C\+\+ lie une expression lambda à ses variables capturées lorsque l'expression est déclarée plutôt que lorsque l'expression est appelée.  L'exemple suivant montre une expression lambda qui capture la variable locale `i` par valeur et la variable locale `j` par référence.  Puisque l'expression lambda capture `i` par valeur, la réaffectation de `i` ultérieurement dans le programme n'affecte pas le résultat de l'expression.  Toutefois, puisque l'expression lambda enregistre `j` par référence, la réaffectation de `j` influence le résultat de l'expression.  
  
### Code  
  
```cpp  
// declaring_lambda_expressions2.cpp  
// compile with: /EHsc /W4  
#include <functional>  
#include <iostream>  
  
int main()  
{  
   using namespace std;  
  
   int i = 3;  
   int j = 5;  
  
   // The following lambda expression captures i by value and  
   // j by reference.  
   function<int (void)> f = [i, &j] { return i + j; };  
  
   // Change the values of i and j.  
   i = 22;  
   j = 44;  
  
   // Call f and print its result.  
   cout << f() << endl;  
}  
```  
  
### Sortie  
  **47** \[[Dans cet article](#top)\]  
  
##  <a name="callingLambdaExpressions"></a> Appel d'expressions lambda  
 Vous pouvez appeler une expression lambda immédiatement, comme indiqué dans l'extrait de code suivant.  Le deuxième extrait montre comment transmettre une expression lambda en tant qu'argument des algorithmes STL \(Standard Template Library\) tels que `find_if`.  
  
### Exemple 1  
 Cet exemple déclare une expression lambda qui retourne la somme de deux entiers et appelle l'expression immédiatement avec les arguments `5` et `4`:  
  
### Code  
  
```cpp  
// calling_lambda_expressions1.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main()  
{  
   using namespace std;  
   int n = [] (int x, int y) { return x + y; }(5, 4);  
   cout << n << endl;  
}  
```  
  
### Sortie  
  **9**   
### Exemple 2  
 Cet exemple passe une expression lambda comme argument de la fonction `find_if`.  L'expression lambda retourne `true` si son paramètre est un nombre pair.  
  
### Code  
  
```cpp  
// calling_lambda_expressions2.cpp  
// compile with: /EHsc /W4  
#include <list>  
#include <algorithm>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    // Create a list of integers with a few initial elements.  
    list<int> numbers;  
    numbers.push_back(13);  
    numbers.push_back(17);  
    numbers.push_back(42);  
    numbers.push_back(46);  
    numbers.push_back(99);  
  
    // Use the find_if function and a lambda expression to find the   
    // first even number in the list.  
    const list<int>::const_iterator result =   
        find_if(numbers.begin(), numbers.end(),[](int n) { return (n % 2) == 0; });  
  
    // Print the result.  
    if (result != numbers.end()) {  
        cout << "The first even number in the list is " << *result << "." << endl;  
    } else {  
        cout << "The list contains no even numbers." << endl;  
    }  
}  
```  
  
### Sortie  
  **Le premier nombre pair de la liste est 42.**   
### Notes  
 Pour plus d'informations sur la fonction `find_if`, consultez [find\_if](../Topic/find_if.md).  Pour plus d'informations sur les fonctions STL qui effectuent des algorithmes communs, consultez [\<algorithm\>](../standard-library/algorithm.md).  
  
 \[[Dans cet article](#top)\]  
  
##  <a name="nestingLambdaExpressions"></a> Imbrication d'expressions lambda  
  
### Exemple  
 Vous pouvez imbriquer une expression lambda dans une autre, comme le montre l'exemple suivant.  L'expression lambda interne multiplie son argument par 2 et retourne le résultat.  L'expression lambda externe appelle l'expression lambda interne avec son argument et ajoute 3 au résultat.  
  
### Code  
  
```cpp  
// nesting_lambda_expressions.cpp  
// compile with: /EHsc /W4  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    // The following lambda expression contains a nested lambda  
    // expression.  
    int timestwoplusthree = [](int x) { return [](int y) { return y * 2; }(x) + 3; }(5);  
  
    // Print the result.  
    cout << timestwoplusthree << endl;  
}  
  
```  
  
### Sortie  
  **13**   
### Notes  
 Dans cet exemple, `[](int y) { return y * 2; }` est l'expression lambda imbriquée.  
  
 \[[Dans cet article](#top)\]  
  
##  <a name="higherOrderLambdaExpressions"></a> Fonctions lambda d'ordre supérieur  
  
### Exemple  
 De nombreux langages de programmation prennent en charge le concept de *fonction d'ordre supérieur.* Une fonction d'ordre supérieur est une expression lambda qui prend une autre expression lambda comme argument ou qui retourne une expression lambda.  Utilisez la classe de [fonction](../standard-library/function-class.md) pour permettre à l'expression lambda C\+\+ de se comporter comme une fonction d'ordre supérieur.  L'exemple suivant présente une expression lambda qui retourne un objet `function` et une expression lambda qui prend un objet `function` comme argument.  
  
### Code  
  
```cpp  
// higher_order_lambda_expression.cpp  
// compile with: /EHsc /W4  
#include <iostream>  
#include <functional>  
  
int main()  
{  
    using namespace std;  
  
    // The following code declares a lambda expression that returns   
    // another lambda expression that adds two numbers.   
    // The returned lambda expression captures parameter x by value.  
    auto addtwointegers = [](int x) -> function<int(int)> {   
        return [=](int y) { return x + y; };   
    };  
  
    // The following code declares a lambda expression that takes another  
    // lambda expression as its argument.  
    // The lambda expression applies the argument z to the function f  
    // and multiplies by 2.  
    auto higherorder = [](const function<int(int)>& f, int z) {   
        return f(z) * 2;   
    };  
  
    // Call the lambda expression that is bound to higherorder.   
    auto answer = higherorder(addtwointegers(7), 8);  
  
    // Print the result, which is (7+8)*2.  
    cout << answer << endl;  
}  
  
```  
  
### Sortie  
  **30** \[[Dans cet article](#top)\]  
  
##  <a name="methodLambdaExpressions"></a> Utilisation d'une expression lambda dans une fonction  
  
### Exemple  
 Vous pouvez utiliser les expressions lambda dans le corps d'une fonction.  L'expression lambda peut accéder à toute donnée membre ou fonction accessible à la fonction englobante.  Vous pouvez explicitement ou implicitement capturer le pointeur `this` pour fournir l'accès aux fonctions et données membres de la classe englobante.  
  
 Vous pouvez utiliser le pointeur `this` explicitement dans une fonction, comme indiqué ci\-dessous :  
  
```cpp  
void ApplyScale(const vector<int>& v) const  
{  
   for_each(v.begin(), v.end(),   
      [this](int n) { cout << n * _scale << endl; });  
}  
```  
  
 Vous pouvez également capturer le pointeur `this` implicitement :  
  
```  
void ApplyScale(const vector<int>& v) const  
{  
   for_each(v.begin(), v.end(),   
      [=](int n) { cout << n * _scale << endl; });  
}  
```  
  
 L'exemple suivant montre la classe `Scale`, qui encapsule une valeur d'échelle.  
  
```cpp  
// function_lambda_expression.cpp  
// compile with: /EHsc /W4  
#include <algorithm>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Scale  
{  
public:  
    // The constructor.  
    explicit Scale(int scale) : _scale(scale) {}  
  
    // Prints the product of each element in a vector object   
    // and the scale value to the console.  
    void ApplyScale(const vector<int>& v) const  
    {  
        for_each(v.begin(), v.end(), [=](int n) { cout << n * _scale << endl; });  
    }  
  
private:  
    int _scale;  
};  
  
int main()  
{  
    vector<int> values;  
    values.push_back(1);  
    values.push_back(2);  
    values.push_back(3);  
    values.push_back(4);  
  
    // Create a Scale object that scales elements by 3 and apply  
    // it to the vector object. Does not modify the vector.  
    Scale s(3);  
    s.ApplyScale(values);  
}  
  
```  
  
### Sortie  
  **3**  
**6**  
**9**  
**12**   
### Notes  
 La fonction `ApplyScale` utilise une expression lambda pour imprimer le produit de la valeur d'échelle et de chaque élément d'un objet `vector`.  L'expression lambda capture implicitement le pointeur `this` afin qu'elle puisse accéder au membre `_scale`.  
  
 \[[Dans cet article](#top)\]  
  
##  <a name="templateLambdaExpressions"></a> Utilisation d'expressions lambda avec des modèles  
  
### Exemple  
 Les expressions lambda étant typées, vous pouvez les utiliser avec des modèles C\+\+.  L'exemple suivant illustre les fonctions `negate_all` et `print_all`.  La fonction `negate_all` applique l'opérateur `operator-` unaire à chaque élément de l'objet `vector`.  La fonction `print_all` affiche chaque élément de l'objet `vector` sur la console.  
  
### Code  
  
```cpp  
// template_lambda_expression.cpp  
// compile with: /EHsc  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
// Negates each element in the vector object. Assumes signed data type.  
template <typename T>  
void negate_all(vector<T>& v)  
{  
    for_each(v.begin(), v.end(), [](T& n) { n = -n; });  
}  
  
// Prints to the console each element in the vector object.  
template <typename T>  
void print_all(const vector<T>& v)  
{  
    for_each(v.begin(), v.end(), [](const T& n) { cout << n << endl; });  
}  
  
int main()  
{  
    // Create a vector of signed integers with a few elements.  
    vector<int> v;  
    v.push_back(34);  
    v.push_back(-43);  
    v.push_back(56);  
  
    print_all(v);  
    negate_all(v);  
    cout << "After negate_all():" << endl;  
    print_all(v);  
}  
  
```  
  
### Sortie  
  **34**  
**\-43**  
**56**  
**Après negate\_all\(\) :**  
**\-34**  
**43**  
**\-56**   
### Notes  
 Pour plus d'informations sur les modèles C\+\+, consultez [Modèles](../cpp/templates-cpp.md).  
  
 \[[Dans cet article](#top)\]  
  
##  <a name="ehLambdaExpressions"></a> Gestion des exceptions  
  
### Exemple  
 Le corps d'une expression lambda suit les règles de la gestion structurée des exceptions \(SEH\) et la gestion des exceptions C\+\+.  Vous pouvez gérer une exception levée dans le corps d'une expression lambda ou différer la gestion des exceptions dans la portée englobante.  L'exemple suivant utilise la fonction `for_each` et une expression lambda pour remplir un objet `vector` avec les valeurs d'un autre.  Il utilise un bloc `try`\/`catch` pour gérer l'accès non valide au premier vecteur.  
  
### Code  
  
```cpp  
// eh_lambda_expression.cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <algorithm>  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    // Create a vector that contains 3 elements.  
    vector<int> elements(3);  
  
    // Create another vector that contains index values.  
    vector<int> indices(3);  
    indices[0] = 0;  
    indices[1] = -1; // This is not a valid subscript. It will trigger an exception.  
    indices[2] = 2;  
  
    // Use the values from the vector of index values to   
    // fill the elements vector. This example uses a   
    // try/catch block to handle invalid access to the   
    // elements vector.  
    try  
    {  
        for_each(indices.begin(), indices.end(), [&](int index) {   
            elements.at(index) = index;   
        });  
    }  
    catch (const out_of_range& e)  
    {  
        cerr << "Caught '" << e.what() << "'." << endl;  
    };  
}  
```  
  
### Sortie  
  **Caught 'invalid vector\<T\> subscript'.**   
### Notes  
 Pour plus d'informations sur la gestion des exceptions, consultez [Gestion des exceptions](../cpp/exception-handling-in-visual-cpp.md).  
  
 \[[Dans cet article](#top)\]  
  
##  <a name="managedLambdaExpressions"></a> Utilisation d'expressions lambda avec des types managés \(C\+\+\/CLI\)  
  
### Exemple  
 La clause de capture d'une expression lambda ne peut pas contenir une variable qui a un type managé.  Toutefois, vous pouvez passer un argument qui a un type managé dans la liste de paramètres d'une expression lambda.  L'exemple suivant contient une expression lambda qui capture la variable non managée locale `ch` par valeur et prend un objet <xref:System.String?displayProperty=fullName> comme paramètre.  
  
### Code  
  
```cpp  
// managed_lambda_expression.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
    char ch = '!'; // a local unmanaged variable  
  
    // The following lambda expression captures local variables  
    // by value and takes a managed String object as its parameter.  
    [=](String ^s) {   
        Console::WriteLine(s + Convert::ToChar(ch));   
    }("Hello");  
}  
  
```  
  
### Sortie  
  **Hello\!**   
### Notes  
 Vous pouvez également utiliser vos expressions lambda avec la bibliothèque STL\/CLR.  Pour plus d'informations, consultez [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md).  
  
> [!IMPORTANT]
>  Les expressions lambda ne sont pas prises en charge dans les entités managées suivantes du CLR \(Common Langage Runtime\) : `ref class`, `ref struct`, `value class` et `value struct`.  
  
 \[[Dans cet article](#top)\]  
  
## Voir aussi  
 [Expressions lambda](../cpp/lambda-expressions-in-cpp.md)   
 [Syntaxe d'expression lambda](../cpp/lambda-expression-syntax.md)   
 [auto](../cpp/auto-cpp.md)   
 [function, classe](../standard-library/function-class.md)   
 [find\_if](../Topic/find_if.md)   
 [\<algorithm\>](../standard-library/algorithm.md)   
 [Appel de fonction](../cpp/function-call-cpp.md)   
 [Modèles](../cpp/templates-cpp.md)   
 [Gestion des exceptions](../cpp/exception-handling-in-visual-cpp.md)   
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)