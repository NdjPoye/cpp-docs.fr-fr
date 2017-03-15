---
title: "decltype (C++) | Microsoft Docs"
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
  - "decltype"
  - "decltype_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "decltype (opérateur)"
  - "opérateurs (C++), decltype"
  - "opérateurs (C++), déduire des types d'expression"
  - "opérateurs (C++), type d'une expression"
ms.assetid: 6dcf8888-8196-4f13-af50-51e3797255d4
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# decltype (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le spécificateur de type `decltype` génère le type d'une expression spécifiée.  Le spécificateur de type `decltype`, avec le [mot clé auto](../cpp/auto-cpp.md), est particulièrement utile pour les développeurs qui écrivent des bibliothèques de modèles.  Utilisez `auto` et `decltype` pour déclarer une fonction de modèle dont le type de retour dépend des types de ses arguments template.  Sinon, utilisez `auto` et `decltype` pour déclarer une fonction de modèle qui encapsule un appel à une autre fonction, puis retourne le type de retour de la fonction encapsulée.  
  
## Syntaxe  
  
```  
decltype( expression )  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`expression`|d'une expression.  Pour plus d'informations, consultez [Expressions](../cpp/expressions-cpp.md).|  
  
## Valeur de retour  
 Type du paramètre `expression`.  
  
## Notes  
 Le spécificateur de type `decltype` est pris en charge dans Visual C\+\+ 2010 ou versions ultérieures et peut être utilisé avec le code natif ou managé.  `decltype(auto)` \(C\+\+14\) est pris en charge dans Visual Studio 2015 et versions ultérieures.  
  
 Le compilateur utilise les règles suivantes pour déterminer le type du paramètre `expression`.  
  
-   Si le paramètre `expression` est un identificateur ou un [accès de membre de classe](../cpp/member-access-operators-dot-and.md), `decltype(``expression``)` est le type de l'entité nommée par `expression`.  Si cette entité n'existe pas ou si le paramètre `expression` nomme un ensemble de fonctions surchargées, le compilateur génère un message d'erreur.  
  
-   Si le paramètre `expression` est un appel à une fonction ou une fonction d'opérateur surchargé, `decltype(``expression``)` est le type de retour de la fonction.  Les parenthèses autour d'un opérateur surchargé sont ignorées.  
  
-   Si le paramètre `expression` est une [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(``expression``)` est le type de `expression`.  Si le paramètre `expression` est une [lvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(``expression``)` est une [référence lvalue](../cpp/lvalue-reference-declarator-amp.md) au type de `expression`.  
  
 L'exemple de code suivant montre certaines utilisations du spécificateur de type `decltype`.  Tout d'abord, supposez que vous avez codé les instructions suivantes.  
  
```  
int var;  
const int&& fx();   
struct A { double x; }  
const A* a = new A();  
```  
  
 Ensuite, examinez les types retournés par les quatre instructions `decltype` dans le tableau suivant.  
  
|Instruction du langage|Type|Remarques|  
|----------------------------|----------|---------------|  
|`decltype(fx());`|`const int&&`|Une [référence rvalue](../cpp/rvalue-reference-declarator-amp-amp.md) à un `const int`.|  
|`decltype(var);`|`int`|Type de la variable `var`.|  
|`decltype(a->x);`|`double`|Type de l'accès au membre.|  
|`decltype((a->x));`|`const double&`|Les parenthèses internes provoquent l'évaluation de l'instruction en tant qu'expression plutôt qu'en tant qu'accès au membre.  Étant donné que `a` est déclaré comme pointeur `const`, le type est une référence à `const double`.|  
  
## Decltype et Auto  
 En C\+\+14, vous pouvez utiliser  `decltype(auto)` sans type de retour de fin pour déclarer une fonction de modèle dont le type de retour dépend des types de ses arguments template.  
  
 En C\+\+11, vous pouvez utiliser le spécificateur de type `decltype` sur un type de retour de fin avec le mot clé `auto` pour déclarer une fonction de modèle dont le type de retour dépend des types de ses arguments template.  Considérez l'exemple de code suivant dans lequel le type de retour de la fonction de modèle dépend des types des arguments template.  Dans l'exemple de code, l'espace réservé *UNKNOWN* indique que le type de retour ne peut pas être spécifié.  
  
```  
template<typename T, typename U>  
UNKNOWN func(T&& t, U&& u){ return t + u; };   
```  
  
 L'introduction du spécificateur de type `decltype` permet à un développeur d'obtenir le type de l'expression retournée par la fonction de modèle.  Utilisez l'*autre syntaxe de déclaration de fonction* illustrée plus loin, le mot clé `auto` et le spécificateur de type `decltype` pour déclarer un type de retour *spécifié à la fin*.  Le type de retour spécifié à la fin est déterminé lors de la compilation de la déclaration, plutôt que lors de son codage.  
  
 Le prototype suivant illustre la syntaxe d'une autre déclaration de fonction.  Notez que les qualificateurs `const` et `volatile`, ainsi que la [spécification d'exception](../cpp/exception-specifications-throw-cpp.md) `throw` sont facultatifs.  L'espace réservé *function\_body* représente une instruction composée qui spécifie ce que fait la fonction.  En matière de codage, il est recommandé que l'espace réservé *expression* dans l'instruction `decltype` corresponde à l'expression spécifiée par l'instruction `return`, le cas échéant, dans *function\_body*.  
  
 `auto` *function\_name*`(`*parameters*opt`)` `const`opt `volatile`opt `−>` `decltype(`*expression*`)` `throw`opt `{`*function\_body*`};`  
  
 Dans l'exemple de code suivant, le type de retour spécifié à la fin de la fonction de modèle `myFunc` est déterminé par les types des arguments template de `t` et de `u`.  En matière de codage, il est recommandé que l'exemple de code utilise également les références rvalue et le modèle de fonction `forward`, qui prennent en charge le *transfert parfait*.  Pour plus d'informations, consultez [Déclarateur de référence Rvalue : &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
```  
//C++11  
 template<typename T, typename U>  
auto myFunc(T&& t, U&& u) -> decltype (forward<T>(t) + forward<U>(u))   
        { return forward<T>(t) + forward<U>(u); };  
  
//C++14  
template<typename T, typename U>  
decltype(auto) myFunc(T&& t, U&& u)   
        { return forward<T>(t) + forward<U>(u); };  
  
```  
  
## Decltype et fonctions de transfert \(C\+\+11\)  
 Les fonctions de transfert encapsulent les appels à d'autres fonctions.  Considérez un modèle de fonction qui transfère ses arguments, ou les résultats d'une expression qui implique ces arguments, à une autre fonction.  En outre, la fonction de transfert retourne le résultat de l'appel à l'autre fonction.  Dans ce scénario, le type de retour de la fonction de transfert doit être identique au type de retour de la fonction encapsulée.  
  
 Dans ce scénario, vous ne pouvez pas écrire une expression de type appropriée sans le spécificateur de type `decltype`.  Le spécificateur de type `decltype` active des fonctions génériques de transfert car il ne perd pas les informations requises indiquant si une fonction retourne un type référence.  Pour obtenir un exemple de code d'une fonction de transfert, consultez l'exemple de la fonction de modèle `myFunc` précédent.  
  
## Exemple  
 L'exemple de code suivant déclare le type de retour spécifié à la fin de la fonction de modèle `Plus()`.  La fonction `Plus` traite ses deux opérandes avec la surcharge `operator+`.  Par conséquent, l'interprétation de l'opérateur plus \(\+\) et le type de retour de la fonction `Plus` dépend des types des arguments de fonction.  
  
```  
// decltype_1.cpp  
// compile with: /EHsc  
//  
#include "stdafx.h"  
#include <iostream>  
#include <string>  
#include <utility>  
#include <iomanip>  
  
using namespace std;  
  
template<typename T1, typename T2>  
auto Plus(T1&& t1, T2&& t2) ->   
   decltype(forward<T1>(t1) + forward<T2>(t2))  
{  
   return forward<T1>(t1) + forward<T2>(t2);  
}  
  
class X  
{  
   friend X operator+(const X& x1, const X& x2)  
   {  
      return X(x1.m_data + x2.m_data);  
   }  
  
public:  
   X(int data) : m_data(data) {}  
   int Dump() const { return m_data;}  
private:  
   int m_data;  
};  
  
int main()  
{  
   // Integer   
   int i = 4;  
   cout <<   
      "Plus(i, 9) = " <<   
      Plus(i, 9) << endl;  
  
   // Floating point  
   float dx = 4.0;  
   float dy = 9.5;  
   cout <<     
      setprecision(3) <<   
      "Plus(dx, dy) = " <<  
      Plus(dx, dy) << endl;  
  
   // String        
   string hello = "Hello, ";  
   string world = "world!";  
   cout << Plus(hello, world) << endl;  
  
   // Custom type  
   X x1(20);  
   X x2(22);  
   X x3 = Plus(x1, x2);  
   cout <<   
      "x3.Dump() = " <<   
      x3.Dump() << endl;  
}  
```  
  
 **Sortie**  
  
 Cet exemple de code génère les résultats suivants.  
  
 13  
  
 13.5  
  
 Hello, world\!  
  
 42  
  
## Configuration requise  
 Visual C\+\+ 2010 ou versions ultérieures.  
  
 decltype\(auto\) requiert Visual Studio 2015 ou version ultérieure  
  
## Voir aussi  
 [\(NOTINBUILD\)Simple Type Names](http://msdn.microsoft.com/fr-fr/333f45cb-2c72-4d81-8e59-e346b05f55e3)