---
title: "Bienvenue dans C++ (Modern C++) | Microsoft Docs"
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
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
caps.latest.revision: 23
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Bienvenue dans C++ (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ est l'un des langages de programmation les plus couramment utilisés au monde.  Les programmes C\+\+ bien écrits sont rapides et efficaces.  Ce langage est plus flexible que d'autres, car il permet de créer une large gamme d'applications \(jeux divertissants et passionnants, logiciels scientifiques de pointe, pilotes de périphériques, programmes incorporés et applications clientes Windows\).  Depuis plus de 20 ans, C\+\+ est utilisé pour résoudre des problèmes similaires et beaucoup d'autres problèmes.  Ce que vous ne savez peut\-être pas, c'est qu'un nombre croissant de programmeurs C\+\+ ont abandonné l'ancienne programmation de type C inélégante au profit de la programmation moderne C\+\+.  
  
 L'une des spécifications d'origine du C\+\+ était la compatibilité descendante avec le langage C.  Depuis, le C\+\+ a évolué selon plusieurs itérations : C avec classes, spécification du langage C\+\+ d'origine, puis nombreuses améliorations ultérieures.  Du fait de cet héritage, C\+\+ est souvent appelé langage de programmation multiparadigme.  En C\+\+, vous pouvez effectuer de la programmation de style C purement procédurale qui comprend des pointeurs bruts, des tableaux, des chaînes de caractères se terminant par null, des structures de données personnalisées et d'autres fonctionnalités permettant de bénéficier de hautes performances mais pouvant donner lieu à des bogues et compliquer les choses.  Étant donné que la programmation de style C est chargée de périls comme ceux\-ci, l'un des objectifs fondamentaux pour C\+\+ était de sécuriser les programmes et de faciliter leur écriture, leur extension et leur mise à jour.  Au départ, C\+\+ comprenait des paradigmes de programmation tels que la programmation orientée objet.  Au fil des années, des fonctionnalités ont été ajoutées au langage, ainsi que des bibliothèques standard de structures de données et d'algorithmes largement éprouvées.  Ce sont ces ajouts qui ont rendu possible l'existence du style C\+\+ moderne.  
  
 Le C\+\+ moderne met en avant les aspects suivants :  
  
-   Portée basée sur la pile au lieu d'une portée globale statique ou de tas.  
  
-   Inférence de type automatique au lieu de noms de types explicites.  
  
-   Pointeurs intelligents au lieu de pointeurs bruts.  
  
-   Types `std::string` et `std::wstring` \(consultez [\<string\>](../standard-library/string.md)\) au lieu des tableaux bruts `char[]`.  
  
-   Conteneurs STL \([Standard Template Library](../standard-library/cpp-standard-library-header-files.md)\) tels que `vector`, `list` et `map`, plutôt que des tableaux bruts ou des conteneurs personnalisés.  Voir [\<vector\>](../standard-library/vector.md), [\<list\>](../standard-library/list.md) et [\< map \>](../standard-library/map.md).  
  
-   [Algorithmes STL](../standard-library/algorithm.md) plutôt que des algorithmes codés manuellement.  
  
-   Exceptions, pour signaler et gérer les conditions d'erreur.  
  
-   Communication entre threads sans verrou utilisant STL `std::atomic<>` \(consultez [\<atomic\>](../standard-library/atomic.md)\) au lieu d'autres mécanismes de communication entre threads.  
  
-   [Fonctions lambda](../cpp/lambda-expressions-in-cpp.md) inline au lieu de petites fonctions implémentées séparément.  
  
-   Boucles for basées sur une plage pour l'écriture de boucles plus fiables, utilisables avec des tableaux, des conteneurs STL et des collections [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] sous la forme `for ( for-range-declaration : expression )`.  Fait partie de la prise en charge du langage principal.  Pour plus d'informations, voir [Basé sur une plage, instruction \(C\+\+\)](../cpp/range-based-for-statement-cpp.md).  
  
 Le langage C\+\+ lui\-même a également évolué.  Comparez les extraits de code suivants.  Cet extrait montre comment les choses se passaient en C\+\+ :  
  
```cpp  
  
// circle and shape are user-defined types  
circle* p = new circle( 42 );   
vector<shape*> v = load_shapes();  
  
for( vector<circle*>::iterator i = v.begin(); i != v.end(); ++i ) {  
    if( *i && **i == *p )  
        cout << **i << “ is a match\n”;  
}  
  
for( vector<circle*>::iterator i = v.begin();  
        i != v.end(); ++i ) {  
    delete *i; // not exception safe  
}  
  
delete p;  
  
```  
  
 Voici comment la même opération est accomplie en C\+\+ moderne :  
  
```cpp  
  
#include <memory>  
#include <vector>  
// ...  
// circle and shape are user-defined types  
auto p = make_shared<circle>( 42 );  
vector<shared_ptr<shape>> v = load_shapes();  
  
for_each( begin(v), end(v), [&](const shared_ptr<shape>& s) {  
    if( s && *s == *p )  
        cout << *s << " is a match\n";  
} );  
  
```  
  
 En C\+\+ moderne, il est inutile d'utiliser new\/delete ou une gestion des exceptions explicite car vous pouvez utiliser des pointeurs intelligents à la place.  Lorsque vous utilisez la déduction de type `auto` et la [fonction lambda](../cpp/lambda-expressions-in-cpp.md), vous pouvez écrire le code plus rapidement, le renforcer et mieux le comprendre.  Et `for_each` est plus clair, plus facile à utiliser et moins sujet aux erreurs inattendues qu'une boucle `for`.  Vous pouvez utiliser le code réutilisable avec un minimum de lignes de code pour écrire votre application.  Et vous pouvez rendre ce code sécurisé du point de vue des exceptions et de la mémoire, et n'avoir aucune allocation\/désallocation ou code d'erreur à traiter.  
  
 Le C\+\+ moderne incorpore deux genres de polymorphisme : au moment de la compilation, via des modèles, et au moment de l'exécution, via l'héritage et la virtualisation.  Vous pouvez combiner ces deux genres de polymorphisme pour obtenir un effet remarquable.  Le modèle STL `shared_ptr` utilise des méthodes virtuelles internes pour accomplir son effacement de type apparemment sans effort.  Mais n'abusez pas de la virtualisation pour le polymorphisme lorsqu'un modèle est plus approprié.  Les modèles peuvent être très puissants.  
  
 Si vous accédez à C\+\+ depuis un autre langage, en particulier un langage managé dans lequel la plupart des types sont des types référence et très peu sont des types valeur, sachez que les classes C\+\+ sont des types valeur par défaut.  Mais vous pouvez les spécifier comme types référence pour activer le comportement polymorphe qui prend en charge la programmation orientée objet.  Une perspective utile : les types valeur concernent davantage la mémoire et le contrôle de disposition, alors que les types référence concernent davantage les classes de base et les fonctions virtuelles pour la prise en charge du polymorphisme.  Par défaut, les types valeur sont copiables. Ils ont chacun un constructeur de copie et un opérateur d'assignation de copie.  Lorsque vous spécifiez un type référence, rendez la classe impossible à copier \(désactivez le constructeur de copie et copiez l'opérateur d'affectation\) et utilisez un destructeur virtuel, ce qui assure la prise en charge du polymorphisme.  Les types valeur concernent également le contenu qui, en cas de copie, vous donne deux valeurs distinctes que vous pouvez modifier séparément.  Mais les types référence concernent l'identité \(quel que soit le type d'objet\) et, pour cette raison, ils sont parfois appelés types polymorphes.  
  
 C\+\+ connaît une renaissance car la puissance est à nouveau reine.  Les langages comme Java et C\# sont suffisants lorsque la productivité du programmeur est importante, mais ils montrent leurs limites lorsque la puissance et les performances sont primordiales.  Pour obtenir des performances et une puissance élevées, surtout sur les appareils qui ont du matériel informatique limité, rien ne surpasse le C\+\+ moderne.  
  
 Non seulement le langage est moderne, mais les outils de développement le sont également.  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] rend toutes les parties du cycle de développement robustes et efficaces.  Il inclut des outils de gestion du cycle de vie des applications \(Application Lifecycle Management\), des améliorations de l'IDE comme IntelliSense, des mécanismes pratiques pour les outils comme XAML, ainsi que des outils de génération, de débogage et ainsi de suite.  
  
 Les articles de cette partie de la documentation fournissent des recommandations de haut niveau et des meilleures pratiques en ce qui concerne les fonctionnalités et les techniques les plus importantes pour l'écriture de programmes C\+\+ modernes.  
  
-   [Prise en charge des fonctionnalités C\+\+11\/14\/17](../cpp/support-for-cpp11-14-17-features-modern-cpp.md)  
  
-   [Système de type C\+\+](../cpp/cpp-type-system-modern-cpp.md)  
  
-   [Constructeurs d'initialisation uniforme et de délégation](../cpp/uniform-initialization-and-delegating-constructors.md)  
  
-   [Gestion de la durée de vie et des ressources de l'objet](../cpp/object-lifetime-and-resource-management-modern-cpp.md)  
  
-   [Ressources propres objets \(RAII\)](../cpp/objects-own-resources-raii.md)  
  
-   [Pointeurs intelligents](../cpp/smart-pointers-modern-cpp.md)  
  
-   [Pimpl pour l'encapsulation au moment de la compilation](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md)  
  
-   [Conteneurs](../cpp/containers-modern-cpp.md)  
  
-   [Algorithmes](../cpp/algorithms-modern-cpp.md)  
  
-   [Mise en forme des chaînes et E\/S](../cpp/string-and-i-o-formatting-modern-cpp.md)  
  
-   [Gestion des erreurs et des exceptions](../cpp/errors-and-exception-handling-modern-cpp.md)  
  
-   [Portabilité aux limites ABI](../cpp/portability-at-abi-boundaries-modern-cpp.md)  
  
 Pour plus d'informations, voir l'article StackOverflow [Quels idiomes C\+\+ sont déconseillés dans C\+\+11 ?](http://go.microsoft.com/fwlink/?LinkId=402836)  
  
## Voir aussi  
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Expressions lambda](../cpp/lambda-expressions-in-cpp.md)   
 [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md)