---
title: "It&#233;rateurs v&#233;rifi&#233;s | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SECURE_SCL"
  - "_SECURE_SCL_THROWS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "itérateurs vérifiés"
  - "itérateurs, checked"
  - "bibliothèques sécurisées"
  - "bibliothèques sécurisées, bibliothèque C++ standard"
  - "bibliothèque C++ standard sécurisée"
ms.assetid: cfc87df8-e3d9-403b-ab78-e9483247d940
caps.latest.revision: 30
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# It&#233;rateurs v&#233;rifi&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les itérateurs vérifiés garantissent que les limites de votre conteneur ne sont pas remplacées.  
  
 Les itérateurs vérifiés s'appliquent aux versions Release et aux versions Debug.  Pour plus d'informations sur la façon d'utiliser des itérateurs lorsque vous compilez en mode débogage, consultez [Itérateurs de débogage, prise en charge](../standard-library/debug-iterator-support.md).  
  
## Notes  
 Pour plus d'informations sur la manière de désactiver les avertissements générés par les itérateurs vérifiés, consultez [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
 Vous pouvez utiliser le symbole suivant avec la fonctionnalité des itérateurs vérifiés.  
  
 `_SECURE_SCL`  
 Si `_SECURE_SCL` est défini sur 1, une utilisation non sécurisée d'itérateurs provoque une erreur d'exécution et le programme se termine.  S'il est défini sur 0, les itérateurs vérifiés sont désactivés.  Par défaut, la valeur de `_SECURE_SCL` est 0 pour les versions Release et 1 pour les versions Debug.  
  
> [!IMPORTANT]
>  Utilisez `_ITERATOR_DEBUG_LEVEL` pour contrôler [\_SECURE\_SCL](../standard-library/secure-scl.md).  Pour plus d'informations, consultez [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md).  
  
 Lorsque `_SECURE_SCL` a pour valeur 1, les vérifications SCL suivantes sont effectuées :  
  
-   Tous les itérateurs standard \(par exemple, [vector::iterator](../Topic/vector::iterator.md)\) sont vérifiés.  
  
-   Si un itérateur de sortie est un itérateur vérifié vous obtenez le comportement vérifié sur les appels à la fonction standard \(par exemple, [std::copy](../Topic/copy.md)\).  
  
-   Si l'itérateur de sortie est un itérateur non vérifié, les appels à la fonction standard entraînent des avertissements du compilateur.  
  
-   Les fonctions suivantes génèrent une erreur d'exécution s'il existe un accès hors des limites du conteneur :  
  
|||||  
|-|-|-|-|  
|[basic\_string::operator](../Topic/basic_string::operator.md)|[bitset::operator](../Topic/bitset::operator.md)|[deque::back](../Topic/deque::back.md)|[deque::front](../Topic/deque::front.md)|  
|[deque::operator](../Topic/deque::operator.md)|[list::back](../Topic/list::back.md)|[list::front](../Topic/list::front.md)|[queue::back](../Topic/queue::back.md)|  
|[queue::front](../Topic/queue::front.md)|[vector::operator](../Topic/vector::operator.md)|[vector::back](../Topic/vector::back.md)|[vector::front](../Topic/vector::front.md)|  
  
 Quand `_SECURE_SCL` a pour valeur 0 :  
  
-   Tous les itérateurs standard sont non vérifiés \(les itérateurs peuvent être déplacés au delà des limites du conteneur, ce qui entraîne un comportement non défini\).  
  
-   Si un itérateur de sortie est un itérateur vérifié vous obtenez un comportement vérifié sur les appels à la fonction standard \(par exemple, `std::copy`\).  
  
-   Si un itérateur de sortie est un itérateur non vérifié vous obtenez un comportement non vérifié sur les appels à la fonction standard \(par exemple, `std::copy`\).  
  
 Un itérateur vérifié fait référence à un itérateur qui appelle `invalid_parameter_handler` si vous tentez de dépasser les limites du conteneur.  Pour plus d'informations sur `invalid_parameter_handler`, consultez [Validation de paramètre](../c-runtime-library/parameter-validation.md).  
  
 [checked\_array\_iterator, classe](../standard-library/checked-array-iterator-class.md) et [unchecked\_array\_iterator, classe](../standard-library/unchecked-array-iterator-class.md) sont les adaptateurs d'itérateur qui prennent en charge les itérateurs vérifiés.  
  
## Exemple  
 Lorsque vous compilez à l'aide de `_SECURE_SCL 1`, une erreur d'exécution se produit si vous tentez d'accéder à un élément situé en dehors des limites du conteneur en utilisant l'opérateur d'indexation de certaines classes.  
  
```cpp  
// checked_iterators_1.cpp  
// cl.exe /Zi /MDd /EHsc /W4  
  
#define _ITERATOR_DEBUG_LEVEL 1  
// implies #define _SECURE_SCL 1  
  
#include <vector>  
#include <iostream>  
  
using namespace std;  
  
int main()   
{  
    vector<int> v;  
    v.push_back(67);  
  
    int i = v[0];  
    cout << i << endl;  
  
    i = v[1]; // triggers invalid parameter handler  
};  
  
```  
  
 Ce programme indiquera « 67 » en sortie et affichera une boîte de dialogue d'échec d'assertion avec des informations supplémentaires sur l'erreur.  
  
## Exemple  
 De même, lorsque vous compilez à l'aide de `_SECURE_SCL 1`, une erreur d'exécution se produit si vous tentez d'accéder à un élément en utilisant l'avant ou l'arrière de certaines classes, lorsque le conteneur est vide.  
  
```cpp  
// checked_iterators_2.cpp  
// cl.exe /Zi /MDd /EHsc /W4  
  
#define _ITERATOR_DEBUG_LEVEL 1  
// implies #define _SECURE_SCL 1  
  
#include <vector>  
#include <iostream>  
  
using namespace std;  
  
int main()   
{  
    vector<int> v;  
  
    int& i = v.front(); // triggers invalid parameter handler  
};  
  
```  
  
 Ce programme affichera une boîte de dialogue d'échec d'assertion avec des informations supplémentaires sur l'erreur.  
  
 Le code suivant illustre différents scénarios de cas d'usage d'itérateur avec des commentaires sur chacun d'eux.  
  
```cpp  
// cl.exe /MTd /EHsc /W4  
#include <algorithm>  
#include <array>  
#include <iostream>  
#include <iterator>  
#include <numeric>  
#include <string>  
#include <vector>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    vector<int> v(16);  
    iota(v.begin(), v.end(), 0);  
    print("v: ", v);  
  
    // OK: vector::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    vector<int> v2(16);  
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });  
    print("v2: ", v2);  
  
    // OK: back_insert_iterator is marked as checked in debug mode  
    // (i.e. an overrun is impossible)  
    vector<int> v3;  
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });  
    print("v3: ", v3);  
  
    // OK: array::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    array<int, 16> a4;  
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });  
    print("a4: ", a4);  
  
    // OK: Raw arrays are checked in debug mode  
    // (an overrun will trigger a debug assertion)  
    // NOTE: This applies only when raw arrays are given to STL algorithms!  
    int a5[16];  
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });  
    print("a5: ", a5);  
  
    // WARNING C4996: Pointers cannot be checked in debug mode  
    // (an overrun will trigger undefined behavior)  
    int a6[16];  
    int * p6 = a6;  
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });  
    print("a6: ", a6);  
  
    // OK: stdext::checked_array_iterator is checked in debug mode  
    // (an overrun will trigger a debug assertion)  
    int a7[16];  
    int * p7 = a7;  
    transform(v.begin(), v.end(), stdext::make_checked_array_iterator(p7, 16), [](int n) { return n * 7; });  
    print("a7: ", a7);  
  
    // WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode  
    // (it performs no checking, so an overrun will trigger undefined behavior)  
    int a8[16];  
    int * p8 = a8;  
    transform(v.begin(), v.end(), stdext::make_unchecked_array_iterator(p8), [](int n) { return n * 8; });  
    print("a8: ", a8);  
}  
  
```  
  
## Sortie  
 La compilation du code présenté dans la section précédente avec `cl.exe /EHsc /W4 /MTd` provoquera l'avertissement du compilateur suivant, mais s'effectuera sans erreur dans un fichier exécutable :  
  
```  
algorithm(1026) : warning C4996: 'std::_Transform1': Function call with parameters that may be unsafe - this call rel  
ies on the caller to check that the passed values are correct. To disable this warning, use -D_SCL_SECURE_NO_WARNINGS. See documentation on how to use Visual C++ 'Checked Iterators'  
```  
  
 L'exécution du fichier exécutable d'application console génère la sortie suivante :  
  
```  
v: 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15  
v2: 0 2 4 6 8 10 12 14 16 18 20 22 24 26 28 30  
v3: 0 3 6 9 12 15 18 21 24 27 30 33 36 39 42 45  
a4: 0 4 8 12 16 20 24 28 32 36 40 44 48 52 56 60  
a5: 0 5 10 15 20 25 30 35 40 45 50 55 60 65 70 75  
a6: 0 6 12 18 24 30 36 42 48 54 60 66 72 78 84 90  
a7: 0 7 14 21 28 35 42 49 56 63 70 77 84 91 98 105  
a8: 0 8 16 24 32 40 48 56 64 72 80 88 96 104 112 120  
```  
  
## Voir aussi  
 [Vue d'ensemble de la bibliothèque STL](../standard-library/cpp-standard-library-overview.md)   
 [Itérateurs de débogage, prise en charge](../standard-library/debug-iterator-support.md)