---
title: "Améliorations de la conformité du compilateur C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: BrianPeek
ms.author: brpeek
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
ms.translationtype: Human Translation
ms.sourcegitcommit: ee7e4f3e09f5b1512182d17fda9033a45ad4aa5b
ms.openlocfilehash: c4bfe76d3b57962fe10df1d55f6ec5b58f70a38a
ms.contentlocale: fr-fr
ms.lasthandoff: 05/09/2017

---
   
# <a name="c-conformance-improvements-in-includevsdev15mdmiscincludesvsdev15mdmd"></a>Améliorations de la conformité de C++ dans [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]
Pour connaître les améliorations apportées à la version de mise à jour 15.3, consultez [Résolutions de bogues dans la version de mise à jour 15.3 de Visual Studio](#update_153).
## <a name="new-language-features"></a>Nouvelles fonctionnalités de langage  
Avec la prise en charge des expressions constexpr généralisées et de NSDMI pour les agrégats, le compilateur est désormais complet pour les fonctionnalités ajoutées à la norme C++14. Notez que le compilateur ne dispose pas encore de certaines fonctionnalités des normes C++11 et C++98. Consultez [Conformité du langage Visual C++](visual-cpp-language-conformance.md) pour obtenir un tableau affichant l’état actuel du compilateur.

### <a name="c11"></a>C++11 :
**Prise en charge de la fonctionnalité SFINAE pour les expressions dans d’autres bibliothèques** Le compilateur Visual C++ continue d’améliorer sa prise en charge de la fonctionnalité SFINAE pour les expressions, qui est nécessaire pour la déduction et la substitution d’argument de modèle dans lesquelles les expressions decltype et constexpr peuvent apparaître en tant que paramètres de modèle. Pour plus d’informations, consultez [Expression SFINAE improvements in Visual Studio 2017 RC](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3). 


### <a name="c-14"></a>C++ 14 :
**NSDMI pour les agrégats** Un agrégat est un tableau ou une classe sans constructeur fourni par l’utilisateur, sans membres de données non statiques privés ou protégés, sans classes de base et sans fonctions virtuelles. À compter de C++14, les agrégats peuvent contenir des initialiseurs de membres. Pour plus d’informations, consultez [Member initializers and aggregates](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html).

**Expressions constexpr étendues** Les expressions déclarées en tant qu’expressions constexpr sont désormais autorisées à contenir certains types de déclarations, des instructions if et switch, des instructions de boucle et une mutation d’objets dont la vie a commencé dans l’évaluation de l’expression constexpr. En outre, il n’est plus nécessaire qu’une fonction membre non statique constexpr soit implicitement de type const. Pour plus d’informations, consultez [Relaxing constraints on constexpr functions](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html). 

### <a name="c17"></a>C++17 :
**static_assert laconique** (disponible avec /std:c++latest) Dans C++17, le paramètre de message pour static_assert est facultatif. Pour plus d’informations, consultez [Extending static_assert, v2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf). 

**Attribut [[fallthrough]]** (disponible avec /std:c++latest) L’attribut [[fallthrough]] est utilisable dans le contexte des instructions switch en tant qu’indicateur informant le compilateur que le comportement fallthrough est prévu. Ce dispositif empêche le compilateur d’émettre des avertissements dans de tels cas. Pour plus d’informations, consultez [Wording for [[fallthrough]] attribute](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf). 

**Boucles range-based for généralisées** (aucun commutateur de compilateur nécessaire) Les Boucles range-based for n’exigent plus que begin() et end() retournent des objets du même type. Ainsi, end() peut retourner un objet sentinel, à l’image de ceux utilisés par les plages définies selon la proposition Ranges-V3. Pour plus d’informations, consultez [Generalizing the Range-Based For Loop](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html) et la [bibliothèque range-v3 sur GitHub](https://github.com/ericniebler/range-v3). 


Pour obtenir la liste complète des améliorations de la conformité jusqu’à Visual Studio 2015, Update 3, consultez [Visual C++ What’s New 2003 through 2015](https://msdn.microsoft.com/en-us/library/mt723604.aspx).

## <a name="bug-fixes"></a>Correctifs de bogues
### <a name="copy-list-initialization"></a>Copy-list-initialization
Visual Studio 2017 déclenche correctement les erreurs de compilateur liées à la création d’objets à l’aide de listes d’initialiseurs qui n’étaient pas interceptées dans Visual Studio 2015 et qui pouvaient entraîner des blocages ou un comportement d’exécution non défini.  Conformément au document N4594, point 13.3.1.7p1, dans copy-list-initialization, le compilateur doit envisager un constructeur explicite pour la résolution de la surcharge, mais doit générer une erreur si cette surcharge est choisie. 

Les deux exemples suivants se compilent dans Visual Studio 2015, mais pas dans Visual Studio 2017.
```cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    A a1 = { 1 }; // error C3445: copy-list-initialization of 'A' cannot use an explicit constructor
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot convert from 'int' to 'const A &'

}
```
Pour corriger l’erreur, utilisez une initialisation directe :
```cpp  
A a1{ 1 };
const A& a2{ 1 };
```

Dans Visual Studio 2015, le compilateur traitait à tort copy-list-initialization de la même façon que l’instruction copy-initialization ordinaire ; il envisageait uniquement de convertir les constructeurs pour résoudre la surcharge. Dans l’exemple suivant, Visual Studio 2015 choisit MyInt(23), mais Visual Studio 2017 déclenche l’erreur correctement. 

```cpp  
// From http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_closed.html#1228
struct MyStore {
       explicit MyStore(int initialCapacity);
};

struct MyInt {
       MyInt(int i);
};

struct Printer {
       void operator()(MyStore const& s);
       void operator()(MyInt const& i);
};

void f() {
       Printer p;
       p({ 23 }); // C3066: there are multiple ways that an object of this type can be called with these arguments
}
```

Cet exemple est semblable au précédent, mais génère une erreur différente. Il réussit dans Visual Studio 2015, mais échoue dans Visual Studio 2017 avec l’erreur C2668. 

```cpp  
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```

### <a name="deprecated-typedefs"></a>Typedefs dépréciées
Visual Studio 2017 émet désormais l’avertissement correct pour les typedefs dépréciées qui sont déclarées dans une classe ou une structure. L’exemple suivant se compile sans avertissements dans Visual Studio 2015, mais génère l’erreur C4996 dans Visual Studio 2017.

```cpp  
struct A 
{
    // also for __declspec(deprecated) 
    [[deprecated]] typedef int inttype;
};

int main()
{
    A::inttype a = 0; // C4996 'A::inttype': was declared deprecated
}
```

### <a name="constexpr"></a>constexpr
Visual Studio 2017 génère correctement une erreur quand l’opérande de gauche d’une opération à évaluation conditionnelle n’est pas valide dans un contexte constexpr. Le code suivant se compile dans Visual Studio 2015, mais pas dans Visual Studio 2017 :

```cpp  
template<int N>
struct array 
{
       int size() const { return N; }
};

constexpr bool f(const array<1> &arr)
{
       return arr.size() == 10 || arr.size() == 11; // error starting in Visual Studio 2017
}
```
Pour corriger cette erreur, déclarez la fonction array::size() en tant que constexpr ou supprimez le qualificateur constexpr de f. 

### <a name="class-types-passed-to-variadic-functions"></a>Types de classe transmis aux fonctions variadiques
Dans Visual Studio 2017, les classes ou structures qui sont passées à une fonction variadique telle que printf doivent être copiables de manière triviale. Quand de tels objets sont passés, le compilateur effectue simplement une copie au niveau du bit et n’appelle pas le constructeur ou le destructeur. 

```cpp  
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function
                        // note: the constructor and destructor will not be called; 
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function

    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);
    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                      // as an argument to a variadic function
}
```
Pour corriger cette erreur, vous pouvez appeler une fonction membre qui retourne un type copiable de manière triviale, 

```cpp  
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```
ou effectuer un cast statique pour convertir l’objet avant de le transmettre :
```cpp  
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```
Pour les chaînes générées et gérées à l’aide de CStringW, vous devez utiliser le `operator LPCWSTR()` fourni pour caster un objet CStringW vers le pointeur C attendu par la chaîne de format.

```cpp  
CStringW str1;
CStringW str2;
str1.Format(L"%s", static_cast<LPCWSTR>(str2));
```

### <a name="cv-qualifiers-in-class-construction"></a>Qualificateurs cv dans la construction de la classe
Dans Visual Studio 2015, le compilateur ignore parfois à tort le qualificateur cv pendant la génération d’un objet de classe par le biais d’un appel de constructeur. Cela peut provoquer un incident ou un comportement inattendu au moment de l’exécution. L’exemple suivant se compile dans Visual Studio 2015, mais génère une erreur de compilateur dans Visual Studio 2017 :

```cpp  
struct S 
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```
Pour corriger cette erreur, déclarez l’opérateur int() en tant que const. 

### <a name="access-checking-on-qualified-names-in-templates"></a>Contrôle d’accès sur les noms qualifiés dans les modèles
Les versions précédentes du compilateur n’effectuaient pas de contrôle d’accès sur les noms qualifiés dans certains contextes de modèle. Cela peut interférer avec le comportement attendu de la fonctionnalité SFINAE où la substitution est supposée échouer en raison de l’inaccessibilité d’un nom. Cette situation peut entraîner un incident ou un comportement inattendu au moment de l’exécution en raison de l’appel par le compilateur de la surcharge incorrecte de l’opérateur. Dans Visual Studio 2017, une erreur de compilateur est générée. L’erreur spécifique peut varier, mais, en général, il s’agit de « C2672 fonction correspondante surchargée introuvable ». Le code suivant se compile dans Visual Studio 2015, mais génère une erreur dans Visual Studio 2017 :

```cpp  
#include <type_traits>

template <class T> class S {
       typedef typename T type;
};

template <class T, std::enable_if<std::is_integral<typename S<T>::type>::value, T> * = 0>
bool f(T x);

int main()
{
       f(10); // C2672: No matching overloaded function found. 
}
```

### <a name="missing-template-argument-lists"></a>Listes d’arguments de modèle manquantes
Dans Visual Studio 2015 et versions antérieures, le compilateur ne diagnostiquait pas les listes d’arguments de modèle manquantes quand le modèle apparaissait dans une liste de paramètres de modèle (par exemple, dans le cadre d’un argument de modèle par défaut ou d’un paramètre de modèle sans type). Cela peut entraîner un comportement imprévisible, y compris des pannes du compilateur ou un comportement inattendu au moment de l’exécution. Le code suivant se compile dans Visual Studio 2015, mais génère une erreur dans Visual Studio 2017 :

```cpp  
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias 
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;  
```

### <a name="expression-sfinae"></a>Fonctionnalité SFINAE pour les expressions
Pour prendre en charge la fonctionnalité SFINAE pour les expressions, le compilateur analyse maintenant les arguments decltype quand les modèles sont déclarés et non instanciés. Ainsi, si une spécialisation non dépendante est trouvée dans l’argument decltype, elle n’est pas reportée à l’instanciation et est traitée immédiatement, et toute erreur résultante est diagnostiquée à ce moment-là.  

L’exemple suivant montre une erreur de compilateur de ce type générée au moment de la déclaration :

```cpp  
#include <utility>
template <class T, class ReturnT, class... ArgsT> class IsCallable
{
public:
       struct BadType {};
       template <class U>
       static decltype(std::declval<T>()(std::declval<ArgsT>()...)) Test(int); //C2064. Should be declval<U>
       template <class U>
       static BadType Test(...);
       static constexpr bool value = std::is_convertible<decltype(Test<T>(0)), ReturnT>::value;
};

constexpr bool test1 = IsCallable<int(), int>::value;
static_assert(test1, "PASS1");
constexpr bool test2 = !IsCallable<int*, int>::value;
static_assert(test2, "PASS2");
```
### <a name="classes-declared-in-anonymous-namespaces"></a>Classes déclarées dans des espaces de noms anonymes
Selon la norme C++, une classe déclarée dans un espace de noms anonyme a une liaison interne et, par conséquent, ne peut pas être exportée. Dans Visual Studio 2015 et versions antérieures, cette règle n’était pas appliquée. Dans Visual Studio 2017, la règle est partiellement appliquée. L’exemple suivant génère cette erreur dans Visual Studio 2017 : « erreur C2201 : 'const `anonymous namespace'::S1::`vftable'' : doit avoir une liaison externe afin d’être exportée/importée. »

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>Initialiseurs par défaut pour les membres de classe value (C++/CLI)
Dans Visual Studio 2015 et antérieur, le compilateur autorisait (mais ignorait) un initialiseur de membre par défaut pour un membre d’une classe value.  L’initialisation par défaut d’une classe value initialise systématiquement les membres à zéro ; un constructeur par défaut n’est pas autorisé.  Dans Visual Studio 2017, les initialiseurs de membres par défaut déclenchent une erreur de compilateur, comme illustré dans cet exemple :

```cpp  
value struct V
{
       int i = 0; // error C3446: 'V::i': a default member initializer  
                  // is not allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>Indexeurs par défaut (C++/CLI)
Dans Visual Studio 2015 et antérieur, le compilateur identifiait à tort une propriété par défaut en tant qu’indexeur par défaut dans certaines circonstances. Il était possible de contourner le problème en utilisant l’identificateur « default » pour accéder à la propriété. La solution de contournement elle-même est devenue problématique dès que default a été introduit comme mot clé dans C++11. Ainsi, dans Visual Studio 2017, les bogues qui nécessitaient la solution de contournement ont été corrigés, et le compilateur génère maintenant une erreur quand l’utilisateur recourt à « default » pour accéder à la propriété par défaut d’une classe.

```cpp  
//class1.cs

using System.Reflection;
using System.Runtime.InteropServices;

namespace ClassLibrary1
{
    [DefaultMember("Value")]
    public class Class1
    {
        public int Value
        {
            // using attribute on the return type triggers the compiler bug
            [return: MarshalAs(UnmanagedType.I4)]
            get;
        }
    }
    [DefaultMember("Value")]
    public class Class2
    {
        public int Value
        {
            get;
        }
    }
}

 
// code.cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value; // error
       r1->default;
       r2->Value;
       r2->default; // error
}
```

Dans Visual Studio 2017, vous pouvez accéder aux deux propriétés Value par leur nom :

```cpp  
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value;
       r2->Value;
}
```

## <a name="update_153"></a> Version de mise à jour 15.3 de Visual Studio 2017
### <a name="calls-to-deleted-member-templates"></a>Appels à des modèles membres supprimés
Dans les versions précédentes de Visual Studio, le compilateur ne parvenait pas dans certains cas à émettre une erreur pour les appels incorrects à un modèle membre supprimé qui pouvaient éventuellement provoquer des incidents lors de l’exécution. Le code suivant génère désormais l’erreur C2280, « 'int S<int>::f<int>(void)' : tentative de référencement d’une fonction supprimée » :
```cpp
template<typename T> 
struct S { 
template<typename U> static int f() = delete; 
}; 
 
void g() 
{ 
decltype(S<int>::f<int>()) i; // this should fail 
}
```
Pour corriger cette erreur, déclarez i comme `int`.

### <a name="pre-condition-checks-for-type-traits"></a>Vérifications de conditions préalables pour les traits de type
La version de mise à jour 15.3 de Visual Studio 2017 améliore les vérifications de conditions préalables pour les traits de type afin de suivre plus strictement la norme. Une telle vérification doit être affectée. Le code suivant génère l’erreur C2139 dans la version de mise à jour 15.3 :

```cpp
struct S; 
enum E; 
 
static_assert(!__is_assignable(S, S), "fail"); // this is allowed in VS2017 RTM, but should fail 
static_assert(__is_convertible_to(E, E), "fail"); // this is allowed in VS2017 RTM, but should fail
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>Nouvel avertissement du compilateur et nouvelles vérifications à l’exécution sur du marshaling de fonctions natives à managées
L’appel des fonctions managées aux fonctions natives nécessite un marshaling. Le CLR exécute le marshaling, mais il ne comprend pas la sémantique C++. Si vous passez un objet natif par valeur, le CLR appelle le constructeur de copie de l’objet ou utilise BitBlt, ce qui peut provoquer un comportement non défini lors de l’exécution. 
 
Désormais, le compilateur émet un avertissement s’il peut savoir au moment de la compilation qu’un objet natif avec un constructeur de copie supprimé est transmis entre les limites native et managée par valeur. Pour les cas où le compilateur ne sait rien au moment de la compilation, il injecte une vérification à l’exécution afin que le programme appelle std::terminate immédiatement dès qu’un marshaling incorrect se produit. Dans la version de mise à jour 15.3, le code suivant génère l’erreur C4606, « 'A' : le passage d’un argument par valeur à travers une frontière native/managée nécessite un constructeur de copie valide. Sinon, le comportement au moment de l’exécution est non défini. »
```cpp
class A 
{ 
public: 
A() : p_(new int) {} 
~A() { delete p_; } 
 
A(A const &) = delete; 
A(A &&rhs) { 
p_ = rhs.p_; 
} 
 
private: 
int *p_; 
}; 
 
#pragma unmanaged 
 
void f(A a) 
{ 
} 
 
#pragma managed 
 
int main() 
{ 
    f(A()); // This call from managed to native requires marshalling. The CLR doesn't understand C++ and uses BitBlt, which will result in a double-free later. 
}
```
Pour corriger cette erreur, supprimez la directive `#pragma managed` pour marquer l’appelant comme natif et éviter le marshaling. 

### <a name="experimental-api-warning-for-winrt"></a>Avertissement d’API expérimentale pour WinRT
Les API WinRT publiées pour l’expérimentation et les commentaires sont décorées avec `Windows.Foundation.Metadata.ExperimentalAttribute`. Dans la version de mise à jour 15.3, le compilateur génère l’avertissement C4698 quand il rencontre l’attribut. Certaines API dans les versions précédentes du SDK Windows ont déjà été décorées avec l’attribut et les appels à ces API déclenchent cet avertissement du compilateur. L’attribut est supprimé de tous les types fournis dans les SDK Windows plus récents mais, si vous utilisez un SDK plus ancien, vous devez supprimer ces avertissements pour tous les appels aux types fournis.
Le code suivant génère l’avertissement C4698 : « 'Windows::Storage::IApplicationDataStatics2::GetForUserAsync' est utilisé à des fins d’évaluation uniquement. Il sera peut-être changé ou supprimé au cours des prochaines mises à jour. » :
```cpp
Windows::Storage::IApplicationDataStatics2::GetForUserAsync()
```

Pour désactiver l’avertissement, ajoutez un #pragma :

```cpp
#pragma warning(push) 
#pragma warning(disable:4698) 
 
Windows::Storage::IApplicationDataStatics2::GetForUserAsync() 
 
#pragma warning(pop)
```
### <a name="out-of-line-definition-of-a-template-member-function"></a>Définition hors ligne d’une fonction membre de modèle 
La version de mise à jour 15.3 génère une erreur quand elle rencontre une définition hors ligne d’une fonction membre de modèle qui n’a pas été déclarée dans la classe. Le code suivant génère désormais l’erreur C2039 : 'f' : n’est pas un membre de 'S' :

```cpp
struct S {}; 
 
template <typename T> 
void S::f(T t) {}
```

Pour corriger cette erreur, ajoutez une déclaration à la classe :

```cpp
struct S { 
    template <typename T> 
    void f(T t); 
}; 
template <typename T> 
void S::f(T t) {}
```

### <a name="attempting-to-take-the-address-of-this-pointer"></a>Tentative de prendre l’adresse du pointeur 'this'
En C++, 'this' est une prvalue de pointeur de type vers X. Vous ne pouvez pas prendre l’adresse de 'this' ni la lier à une référence lvalue. Dans les versions précédentes de Visual Studio, le compilateur vous permettait de contourner cette restriction en effectuant un cast. Dans la version de mise à jour 15.3, le compilateur génère l’erreur C2664.

### <a name="conversion-to-an-inaccessible-base-class"></a>Conversion vers une classe de base inaccessible
La version de mise à jour 15.3 génère une erreur quand vous essayez de convertir un type en une classe de base qui n’est pas accessible. Le compilateur génère maintenant  
« erreur C2243 : 'cast de type' : la conversion de 'D *' en 'B *' existe, mais n’est pas accessible ». Le code suivant est incorrect et peut éventuellement provoquer un incident lors de l’exécution. Le compilateur génère désormais l’erreur C2243 quand il rencontre un code tel que le suivant :

```cpp
#include <memory> 
 
class B { }; 
class D : B { }; // should be public B { }; 
 
void f() 
{ 
   std::unique_ptr<B>(new D()); 
}
```
### <a name="default-arguments-are-not-allowed-on-out-of-line-definitions-of-member-functions"></a>Les arguments par défaut ne sont pas autorisés sur les définitions hors ligne des fonctions membres
Les arguments par défaut ne sont pas autorisés sur les définitions hors ligne des fonctions membres dans les classes de modèles.  Le compilateur émet un avertissement sous /permissive et une erreur matérielle sous /permissive. Dans les versions précédentes de Visual Studio, le code incorrect suivant pouvait éventuellement provoquer un incident lors de l’exécution. La version de mise à jour 15.3 génère l’avertissement C5034 : 'A<T>::f' : une définition hors ligne d’un membre d’un modèle de classe ne peut pas avoir d’arguments par défaut :
```cpp
 
template <typename T> 
struct A { 
    T f(T t, bool b = false); 
}; 
 
template <typename T> 
T A<T>::f(T t, bool b = false) 
{ 
... 
}
```
Pour corriger cette erreur, supprimez l’argument par défaut « = false ». 

### <a name="use-of-offsetof-with-compound-member-designator"></a>Utilisation d’offsetof avec désignateur de membre composé
Dans la version de mise à jour 15.3, l’utilisation d’offsetof(T, m) où m est un « désignateur de membre composé » aboutit à un avertissement quand vous compilez avec l’option /Wall. Le code suivant est incorrect et peut éventuellement provoquer un incident lors de l’exécution. La version de mise à jour 15.3 génère l’avertissement C4841 : extension non standard utilisée : désignateur de membre composé dans offsetof » :

```cpp
  
struct A { 
int arr[10]; 
}; 
 
// warning C4841: non-standard extension used: compound member designator in offsetof 
constexpr auto off = offsetof(A, arr[2]);
```
Pour corriger le code, désactivez l’avertissement avec un pragma ou modifiez le code pour ne pas utiliser offsetof : 

```cpp
#pragma warning(push) 
#pragma warning(disable: 4841) 
constexpr auto off = offsetof(A, arr[2]); 
#pragma warning(pop) 
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>Utilisation d’offsetof avec des données membres static ou une fonction membre
Dans la version de mise à jour 15.3, l’utilisation d’offsetof(T, m) où m fait référence à des données membres static ou une fonction membre aboutit à une erreur. Le code suivant génère « erreur C4597 : comportement non défini : offsetof appliqué à la fonction membre « foo » » et « erreur C4597 : comportement non défini : offsetof appliqué à des données membres static 'bar' » :
```cpp
 
#include <cstddef> 
 
struct A { 
int foo() { return 10; } 
static constexpr int bar = 0; 
}; 
 
constexpr auto off = offsetof(A, foo); 
Constexpr auto off2 = offsetof(A, bar);
```
 
Ce code est incorrect et peut éventuellement provoquer un incident lors de l’exécution. Pour corriger cette erreur, modifiez le code pour ne plus appeler un comportement non défini. Il s’agit de code non portable qui n’est pas autorisé par la norme C++.

### <a name="new-warning-on-declspec-attributes"></a>Nouvel avertissement sur les attributs declspec
Dans la version de mise à jour 15.3, le compilateur n’ignore plus les attributs si __declspec(…) est appliqué avant une spécification de liaison 'C' externe. Auparavant, le compilateur ignorait l’attribut, ce qui pouvait avoir des implications lors de l’exécution. Quand l’option `/Wall /WX` est définie, le code suivant génère « avertissement C4768 : les attributs __declspec avant la spécification de liaison sont ignorés » :

```cpp
 
__declspec(noinline) extern "C" HRESULT __stdcall
```

Pour corriger l’avertissement, placez 'C' externe en premier :

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

### <a name="decltype-and-calls-to-deleted-destructors"></a>decltype et appels à des destructeurs supprimés
Dans les versions précédentes de Visual Studio, le compilateur ne détectait pas quand un appel à un destructeur supprimé se produisait dans le contexte de l’expression associée à « decltype ». Dans la version de mise à jour 15.3, le code suivant génère « erreur C2280 : 'A<T>::~A(void)' : tentative de référencement d’une fonction supprimée » :

```cpp
template<typename T> 
struct A 
{ 
   ~A() = delete; 
}; 
 
template<typename T> 
auto f() -> A<T>; 
 
template<typename T> 
auto g(T) -> decltype((f<T>())); 
 
void h() 
{ 
   g(42); 
}
```
### <a name="unitialized-const-variables"></a>Variables const non initialisées
La version Visual Studio 2017 RTW avait une régression dans laquelle le compilateur C++ n’émettait pas de diagnostic si une variable 'const' n’était pas initialisée. Cette régression a été corrigée dans Visual Studio 2017 Update 1. Le code suivant génère désormais « avertissement C4132 : 'Value' : un objet const doit être initialisé » :

```cpp
const int Value;
```
Pour corriger cette erreur, attribuez une valeur à `Value`.

### <a name="empty-declarations"></a>Déclarations vides
La version de mise à jour 15.3 de Visual Studio 2017 émet désormais un avertissement relatif aux déclarations vides pour tous les types, non seulement les types intégrés. Le code suivant génère désormais un avertissement C4091 de niveau 2 pour les quatre déclarations :

```cpp
struct A {};
template <typename> struct B {};
enum C { c1, c2, c3 };
 
int;    // warning C4091 : '' : ignored on left of 'int' when no variable is declared
A;      // warning C4091 : '' : ignored on left of 'main::A' when no variable is declared
B<int>; // warning C4091 : '' : ignored on left of 'B<int>' when no variable is declared
C;      // warning C4091 : '' : ignored on left of 'C' when no variable is declared
```

Pour supprimer les avertissements, il vous suffit de commenter ou de supprimer les déclarations vides.  Dans les cas où l’objet sans nom doit avoir un effet secondaire (par exemple, RAII), vous devez lui affecter un nom.
 
L’avertissement est exclu sous /Wv:18 et est activé par défaut sous le niveau d’avertissement W2.


## <a name="see-also"></a>Voir aussi  
[Conformité du langage Visual C++](visual-cpp-language-conformance.md)  

