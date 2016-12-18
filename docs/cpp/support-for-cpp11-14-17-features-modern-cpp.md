---
title: "Prise en charge des fonctionnalit&#233;s C++11/14/17 (Modern C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: dd2d5cbc-caf5-4a11-a057-8c365decba4e
caps.latest.revision: 59
caps.handback.revision: 56
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Prise en charge des fonctionnalit&#233;s C++11/14/17 (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article décrit les fonctionnalités C\+\+11\/14\/17 de Visual C\+\+.  
  
##  <a name="top"></a> Dans cet article  
  
-   [Liste des fonctionnalités C++11](#featurelist)  
  
    -   [Tableau des fonctionnalités du langage principal C++11](#corelanguagetable)  
  
    -   [Tableau des fonctionnalités du langage principal C++11 : concurrence](#concurrencytable)  
  
    -   [Fonctionnalités du langage principal C++11 : C99](#c99table)  
  
-   [Fonctionnalités du langage principal C++ 14](#cpp14table)  
  
-   [Fonctionnalités proposées du langage principal C++17](#cpp17table)  
  
-   [Guide des tableaux de fonctionnalités](#tableguide)  
  
    -   [Références Rvalue](#rvref)  
  
    -   [Lambdas](#lambdas)  
  
    -   [decltype](#decltype)  
  
    -   [Enums fortement typés/déclarés avec anticipation](#stronglytyped)  
  
    -   [Alignement](#alignment)  
  
    -   [Types de disposition standard et types triviaux](#standardlayout)  
  
    -   [Fonctions utilisées par défaut et supprimées](#defaultedanddeleted)  
  
    -   [override et final](#overrideandfinal)  
  
    -   [Éléments atomiques et autres](#atomics)  
  
    -   [Règles de préprocesseur C99 __func__](#c99)  
  
-   [Fonctionnalités de bibliothèque standard](#stl)  
  
##  <a name="featurelist"></a> Liste des fonctionnalités C\+\+11  
 Visual C\+\+ implémente une grande majorité des fonctionnalités dans la [spécification du langage principal C\+\+11](http://go.microsoft.com/fwlink/p/?LinkID=235092), ainsi qu’un grand nombre de fonctionnalités de la bibliothèque C\+\+14 et certaines fonctionnalités proposées pour C\+\+17. Le tableau suivant répertorie les fonctionnalités du langage principal C\+\+11\/14\/17, ainsi que leur état d’implémentation dans Visual C\+\+ dans Visual Studio 2010, [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)], [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] et Visual Studio 2015.  
  
###  <a name="corelanguagetable"></a> Tableau des fonctionnalités du langage principal C\+\+11  
  
|[Fonctionnalités du langage principal C\+\+11](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2009/n2869.html)|Visual Studio 2010|Visual Studio 2012|[!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]|Visual Studio 2015|  
|------------------------------------------------------------------------------------------------------------------------|------------------------|------------------------|--------------------------------------------------------------|------------------------|  
|Références Rvalue [v0.1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1610.html), [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n2118.html), [v2.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2009/n2844.html), [v2.1](http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_defects.html), [v3.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2010/n3053.html)|v2.0|v2.1\*|v2.1\*|V3.0|  
|[Qualificateurs ref](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2439.htm)|Non|Non|Non|Oui|  
|[Initialiseurs de données membres non statiques](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2756.htm)|Non|Non|[Oui](../cpp/uniform-initialization-and-delegating-constructors.md)|Oui|  
|Modèles variadiques [v0.9](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2242.pdf), [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2555.pdf)|Non|Non|[Oui](../cpp/ellipses-and-variadic-templates.md)|Oui|  
|[Listes d’initialiseurs](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2672.htm)|Non|Non|[Oui](../cpp/uniform-initialization-and-delegating-constructors.md)|Oui|  
|[static\_assert](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1720.html)|Oui|Oui|Oui|Oui|  
|auto [v0.9](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1984.pdf), [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2546.htm)|v1.0|v1.0|v1.0|Oui|  
|[Types de retours de fin](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2541.htm)|Oui|Oui|Oui|Oui|  
|Lambdas [v0.9](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2550.pdf), [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2658.pdf), [v1.1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2009/n2927.pdf)|v1.0|v1.1|v1.1|Oui|  
|decltype [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2343.pdf), [v1.1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2011/n3276.pdf)|v1.0|v1.1\*\*|v1.1|Oui|  
|[Crochets angulaires à droite](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2005/n1757.html)|Oui|Oui|Oui|Oui|  
|[Arguments du modèle par défaut pour les modèles de fonctions](http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_defects.html)|Non|Non|Oui|Oui|  
|[Expression SFINAE](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2634.html)|Non|Non|Non|Non|  
|[Modèles d’alias](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2258.pdf)|Non|Non|[Oui](../cpp/aliases-and-typedefs-cpp.md)|Oui|  
|[Modèles externes](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1987.htm)|Oui|Oui|Oui|Oui|  
|[nullptr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2431.pdf)|Oui|Oui|Oui|Oui|  
|[Enums fortement typées](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2347.pdf)|Partial|Oui|Oui|Oui|  
|[Enums avec déclaration anticipée](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2764.pdf)|Non|Oui|Oui|Oui|  
|[Attributs](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2761.pdf)|Non|Non|Non|Oui|  
|[constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2235.pdf)|Non|Non|Non|Oui|  
|[Alignement](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2341.pdf)|TR1|Partial|Partial|Oui|  
|[Constructeurs effectuant une délégation](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1986.pdf)|Non|Non|[Oui](../cpp/uniform-initialization-and-delegating-constructors.md)|Oui|  
|[Héritage de constructeurs](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2540.htm)|Non|Non|Non|Oui|  
|[Opérateurs de conversion explicite](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2437.pdf)|Non|Non|Oui|Oui|  
|[char16\_t\/char32\_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2249.html)|Non|Non|Non|Oui|  
|[Littéraux de chaîne Unicode](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2442.htm)|Non|Non|Non|Oui|  
|[Littéraux de chaîne bruts](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2442.htm)|Non|Non|[Oui](../cpp/string-and-character-literals-cpp.md)|Oui|  
|[Noms de caractères universels dans les littéraux](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2170.html)|Non|Non|Non|Oui|  
|[Littéraux définis par l’utilisateur](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2765.pdf)|Non|Non|Non|Oui|  
|[Types de disposition standard et types triviaux](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2342.htm)|Non|Oui|Oui|Oui|  
|[Fonctions utilisées par défaut et supprimées](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2346.htm)|Non|Non|[Oui\*](../cpp/explicitly-defaulted-and-deleted-functions.md)|Oui|  
|[Déclarations Friend étendues](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2005/n1791.pdf)|Oui|Oui|Oui|Oui|  
|[sizeof étendu](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2253.html)|Non|Non|Non|Oui|  
|[Espaces de noms inline](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2535.htm)|Non|Non|Non|Oui|  
|[Unions non restreintes](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2544.pdf)|Non|Non|Non|Oui|  
|[Types locaux et sans nom comme arguments de modèle](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2657.htm)|Oui|Oui|Oui|Oui|  
|[Boucle For basée sur une plage](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2009/n2930.html)|Non|Oui|Oui|Oui|  
|override et final [v0.8](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2009/n2928.htm), [v0.9](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2010/n3206.htm), [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2011/n3272.htm)|Partial|Oui|Oui|Oui|  
|[Prise en charge minimale du GC](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2670.htm)|Oui|Oui|Oui|Oui|  
|[noexcept](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2010/n3050.html)|Non|Non|Non|Oui|  
  
 \[[Dans cet article](#top)\]  
  
###  <a name="concurrencytable"></a> Tableau des fonctionnalités du langage principal C\+\+11 : concurrence  
  
|Fonctionnalités du langage principal C\+\+11 : concurrence|Visual Studio 2010|Visual Studio 2012|[!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]|Visual Studio 2015|  
|----------------------------------------------------------------|------------------------|------------------------|--------------------------------------------------------------|------------------------|  
|[Points de séquence reformulés](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2239.html)|N\/A|N\/A|N\/A|Oui|  
|[Éléments atomiques](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2427.html)|Non|Oui|Oui|Oui|  
|[Comparaison et échange forts](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2748.html)|Non|Oui|Oui|Oui|  
|[Délimitations bidirectionnelles](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2752.htm)|Non|Oui|Oui|Oui|  
|[Modèle de mémoire](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2429.htm)|N\/A|N\/A|N\/A|Oui|  
|[Classement des dépendances de données](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2664.htm)|Non|Oui|Oui|Oui|  
|[Classement des dépendances de données : annotation de fonction](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2782.htm)|Non|Non|Non|Oui|  
|[exception\_ptr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2179.html)|Oui|Oui|Oui|Oui|  
|[quick\_exit](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2440.htm)|Non|Non|Non|Oui|  
|[Éléments atomiques des manipulateurs de signal](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2547.htm)|Non|Non|Non|Non|  
|[Stockage local des threads](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2659.htm)|Partial|Partial|Partial|Oui|  
|[Statiques « magiques »](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2660.htm)|Non|Non|Non|Oui|  
  
 \[[Dans cet article](#top)\]  
  
###  <a name="c99table"></a> Fonctionnalités du langage principal C\+\+11 : C99  
  
|Fonctionnalités du langage principal C\+\+11 : C99|Visual Studio 2010|Visual Studio 2012|[!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]|Visual Studio 2015|  
|--------------------------------------------------------|------------------------|------------------------|--------------------------------------------------------------|------------------------|  
|[\_\_func\_\_](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2340.htm)|Partial|Partial|Partial|Oui|  
|[Préprocesseur C99](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1653.htm)|Partial|Partial|Partial|Partial|  
|[long long](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2005/n1811.pdf)|Oui|Oui|Oui|Oui|  
|[Types entiers étendus](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1988.pdf)|N\/A|N\/A|N\/A|N\/A|  
  
 \[[Dans cet article](#top)\]  
  
###  <a name="cpp14table"></a> Fonctionnalités du langage principal C\+\+ 14  
  
||||  
|-|-|-|  
|Fonctionnalité|Visual Studio 2013|Visual Studio 2015|  
|Formulation optimisée pour les conversions contextuelles|Oui|Oui|  
|Littéraux binaires|Non|Oui|  
|Types de retour auto et decltype\(auto\)|Non|Oui|  
|init\-captures|Non|Oui|  
|Expressions lambda génériques|Non|Oui|  
|Modèles de variables|Non|Non|  
|Fonctions constexpr étendues|Non|Non|  
|NSDMI pour agrégats|Non|Non|  
|Prévention\/fusion des allocations|Non|Non|  
|Attributs \[\[deprecated\]\]|Non|Non|  
|Allocation dimensionnée|Non|Oui|  
|Séparateurs de chiffres|Non|Oui|  
  
###  <a name="cpp17table"></a> Fonctionnalités proposées du langage principal C\+\+17  
  
||||  
|-|-|-|  
|Fonctionnalité|Visual Studio 2013|Visual Studio 2015|  
|Nouvelles règles pour auto avec braced\-init\-lists|Non|Non|  
|static\-assert court|Non|Non|  
|typename dans les paramètres template template|Non|Non|  
|Suppression des trigraphes|Oui|Oui|  
|Définitions d'espaces de noms imbriqués|Non|Non|  
|N4259 std::uncaught\_exceptions\(\)|Non|Non|  
|N4261 Correction des conversions de qualifications|Non|Non|  
|N4266 Attributs pour espaces de noms et énumérateurs|Non|Non|  
|N4267 Littéraux de caractère u8|Non|Non|  
|N4268 Autorisation de plusieurs arguments de modèle sans type|Non|Non|  
|N4295 Expressions fold|Non|Non|  
|await\/resume|Non|Oui|  
  
##  <a name="tableguide"></a> Guide des tableaux de fonctionnalités  
  
###  <a name="rvref"></a> Références Rvalue  
  
> [!NOTE]
>  Les désignations de version \(v0.1, v1.0, v2.0, v2.1 et v3.0\) figurant dans les descriptions suivantes ont été inventées uniquement pour montrer l'évolution de C\+\+11. Le standard lui\-même ne les utilise pas.  
  
 Le document [N1610 « Clarification of Initialization of Class Objects by rvalues »](http://go.microsoft.com/fwlink/p/?LinkID=235093) était une première tentative pour permettre le déplacement de sémantique sans références rvalue.  Dans cette discussion, appelons cela « références rvalue v0.1 ». Ceci a été remplacé par les « références rvalue [v1.0](http://go.microsoft.com/fwlink/p/?LinkID=235094) ». Les « références rvalue [v2.0](http://go.microsoft.com/fwlink/p/?LinkID=235095) », sur lesquelles repose le travail dans Visual C\+\+ de Visual Studio 2010, interdit aux références rvalue de créer une liaison à des lvalues et résout ainsi un problème de sécurité majeur.  Les « références rvalue [v2.1](http://go.microsoft.com/fwlink/p/?LinkID=235096) » affinent cette règle.  Tenez compte de `vector<string>::push_back()`, qui a les surcharges `push_back(const string&)` et `push_back(string&&)`, et l’appel `v.push_back("strval")`.  L'expression `"strval"` est un littéral de chaîne et représente une lvalue.  \(Les autres littéraux, par exemple le nombre entier 1 729, sont des rvalues, mais les littéraux de chaîne sont spéciaux car il s'agit de tableaux.\)  Les règles des « références rvalue v2.0 » révèlent que `string&&` ne peut pas créer de liaison avec `"strval"` car `"strval"` est une lvalue et que `push_back(const string&)` est donc la seule surcharge valide.  Cela crée une `std::string`temporaire, la copie dans le vecteur, puis détruit la `std::string`temporaire, qui n'était pas très efficace. Les règles des « références rvalue v2.1 » identifient que la liaison de `string&&` avec `"strval"` créerait une `std::string`temporaire, et que temporaire est une rvalue.  Par conséquent, `push_back(const string&)` et `push_back(string&&)` sont viables et `push_back(string&&)` est préféré.  Une `std::string` temporaire est construite, puis déplacée dans le vecteur.  Cette méthode est plus efficace.  
  
 Les « références rvalue [v3.0](http://go.microsoft.com/fwlink/p/?LinkID=235097) » ajoutent des règles pour générer automatiquement des constructeurs de déplacement et pour déplacer des opérateurs d’affectation sous certaines conditions. Ceci est implémenté dans Visual Studio 2015.  
  
 \[[Dans cet article](#top)\]  
  
###  <a name="lambdas"></a> Lambdas  
 Après que les [fonctions lambda](../cpp/lambda-expressions-in-cpp.md) ont été déclarées dans le document de travail \([version « 0.9 »](http://go.microsoft.com/fwlink/p/?LinkID=235098)\) et que les lambdas mutables ont été ajoutés \([version « 1.0 »](http://go.microsoft.com/fwlink/p/?LinkID=235099)\), le Comité de normalisation en a révisé la formulation. Ceci a produit les expressions lambda [version « 1.1 »](http://go.microsoft.com/fwlink/p/?LinkID=235100), qui sont maintenant entièrement prises en charge.  Les lambdas v1.1 clarifient ce qui doit se produire en cas de référence à des membres statiques ou des lambdas imbriqués.  Cela corrige les problèmes déclenchés par les expressions lambda complexes.  En outre, les expressions lambda sans état sont maintenant convertissables en pointeurs de fonction.  Ce n’est pas dans la formulation N2927, mais est considéré comme faisant partie, néanmoins, des expressions lambda v1.1.[C\+\+11](http://go.microsoft.com/fwlink/p/?LinkID=235092) **5.1.2 \[expr.prim.lambda\]\/6** a cette description : « Le type de clôture d’une `lambda-capture` sans `lambda-expression` a une fonction de conversion const non explicite non virtuelle publique de conversion en pointeur vers une fonction ayant les mêmes types de paramètres et de retours que l’opérateur d’appel de fonction du type de la clôture. La valeur retournée par cette fonction de conversion est l’adresse d’une fonction qui, quand elle est appelée, a le même effet que l’appel de l’opérateur d’appel de fonction du type de la clôture ».  \(L’implémentation [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] est encore meilleure, car elle rend les expressions lambdas sans état convertibles en pointeurs de fonction qui ont des conventions d’appel arbitraires.  Ceci est important lorsque vous utilisez des API qui attendent des éléments comme des pointeurs de fonction `__stdcall`.\)  
  
 \[[Dans cet article](#top)\]  
  
###  <a name="decltype"></a> decltype  
 Après que decltype a été déclaré dans le document de travail \([version 1.0](http://go.microsoft.com/fwlink/p/?LinkID=235101)\), il a reçu à la dernière minute une petite correction qui est importante \([version 1.1](http://go.microsoft.com/fwlink/p/?LinkID=235102)\).  Cela présente un grand intérêt pour les programmeurs qui travaillent dans STL et Boost.  
  
 \[[Dans cet article](#top)\]  
  
###  <a name="stronglytyped"></a> Enums fortement typés\/déclarés avec anticipation  
 Les [enums fortement typées](http://go.microsoft.com/fwlink/p/?LinkID=235103) étaient partiellement prises en charge dans Visual C\+\+ de Visual Studio 2010 \(en particulier, la partie concernant les types sous\-jacents explicitement spécifiés\). Celles\-ci sont maintenant entièrement implémentées dans Visual Studio, et la sémantique C\+\+11 pour les [enums avec déclaration anticipée](http://go.microsoft.com/fwlink/p/?LinkID=235104) est également entièrement implémentée.  
  
 \[[Dans cet article](#top)\]  
  
###  <a name="alignment"></a> Alignement  
 Les mots clés du langage principal `alignas`\/`alignof` de la [proposition d’alignement](http://go.microsoft.com/fwlink/p/?LinkID=235105) qui a été votée dans le document de travail sont implémentés dans Visual Studio 2015.  Visual C\+\+ dans Visual Studio 2010 avait `aligned_storage` à partir de TR1.[!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] a ajouté `aligned_union` et `std::align()` dans la bibliothèque standard et des problèmes importants ont été résolus dans [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)].  
  
 \[[Dans cet article](#top)\]  
  
###  <a name="standardlayout"></a> Types de disposition standard et types triviaux  
 Les modifications exposées issues du document [N2342 « POD’s Revisited; Resolving Core Issue 568 \(Revision 5\) »](http://go.microsoft.com/fwlink/p/?LinkID=235106) sont les ajouts de `is_trivial` et de `is_standard_layout` aux `<type_traits>` de la bibliothèque STL \(Standard Template Library\).  \(N2342 a retouché une grande partie du libellé du langage principal, mais aucun changement de compilateur n’est nécessaire.\)  Ces caractéristiques de type étaient disponibles dans Visual C\+\+ de Visual Studio 2010, mais elles ont seulement dupliqué `is_pod`. Par conséquent, la table évoquée plus haut dans ce document indiquait « Non » pour la prise en charge.  Ils sont maintenant actionnés par des raccordements de compilateur qui permettent de proposer des réponses exactes.  
  
 Le [common\_type\<\>](../standard-library/common-type-class.md) de la bibliothèque STL a fait l'objet d'un correctif fort attendu dans [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)].  La spécification C\+\+11 pour `common_type<>` avait des conséquences inattendues et indésirables ; en particulier, `common_type<int, int>::type` retournait `int&&`. Par conséquent, [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] implémente la [Résolution proposée pour le problème 2141 du groupe de travail sur les bibliothèques](http://go.microsoft.com/fwlink/p/?LinkId=320075), qui fait que `common_type<int, int>::type` retourne `int`.  
  
 Effet secondaire de cette modification : le cas d’identité ne s’exécute plus \(`common_type<T>` ne produit pas toujours le type `T`\). Cela est conforme à la résolution proposée, mais interrompt le code qui était fondé sur le comportement précédent.  
  
 Si une caractéristique de type identité est requise, n'utilisez pas la caractéristique `std::identity` non standard définie dans `<type_traits>`, car elle ne fonctionnera pas pour `<void>`. À la place, implémentez votre propre caractéristique de type d'identité pour répondre à vos besoins. Voici un exemple :  
  
```cpp  
template <typename T> struct Identity { typedef T type; };  
  
```  
  
> [!NOTE]
>  Pour les autres modifications fondamentales, consultez [Modifications avec rupture dans Visual C\+\+ 2015](../porting/visual-cpp-change-history-2003-20151.md).  
  
 \[[Dans cet article](#top)\]  
  
###  <a name="defaultedanddeleted"></a> Fonctions utilisées par défaut et supprimées  
 Celles\-ci sont maintenant prises en charge, mais avec cette exception : pour les fonctions utilisées par défaut, l'utilisation de `=default` pour demander le déplacement de constructeurs et d'opérateurs d'assignation n'est pas prise en charge. Les copies et les déplacements n’interagissent pas précisément comme le prétend la norme. Par exemple, la suppression des déplacements est spécifiée pour supprimer également les copies, mais ce n’est pas le cas de [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)].  
  
 Pour plus d’informations sur l’utilisation des fonctions par défaut et supprimées, consultez [Fonctions](../cpp/functions-cpp.md).  
  
 \[[Dans cet article](#top)\]  
  
###  <a name="overrideandfinal"></a> override et final  
 L’évolution a été brève, mais complexe. Initialement, dans la [version 0.8](http://go.microsoft.com/fwlink/p/?LinkID=235108), il existait les attributs \[\[`override`\]\], \[\[`hiding`\]\] et \[\[`base_check`\]\].  Ensuite, dans la [version 0.9](http://go.microsoft.com/fwlink/p/?LinkID=235109), les attributs ont été supprimés et remplacés par des mots clés contextuels.  Enfin, dans la [version 1.0](http://go.microsoft.com/fwlink/p/?LinkID=235110), ils ont été réduits à « `final` » sur les classes, et à « `override` » et « `final` » sur les fonctions.  Ceci en fait une extension ascendante, car Visual C\+\+ dans Visual Studio 2010 prenait déjà en charge cette syntaxe « `override` » sur les fonctions et avait une sémantique assez proche de celle de C\+\+11.  « `final` » était également pris en charge, mais avec l’orthographe différente « sealed ».  L’orthographe et la sémantique standard de « `override` » et « `final` » sont maintenant complètement prises en charge. Pour plus d’informations, consultez [Spécificateur de substitution](../cpp/override-specifier.md) et [Spécificateur final](../cpp/final-specifier.md).  
  
 \[[Dans cet article](#top)\]  
  
###  <a name="atomics"></a> Éléments atomiques et autres  
 [Les éléments atomiques](http://go.microsoft.com/fwlink/p/?LinkID=235111), [les comparaisons et les échanges forts](http://go.microsoft.com/fwlink/p/?LinkID=235112), [les délimitations bidirectionnelles](http://go.microsoft.com/fwlink/p/?LinkID=235113) et [le classement des dépendances de données](http://go.microsoft.com/fwlink/p/?LinkID=235114) spécifient un mécanisme de bibliothèque standard, qui est maintenant implémenté.  
  
 **En\-têtes STL associés :** [\<atomic\>](../standard-library/atomic.md), [\<chrono\>](../standard-library/chrono.md), [\<condition\_variable\>](../standard-library/condition-variable.md), [\<future\>](../standard-library/future.md), [\<mutex\>](../standard-library/mutex.md), [\<ratio\>](../standard-library/ratio.md), [\<scoped\_allocator\>](../standard-library/scoped-allocator.md) et [\<thread\>](../standard-library/thread.md).  
  
 \[[Dans cet article](#top)\]  
  
###  <a name="c99"></a> Règles de préprocesseur C99 \_\_func\_\_  
 Le tableau [Fonctionnalités du langage principal C++11 : C99](#c99table) indique une implémentation « partielle » pour deux éléments. Pour l’identificateur prédéfini `__func__`, la mention « Partielle » figure dans le tableau car une prise en charge est fournie pour les extensions non standard `__FUNCDNAME__`, `__FUNCSIG__` et `__FUNCTION__`. Pour plus d’informations, consultez [Macros prédéfinies](../preprocessor/predefined-macros.md). Pour les règles du préprocesseur C99, la mention « Partielle » est répertoriée car les *macros variadiques* sont prises en charge. Pour plus d’informations, consultez [Macros Variadic](../preprocessor/variadic-macros.md).  
  
 \[[Dans cet article](#top)\]  
  
###  <a name="stl"></a> Fonctionnalités de bibliothèque standard  
 Cela couvre le langage principal. Comme pour la bibliothèque standard C\+\+11, nous n'avons pas une grande table de comparaison des fonctionnalités, mais [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] les a implémentées, avec deux exceptions.  Tout d'abord, lorsqu'une fonctionnalité de bibliothèque dépendait d'une fonctionnalité qui manquait dans le compilateur, celle\-ci était simulée, par exemple, des modèles variadiques simulés pour `make_shared<T>()`, ou n'était pas implémentée. \(Il n’y avait que quelques cas, principalement `<initializer_list>`, qui ont été totalement implémentés dans [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)].\)  À quelques exceptions près, C99 a été implémenté dans [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] et les en\-têtes de wrapper C\+\+ fournis. Pour plus d’informations, consultez [Prise en charge de la bibliothèque C99 dans Visual Studio 2013](http://go.microsoft.com/fwlink/p/?LinkId=321308).  
  
 Voici une liste partielle des modifications dans [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] et [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] :  
  
 **Emplacement :** comme requis par C\+\+11, `emplace()`\/`emplace_front()`\/`emplace_back()`\/`emplace_hint()`\/`emplace_after()` sont implémentés dans tous les conteneurs pour les nombres « arbitraires » d'arguments \(consultez la section sur les « variadiques simulés »\).  Par exemple, `vector<T>` a « `template <typename... Args> void emplace_back(Args&&... args)` » qui construit directement un élément de type T à l'arrière du vecteur à partir d'un nombre arbitraire d'arguments arbitraires, parfaitement transférés.  Cela peut être plus efficace que `push_back(T&&)`, qui comporterait une construction et une destruction de déplacements supplémentaires.  
  
 **Variadiques :** [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] comportait un schéma pour simuler les modèles variadiques. Dans [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], les simulations ont disparu et les **modèles variadiques sont entièrement implémentés**. Si votre code dépend de l'ancien comportement des modèles variadiques simulés, vous devez le corriger. Toutefois, l'implémentation de modèles variadiques réels a **amélioré les délais de compilation** et **réduit la consommation de la mémoire du compilateur**.  
  
 **Opérateurs de conversion explicites :** dans le langage principal, les opérateurs de conversion explicites sont une fonctionnalité générale ; par exemple, vous pouvez avoir `explicit operator MyClass()`. Toutefois, la bibliothèque standard n'utilise actuellement qu'un seul formulaire : `explicit operator bool()`, qui rend les classes booléennes testables en toute sécurité. \(Un simple « `operator bool()` » est notoirement dangereux.\) Auparavant, Visual C\+\+ simulait `explicit operator bool()` avec `operator pointer-to-member()`, ce qui a entraîné plusieurs problèmes et un léger manque d'efficacité. À présent, cette solution de contournement « fausse valeur booléenne » est complètement supprimée.  
  
 **Caractère aléatoire :** `uniform_int_distribution` est maintenant parfaitement impartial et `shuffle()` est implémenté dans `<algorithm>`, qui accepte directement les générateurs de nombres aléatoires uniformes, comme `mersenne_twister`.  
  
 **Résistance aux opérateurs d’adresse surchargés :** C\+\+98\/03 interdisait à un élément de conteneur STL de surcharger son opérateur d’adresse.  C'est ainsi que les classes comme `CComPtr` agissent, afin que les classes d'assistance comme `CAdapt` soient obligées de protéger la bibliothèque STL de telles surcharges.  Pendant le développement de Visual C\+\+ dans Visual Studio 2010, les modifications apportées à STL provoquent le rejet des opérateurs address\-of surchargés dans davantage de situations. C\+\+11 a modifié les spécifications visant à rendre les opérateurs d'adresse surchargés acceptables. C\+\+11 et Visual C\+\+ dans Visual Studio 2010 fournissent la fonction d'assistance `std::addressof()`, qui peut obtenir l'adresse exacte d'un objet, quelle que soit la surcharge d'opérateur.  Avant la parution de Visual C\+\+ dans Visual Studio 2010, nous avons essayé de remplacer les occurrences de « `&elem` » par « `std::addressof(elem)` », qui présente la résistance appropriée.[!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] est allé plus loin, pour que les classes qui surchargent leur opérateur address\-of soient utilisables dans l’ensemble de la bibliothèque STL.  
  
 **[!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] a dépassé C\+\+11 de plusieurs façons :**  
  
 **Itérateurs SCARY :** comme c’est autorisé mais pas obligatoire dans la norme C\+\+11, les itérateurs SCARY ont été implémentés, conformément à ce qui est décrit dans [N2911 « Minimizing Dependencies within Generic Classes for Faster and Smaller Programs »](http://go.microsoft.com/fwlink/p/?LinkID=235115) et dans [N2980 « SCARY Iterator Assignment and Initialization, Revision 1 »](http://go.microsoft.com/fwlink/p/?LinkID=235116).  
  
 **Filesystem :** l’en\-tête `<filesystem>` de [la proposition TR2](http://go.microsoft.com/fwlink/p/?LinkID=235117) a été ajouté. Il offre `recursive_directory_iterator` et d’autres fonctionnalités intéressantes.  Avant que le travail sur TR2 ne soit stoppé en raison du fait que C\+\+0x s’est prolongé très tard et qu’il était devenu C\+\+11, la proposition 2006 a été dérivée de [Boost.Filesystem V2](http://go.microsoft.com/fwlink/p/?LinkID=235118). Il a ensuite évolué vers Boost.Filesystem V3, qui est implémenté dans Visual Studio 2015.  
  
 Et une optimisation importante \!  Tous nos conteneurs sont désormais réduits de façon optimale au vu de leurs représentations actuelles.  Cela fait référence aux objets conteneurs eux\-mêmes, pas aux contenus vers lesquels ils pointent.  Par exemple, `std::vector` contient trois pointeurs bruts.  En Visual C\+\+ dans Visual Studio 2010, le mode release x86, `std::vector` était de 16 octets.  Dans [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)], il est de 12 octets, ce qui est réduit de façon optimale.  La belle affaire : si vous avez 100 000 vecteurs dans votre programme, [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] vous fait gagner 400 000 octets.  L'utilisation réduite de la mémoire permet d'économiser de l'espace et du temps.  
  
 Cela a été accompli en évitant le stockage d'allocateurs et comparateurs vides, car `std::allocator` et `std::less` sont sans état.  \(Ces optimisations sont activées pour les allocateurs\/comparateurs personnalisés, tant qu'elles sont sans état.  Évidemment, le stockage d’allocateurs\/de comparateurs avec état est inévitable, mais il s’agit de cas très rares.\)  
  
 **[!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] a implémenté certaines fonctionnalités clés de la bibliothèque C\+\+14 :**  
  
-   « Foncteurs d’opérateurs transparents » `less<>`, `greater<>`, `plus<>`, `multiplies<>`, et ainsi de suite.  
  
-   `make_unique<T>(args...)` et `make_unique<T[]>(n)`  
  
-   Fonctions non membres `cbegin()`\/`cend()`, `rbegin()`\/`rend()` et `crbegin()`\/`crend()`.  
  
 \[[Dans cet article](#top)\]  
  
## Voir aussi  
 [Bienvenue dans C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Expressions lambda](../cpp/lambda-expressions-in-cpp.md)   
 [Basé sur une plage, instruction \(C\+\+\)](../cpp/range-based-for-statement-cpp.md)   
 [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md)   
 [Blog de l’équipe Visual C\+\+](http://blogs.msdn.com/b/vcblog/)   
 [Nouveautés dans Visual C\+\+](../top/what-s-new-for-visual-cpp-in-visual-studio-2015.md)   
 [Modifications avec rupture dans Visual C\+\+ 2015](../porting/visual-cpp-change-history-2003-20151.md)