---
title: "It&#233;rateurs de d&#233;bogage, prise en charge | Microsoft Docs"
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
  - "_HAS_ITERATOR_DEBUGGING symbol"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "itérateurs de débogage (prise en charge)"
  - "itérateurs incompatibles"
  - "itérateurs, itérateurs de débogage (prise en charge)"
  - "itérateurs, incompatibles"
  - "bibliothèques sécurisées"
  - "bibliothèques sécurisées, bibliothèque C++ standard"
  - "bibliothèque C++ standard sécurisée"
  - "bibliothèque C++ standard, itérateurs de débogage (prise en charge)"
ms.assetid: f3f5bd15-4be8-4d64-a4d0-8bc0761c68b6
caps.latest.revision: 22
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# It&#233;rateurs de d&#233;bogage, prise en charge
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque Runtime Visual C\+\+ détecte l'utilisation incorrecte itérateur, et affirme et affiche une boîte de dialogue lors de l'exécution.  Pour permettre la prise en charge d'itérateur de débogage, vous devez utiliser une version de débogage de la bibliothèque Runtime c en cours pour compiler votre programme.  Pour plus d'informations, consultez [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md).  Pour plus d'informations sur l'utilisation des itérateurs, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
 La norme C\+\+ décrit comment les fonctions membres peuvent entraîner des itérateurs à un conteneur valides.  Deux exemples :  
  
-   Effacer un élément d'un conteneur a pour devenir des itérateurs à l'élément non valide.  
  
-   Augmenter la taille d'[vecteur](../standard-library/vector.md) \(par émission ou insert\) entraîne devenir des itérateurs dans `vector` valide.  
  
## Exemple  
 Si vous compilez le programme suivant en mode débogage, au moment de l'exécution de données SQL server vérifie et de fin.  
  
```cpp  
/* compile with /EHsc /MDd */  
#include <vector>  
#include <iostream>  
  
int main() {  
   std::vector<int> v ;  
  
   v.push_back(10);  
   v.push_back(15);  
   v.push_back(20);  
  
   std::vector<int>::iterator i = v.begin();  
   ++i;  
  
   std::vector<int>::iterator j = v.end();  
   --j;  
  
   std::cout<<*j<<'\n';  
  
   v.insert(i,25);   
  
   std::cout<<*j<<'\n'; // Using an old iterator after an insert  
}  
  
```  
  
## Exemple  
 Vous pouvez utiliser le symbole [\_HAS\_ITERATOR\_DEBUGGING](../standard-library/has-iterator-debugging.md) pour désactiver la fonctionnalité de débogage d'itération dans une version de débogage.  Le programme suivant n'affirme pas, mais les déclencheurs éliminaient toujours le comportement.  
  
> [!IMPORTANT]
>  Utilisation `_ITERATOR_DEBUG_LEVEL` de contrôler `_HAS_ITERATOR_DEBUGGING`.  Pour plus d'informations, consultez [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md).  
  
```cpp  
// iterator_debugging.cpp  
// compile with: /EHsc /MDd  
#define _HAS_ITERATOR_DEBUGGING 0  
#include <vector>  
#include <iostream>  
  
int main() {  
   std::vector<int> v ;  
  
   v.push_back(10);  
   v.push_back(15);  
   v.push_back(20);  
  
   std::vector<int>::iterator i = v.begin();  
   ++i;  
  
   std::vector<int>::iterator j = v.end();  
   --j;  
  
   std::cout<<*j<<'\n';  
  
   v.insert(i,25);   
  
   std::cout<<*j<<'\n'; // Using an old iterator after an insert  
}  
```  
  
  **20**  
**\-572662307**   
## Exemple  
 Une assertion se produit également si vous tentez d'utiliser un itérateur avant d'être initialisé, comme indiqué ici :  
  
```cpp  
/* compile with /EHsc /MDd */  
#include <string>  
using namespace std;  
int main() {  
   string::iterator i1, i2;  
   if (i1 == i2)  
      ;  
}  
```  
  
## Exemple  
 L'exemple suivant provoque une assertion car les deux itérateurs à l'algorithme d'[for\_each](../Topic/for_each.md) sont incompatibles.  Les algorithmes permettent de déterminer si les itérateurs fournis à elles référencent le même conteneur.  
  
```cpp  
/* compile with /EHsc /MDd */  
#include <algorithm>  
#include <vector>  
using namespace std;  
  
int main()  
{  
    vector<int> v1;  
    vector<int> v2;  
  
    v1.push_back(10);  
    v1.push_back(20);  
  
    v2.push_back(10);  
    v2.push_back(20);  
  
    // The next line will assert because v1 and v2 are  
    // incompatible.  
    for_each(v1.begin(), v2.end(), [] (int& elem) { elem *= 2; } );  
}  
```  
  
 Notez que cet exemple utilise l'expression lambda `[] (int& elem) { elem *= 2; }` au lieu d'un functor.  Bien que ce tableau est pas portant sur l'échec \(FCI\) assertion le functor que similaire changerait le même problème \- lambdas sont très une méthode utile d'effectuer des tâches compact de fonction.  Pour plus d'informations sur les expressions lambda, consultez [Expressions lambda](../cpp/lambda-expressions-in-cpp.md).  
  
## Exemple  
 Déboguer l'itérateur vérification également provoque une variable itérateur déclarée dans une boucle d'`for` soit hors de portée lorsque l'étendue de boucle d'`for` se termine.  
  
```cpp  
// debug_iterator.cpp  
// compile with: /EHsc /MDd  
#include <vector>  
#include <iostream>  
int main() {  
   std::vector<int> v ;  
  
   v.push_back(10);  
   v.push_back(15);  
   v.push_back(20);  
  
   for (std::vector<int>::iterator i = v.begin() ; i != v.end(); ++i)  
   ;  
   --i;   // C2065  
}  
```  
  
## Exemple  
 Les itérateurs de débogage ont les destructeurs non triviaux.  Si un destructeur ne fonctionne pas, pour quelque raison que ce soit, les violations d'accès et les données endommagées peuvent se produire.  Considérez cet exemple :  
  
```cpp  
/* compile with: /EHsc /MDd */  
#include <vector>  
struct base {  
   // FIX: uncomment the next line  
   // virtual ~base() {}  
};  
  
struct derived : base {  
   std::vector<int>::iterator m_iter;  
   derived( std::vector<int>::iterator iter ) : m_iter( iter ) {}  
   ~derived() {}  
};  
  
int main() {  
   std::vector<int> vect( 10 );  
   base * pb = new derived( vect.begin() );  
   delete pb;  // doesn't call ~derived()  
   // access violation  
}  
```  
  
## Voir aussi  
 [Vue d'ensemble de la bibliothèque STL](../standard-library/cpp-standard-library-overview.md)