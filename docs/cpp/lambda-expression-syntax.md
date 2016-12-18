---
title: "Syntaxe d&#39;expression lambda | Microsoft Docs"
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
  - "VCF1 Lambda_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "expressions lambda (C++), syntaxe"
ms.assetid: 5d6154a4-f34d-4a15-970d-7e7de45f54e9
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Syntaxe d&#39;expression lambda
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article décrit la syntaxe et les éléments structuraux des expressions lambda.  Pour obtenir une description des expressions lambda, consultez [Expressions lambda](../cpp/lambda-expressions-in-cpp.md).  
  
## Objets de fonction comparés aux expressionsLambdas  
 Lorsque vous écrivez du code, vous utilisez probablement des pointeurs de fonction et des objets de fonction pour résoudre des problèmes et effectuer des calculs, surtout lorsque vous utilisez des [algorithmes STL](../cpp/algorithms-modern-cpp.md).  Les pointeurs de fonction et les objets de fonction présentent chacun des avantages et des inconvénients. Par exemple, les pointeurs de fonction possèdent une charge mémoire syntaxique minimale, mais leur état n'est pas conservé au sein d'une portée. Les objets de fonction, quant à eux, peuvent conserver leur état, mais ils nécessitent la charge mémoire syntaxique d'une définition de classe.  
  
 Une expression lambda combine les avantages des pointeurs et des objets de fonction, tout en évitant leurs inconvénients.  Tout comme les objets de fonction, les expressions lambda sont flexibles et peuvent conserver leur état. Toutefois, contrairement aux objets de fonction, leur syntaxe compacte ne requiert pas de définition de classe explicite.  Grâce aux expressions lambda, votre code est moins encombré et moins sujet aux erreurs que le code nécessaire pour un objet de fonction équivalent.  
  
 Les exemples suivants comparent l'utilisation d'une expression lambda et d'un objet de fonction.  Le premier exemple utilise une expression lambda pour afficher sur la console si chaque élément d'un objet `vector` est pair ou impair.  Le deuxième exemple utilise un objet de fonction pour accomplir la même tâche.  
  
## Exemple 1 : Utilisation d'une expression lambda  
 Cet exemple passe une expression lambda à la fonction `for_each`.  L'expression lambda imprime un résultat qui indique si chaque élément dans un objet `vector` est pair ou impair.  
  
### Code  
  
```cpp  
// even_lambda.cpp  
// compile with: cl /EHsc /nologo /W4 /MTd  
#include <algorithm>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
int main()   
{  
   // Create a vector object that contains 10 elements.  
   vector<int> v;  
   for (int i = 1; i < 10; ++i) {  
      v.push_back(i);  
   }  
  
   // Count the number of even numbers in the vector by   
   // using the for_each function and a lambda.  
   int evenCount = 0;  
   for_each(v.begin(), v.end(), [&evenCount] (int n) {  
      cout << n;  
      if (n % 2 == 0) {  
         cout << " is even " << endl;  
         ++evenCount;  
      } else {  
         cout << " is odd " << endl;  
      }  
   });  
  
   // Print the count of even numbers to the console.  
   cout << "There are " << evenCount   
        << " even numbers in the vector." << endl;  
}  
```  
  
### Sortie  
  **1 est impair**  
**2 est pair**  
**3 est impair**  
**4 est pair**  
**5 est impair**  
**6 est pair**  
**7 est impair**  
**8 est pair**  
**9 est impair**  
**Le vecteur contient 4 nombres pairs.**   
### Commentaires  
 Dans l'exemple, le troisième argument de la fonction `for_each` est une expression lambda.  La partie `[&evenCount]` spécifie la clause de capture de l'expression, `(int n)` spécifie la liste des paramètres, et la partie restante spécifie le corps de l'expression.  
  
## Exemple 2 : Utilisation d'un objet de fonction  
 Il arrive qu'une expression lambda soit trop complexe pour être utilisée autrement que dans l'exemple précédent.  L'exemple suivant utilise un objet de fonction au lieu d'une expression lambda, en même temps que la fonction `for_each`, pour produire les mêmes résultats que dans l'exemple 1.  Les deux exemples indiquent le nombre de chiffres pairs dans un objet `vector`.  Pour conserver l'état de l'opération, la classe `FunctorClass` enregistre la variable `m_evenCount` par référence comme variable membre.  Pour exécuter l'opération, `FunctorClass` implémente l'opérateur d'appel de fonction, `operator()`.  Le compilateur Visual C\+\+ génère un code qui est comparable en taille et en performances au code de l'expression lambda de l'exemple 1.  Pour un problème simple comme celui de cet article, la plus simple des expressions lambda convient probablement mieux qu'un objet de fonction.  Toutefois, si vous pensez que les fonctionnalités peuvent nécessiter une expansion significative à l'avenir, il serait plus judicieux d'utiliser un objet de fonction afin que la maintenance du code soit facilitée.  
  
 Pour plus d'informations sur le mot clé `operator()`, consultez [Appel de fonction](../cpp/function-call-cpp.md).  Pour plus d'informations sur la fonction `for_each`, consultez [for\_each](../Topic/for_each.md).  
  
### Code  
  
```cpp  
// even_functor.cpp  
// compile with: /EHsc  
#include <algorithm>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
class FunctorClass  
{  
public:  
    // The required constructor for this example.  
    explicit FunctorClass(int& evenCount)  
        : m_evenCount(evenCount) { }  
  
    // The function-call operator prints whether the number is  
    // even or odd. If the number is even, this method updates  
    // the counter.  
    void operator()(int n) const {  
        cout << n;  
  
        if (n % 2 == 0) {  
            cout << " is even " << endl;  
            ++m_evenCount;  
        } else {  
            cout << " is odd " << endl;  
        }  
    }  
  
private:  
    // Default assignment operator to silence warning C4512.  
    FunctorClass& operator=(const FunctorClass&);  
  
    int& m_evenCount; // the number of even variables in the vector.  
};  
  
int main()  
{  
    // Create a vector object that contains 10 elements.  
    vector<int> v;  
    for (int i = 1; i < 10; ++i) {  
        v.push_back(i);  
    }  
  
    // Count the number of even numbers in the vector by   
    // using the for_each function and a function object.  
    int evenCount = 0;  
    for_each(v.begin(), v.end(), FunctorClass(evenCount));  
  
    // Print the count of even numbers to the console.  
    cout << "There are " << evenCount  
        << " even numbers in the vector." << endl;  
}  
  
```  
  
## Sortie  
  **1 est impair**  
**2 est pair**  
**3 est impair**  
**4 est pair**  
**5 est impair**  
**6 est pair**  
**7 est impair**  
**8 est pair**  
**9 est impair**  
**Le vecteur contient 4 nombres pairs.**   
## Voir aussi  
 [Expressions lambda](../cpp/lambda-expressions-in-cpp.md)   
 [Exemples d'expressions lambda](../cpp/examples-of-lambda-expressions.md)   
 [générer](../Topic/generate.md)   
 [generate\_n](../Topic/generate_n.md)   
 [for\_each](../Topic/for_each.md)   
 [Spécifications d'exception \(throw\)](../cpp/exception-specifications-throw-cpp.md)   
 [Avertissement du compilateur \(niveau 1\) C4297](../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md)   
 [Modificateurs spécifiques Microsoft](../cpp/microsoft-specific-modifiers.md)