---
title: "Fonctions (C++) | Microsoft Docs"
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
  - "déclarateurs, fonctions"
  - "arguments par défaut"
  - "valeurs par défaut, arguments"
  - "définitions de fonction"
  - "définitions de fonction, à propos des définitions de fonction"
ms.assetid: 33ba01d5-75b5-48d2-8eab-5483ac7d2274
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fonctions (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une fonction est un bloc de code qui effectue une opération.  Une fonction peut éventuellement définir les paramètres d'entrée qui permettent aux appelants de passer des arguments dans la fonction.  Une fonction peut éventuellement retourner une valeur en tant que sortie.  Les fonctions sont utiles pour encapsuler les opérations courantes dans un seul bloc réutilisable, idéalement avec un nom qui décrit clairement ce que fait la fonction.  La fonction suivante accepte deux entiers à partir d'un appelant et retourne leur somme ; `a` et `b` sont des *paramètres* de type `int`.  
  
```  
int sum(int a, int b)  
{  
    return a + b;  
}  
```  
  
 La fonction peut être *appelée* à partir d'un nombre quelconque d'emplacements dans le programme.  Les valeurs qui sont passées à la fonction sont les *arguments*, dont les types doivent être compatibles avec les types de paramètres dans la définition de fonction.  
  
```  
int main()  
{  
    int i = sum(10, 32);  
    int j = sum(i, 66);  
    cout << "The value of j is" << j << endl; // 108  
}  
```  
  
 Il n'existe aucune limite pratique à la longueur de la fonction, mais une conception judicieuse s'adresse aux fonctions qui effectuent une seule tâche bien définie.  Les algorithmes complexes doivent être divisés en fonctions plus simples à comprendre chaque fois que possible.  
  
 Les fonctions qui sont définies au niveau de la portée de classe sont appelées fonctions membres.  En C\+\+, contrairement à d'autres langages, une fonction peut également être définie au niveau de la portée d'espace de noms \(y compris l'espace de noms global implicite\).  Ces fonctions sont appelées *fonctions libres* ou *fonctions non membres* ; elles sont largement utilisées dans la bibliothèque standard.  
  
## Éléments d'une déclaration de fonction  
 Une *déclaration* de fonction minimale est constituée du type de retour, du nom de fonction et de la liste de paramètres \(qui peut être vide\), ainsi que des mots clés facultatifs qui fournissent des instructions supplémentaires au compilateur.  Une définition de fonction se compose d'une déclaration, plus du *corps*, qui est tout le code entre les accolades.  Une déclaration de fonction suivie d'un point\-virgule peut apparaître à plusieurs endroits dans un programme.  Elle doit apparaître avant tout appel à cette fonction dans chaque unité de traduction.  La définition de fonction doit apparaître une seule fois dans le programme, en fonction de la règle de définitions.  
  
 Les éléments requis d'une déclaration de fonction sont les suivants :  
  
1.  Le type de retour, qui spécifie le type de la valeur retournée par la fonction, ou `void` si aucune valeur n'est retournée.  En C\+\+11, auto est un type de retour valide qui indique au compilateur de déduire le type de l'instruction return.  En C\+\+14, decltype\(auto\) est également autorisé.  Pour plus d'informations, consultez Déduction de type dans les types de retours ci\-dessous.  
  
2.  Le nom de fonction, qui doit commencer par une lettre ou un trait de soulignement et ne peut pas contenir d'espaces.  En général, les traits de soulignement de début dans les noms de fonctions de bibliothèque standard indiquent des fonctions membres privées ou des fonctions non membres qui ne sont pas destinées à être utilisées par votre code.  
  
3.  La liste de paramètres, un ensemble de zéro ou plusieurs paramètres séparés par des virgules et délimités par des accolades qui spécifient le type et éventuellement un nom local selon lequel les valeurs sont accessibles à l'intérieur du corps de la fonction.  
  
 Les éléments facultatifs d'une déclaration de fonction sont les suivants :  
  
1.  `constexpr`, qui indique que la valeur de retour de la fonction est une valeur de constante pouvant être calculée au moment de la compilation.  
  
    ```  
  
                  constexpr float exp(float x, int n)  
    {  
        return n == 0 ? 1 :  
            n % 2 == 0 ? exp(x * x, n / 2) :  
            exp(x * x, (n - 1) / 2) * x;  
    };  
    ```  
  
2.  Sa spécification `linkage`, `extern` ou `static`.  
  
    ```  
    Declare printf with C linkage.  
    extern "C" int printf( const char *fmt, ... );  
  
    ```  
  
     Pour plus d'informations, consultez [Programme et liaison](../cpp/program-and-linkage-cpp.md).  
  
3.  `inline`, qui indique au compilateur de remplacer chaque appel à la fonction par le code de la fonction.  L'incorporation peut améliorer les performances dans les scénarios où une fonction s'exécute rapidement et est appelée à plusieurs reprises dans une section du code critique pour les performances.  
  
    ```  
    inline double Account::GetBalance()  
    {  
        return balance;  
    }  
    ```  
  
     Pour plus d'informations, consultez [Fonctions inline](../cpp/inline-functions-cpp.md).  
  
4.  `noexcept`, qui spécifie si la fonction peut lever une exception.  Dans l'exemple suivant, la fonction ne lève pas d'exception si l'expression `is_pod` correspond à `true`.  
  
    ```  
    #include <type_traits>  
  
    template <typename T>  
    T copy_object(T& obj) noexcept(std::is_pod<T>) {...}  
    ```  
  
     Pour plus d'informations, consultez [noexcept](../cpp/noexcept-cpp.md).  
  
5.  \(Fonctions membres uniquement\) Les qualificateurs cv, qui indiquent si la fonction est `const` ou `volatile`.  
  
6.  \(Fonctions membres uniquement\) `virtual`, `override` ou `final`.  `virtual` spécifie qu'une fonction peut être substituée dans une classe dérivée.  `override` signifie qu'une fonction dans une classe dérivée remplace une fonction virtuelle.  `final` signifie qu'une fonction ne peut pas être substituée dans toute classe dérivée supplémentaire.  Pour plus d'informations, consultez [Fonctions virtuelles](../cpp/virtual-functions.md).  
  
7.  \(Fonctions membres uniquement\) `static` appliqué à une fonction membre signifie que la fonction n'est pas associée à des instances d'objet de la classe.  
  
8.  \(Fonctions membres non statiques uniquement\) Le qualificateur ref, qui indique au compilateur quelle surcharge d'une fonction choisir quand le paramètre d'objet implicite \(\*this\) est une référence rvalue par rapport  à une référence lvalue.  
  
 L'illustration suivante montre les parties d'une définition de fonction.  La zone grisée est le corps de la fonction.  
  
 ![Éléments de définition de fonction](../cpp/media/vc38ru1.png "vc38RU1")  
Parties d'une définition de fonction  
  
## Définitions de fonction  
 Les variables déclarées à l'intérieur du corps sont appelées variables locales.  Elles sortent de la portée lors de la fermeture de la fonction ; par conséquent, une fonction ne doit jamais retourner une référence à une variable locale \!  
  
## Modèles de fonctions  
 Un modèle de fonction est similaire à un modèle de classe ; il génère des fonctions concrètes basées sur les arguments template.  Dans de nombreux cas, le modèle est capable de déduire les arguments de type et, par conséquent, il n'est pas nécessaire de les spécifier explicitement.  
  
```  
template<typename Lhs, typename Rhs>  
auto Add2(const Lhs& lhs, const Rhs& rhs)  
{  
    return lhs + rhs;  
}  
  
auto a = Add2(3.13, 2.895); // a is a double  
auto b = Add2(string{ "Hello" }, string{ " World" }); // b is a std::string  
```  
  
 Pour plus d'informations, consultez [Modèles de fonctions](../cpp/function-templates.md).  
  
## Paramètres et arguments de fonction  
 Une fonction possède une liste de paramètres séparés par des virgules de zéro, un ou plusieurs types, chacun d'eux ayant un nom selon lequel il est accessible à l'intérieur du corps de la fonction.  Un modèle de fonction peut spécifier des paramètres de type ou de valeur supplémentaires.  L'appelant transmet les arguments, qui sont des valeurs concrètes dont les types sont compatibles avec la liste de paramètres.  
  
 Par défaut, les arguments sont passés à la fonction par valeur, ce qui signifie que la fonction reçoit une copie de l'objet passé.  Pour les objets volumineux, une copie peut être coûteuse et n'est pas toujours nécessaire.  Pour que les arguments soient passés par référence \(en particulier la référence lvalue\), ajoutez un qualificateur de référence au paramètre :  
  
```  
void DoSomething(std::string& input){...}  
```  
  
 Lorsqu'une fonction modifie un argument passé par référence, elle modifie l'objet d'origine, pas une copie locale.  Pour empêcher une fonction de modifier un tel argument, qualifiez le paramètre comme const& :  
  
```  
void DoSomething(const std::string& input){...}  
```  
  
 **C\+\+ 11 :**  pour gérer explicitement les arguments passés par référence rvalue OU par référence lvalue, utilisez une double perluète sur le paramètre pour indiquer une référence universelle :  
  
```  
void DoSomething(const std::string&& input){...}  
```  
  
 Une fonction déclarée avec le mot clé unique `void` dans la liste des déclarations de paramètres ne prend pas d'argument, tant que le mot clé `void` est le premier et le seul membre de la liste des déclarations d'arguments.  Les arguments de type `void` situés ailleurs dans la liste génèrent des erreurs.  Exemple :  
  
```  
  
// OK same as GetTickCount()  
long GetTickCount( void );   
```  
  
 Notez que, bien qu'il ne soit pas conforme de spécifier un argument `void`, sauf comme exposé dans cette section, les types dérivés du type `void` \(comme les pointeurs vers `void` et les tableaux de `void`\) peuvent apparaître partout dans la liste des déclarations d'arguments.  
  
### Arguments par défaut  
 Le ou les derniers paramètres dans une signature de fonction peuvent recevoir un argument par défaut, ce qui signifie que l'appelant peut omettre l'argument lors de l'appel de la fonction, à moins de vouloir spécifier une autre valeur.  
  
```  
int DoSomething(int num,   
    string str,   
    Allocator& alloc = defaultAllocator)  
{ ... }  
  
// OK both parameters are at end  
int DoSomethingElse(int num,   
    string str = string{ "Working" },   
    Allocator& alloc = defaultAllocator)  
{ ... }  
  
// C2548: 'DoMore': missing default parameter for parameter 2  
int DoMore(int num = 5, // Not a trailing parameter!  
    string str,  
    Allocator& = defaultAllocator)  
{...}  
```  
  
 Pour plus d'informations, consultez [Arguments par défaut](../cpp/default-arguments.md) et [Arguments par défaut pour les modèles de classe](../Topic/Default%20Arguments%20for%20Class%20Templates.md).  
  
## Types de retour de fonction  
 Une fonction ne peut pas retourner une autre fonction ni un tableau intégré ; toutefois, elle peut retourner des pointeurs vers ces types, ou une expression *lambda*, ce qui génère un objet de fonction.  À l'exception de ces cas, une fonction peut retourner une valeur de n'importe quel type qui est dans la portée, ou elle peut ne retourner aucune valeur, auquel cas le type de retour est `void`.  
  
### Types de retours de fin  
 Un type de retour « ordinaire » se trouve sur le côté gauche de la signature de fonction.  Un *type de retour de fin* se trouve sur le côté droit de la signature et est précédé par l'opérateur \-\>.  Les types de retours de fin sont particulièrement utiles dans les modèles de fonction quand le type de la valeur de retour dépend des paramètres de modèle.  
  
```  
template<typename Lhs, typename Rhs>  
auto Add(const Lhs& lhs, const Rhs& rhs) -> decltype(lhs + rhs)  
{  
    return lhs + rhs;   
}  
```  
  
 Quand `auto` est utilisé avec un type de retour de fin, il sert seulement d'espace réservé pour le résultat produit par l'expression decltype et n'effectue pas lui\-même de déduction de type.  
  
###  <a name="type_deduction"></a> Déduction de type dans les types de retours \(C\+\+14\)  
 En C\+\+14, vous pouvez utiliser `auto` pour indiquer au compilateur de déduire le type de retour du corps de fonction sans avoir à fournir un type de retour de fin.  Notez qu'`auto` est toujours déduit à un retour par valeur.  Utilisez `auto&&` pour indiquer au compilateur de déduire une référence.  
  
 Dans cet exemple, `auto` sera déduit en tant que copie de valeur non\-const de la somme de lhs et rhs.  
  
```  
template<typename Lhs, typename Rhs>  
auto Add2(const Lhs& lhs, const Rhs& rhs)  
{  
    return lhs + rhs; //returns a non-const object by value  
}  
```  
  
 Notez qu'`auto` ne conserve pas non plus la nature const du type déduit.  Pour les fonctions de transfert dont la valeur de retour doit préserver la nature const ou ref de ses arguments, vous pouvez utiliser le mot clé `decltype(auto)`, qui utilise les règles d'inférence de type `decltype` et conserve toutes les informations de type.  `decltype(auto)` peut être utilisé comme valeur de retour ordinaire sur le côté gauche, ou en tant que valeur de retour de fin.  
  
 L'exemple suivant \(basé sur le code de [N3493](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2013/n3493.html)\) illustre l'utilisation de `decltype(auto)` pour permettre une transmission parfaite des arguments de fonction dans un type de retour inconnu jusqu'à ce que le modèle soit instancié.  
  
```  
template<typename F, typename Tuple = tuple<T...>, int... I>  
decltype(auto) apply_(F&& f, Tuple&& args, index_sequence<I...>)   
{  
    return std::forward<F>(f)(std::get<I>(std::forward<Tuple>(args))...);  
}  
  
template<typename F, typename Tuple = tuple<T...>,  
    typename Indices = make_index_sequence<tuple_size<Tuple>::value >>  
   decltype( auto)  
    apply(F&& f, Tuple&& args)      
{  
    return apply_(std::forward<F>(f), std::forward<Tuple>(args), Indices());  
}  
}  
```  
  
## Variables locales de fonction  
 Une variable déclarée à l'intérieur d'un corps de fonction est appelée une *variable locale*.  Les variables locales non statiques sont uniquement visibles à l'intérieur du corps de la fonction et, si elles sont déclarées sur la pile, sortent de la portée lors de la fermeture de la fonction.  Quand vous construisez une variable locale et la retournez par valeur, le compilateur peut généralement exécuter l'optimisation de la valeur de retour pour éviter des opérations de copie inutiles.  Si vous retournez une variable locale par référence, le compilateur émet un avertissement, car toute tentative d'utiliser cette référence par l'appelant se produit après la destruction de la variable locale.  
  
 Les objets statiques locaux sont détruits durant l'arrêt spécifié par `atexit`.  Si un objet statique n'a pas été construit car le flux de contrôle du programme a contourné sa déclaration, aucune tentative de destruction de cet objet n'est effectuée.  
  
### Variables locales statiques  
 En C\+\+, une variable locale peut être déclarée comme statique.  La variable n'est visible que dans le corps de fonction, mais une seule copie de la variable existe pour toutes les instances de la fonction.  
  
## Pointeurs fonction  
 C\+\+ prend en charge les pointeurs de fonction de la même manière que le langage C.  Toutefois, une alternative de type plus sécurisé consiste généralement à utiliser un objet de fonction.  
  
 Il est recommandé d'utiliser `typedef` pour déclarer un alias pour le type de pointeur fonction si vous déclarez une fonction qui retourne un type de pointeur fonction.  Exemple :  
  
```  
typedef int (*fp)(int);  
fp myFunction(char* s); // function returning function pointer  
```  
  
 Si vous ne procédez pas ainsi, la syntaxe appropriée pour la déclaration de fonction peut être déduite de la syntaxe des déclarateurs pour le pointeur fonction, en remplaçant l'identificateur \(`fp` dans l'exemple ci\-dessus\) par la liste de noms et d'arguments de fonctions, comme suit :  
  
```  
int (*myFunction(char* s))(int);  
```  
  
 La déclaration précédente est équivalente à la déclaration utilisant typedef ci\-dessus.  
  
## Voir aussi  
 [Surcharge de fonction](../cpp/function-overloading.md)   
 [Fonctions avec listes d'arguments variables](../cpp/functions-with-variable-argument-lists-cpp.md)   
 [Fonctions utilisées par défaut et supprimées explicitement](../cpp/explicitly-defaulted-and-deleted-functions.md)   
 [Recherche de nom qui dépend de l'argument \(Koenig\) sur les fonctions](../cpp/argument-dependent-name-koenig-lookup-on-functions.md)   
 [Arguments par défaut](../cpp/default-arguments.md)   
 [Fonctions inline](../cpp/inline-functions-cpp.md)