---
title: "Conformité du langage Visual C++ | Microsoft Docs"
ms.custom: 
ms.date: 3/1/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 475da6e9-0d78-4b4e-bd23-f41c406c4efe
caps.latest.revision: 11
author: corob-msft
ms.author: corob
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
translationtype: Human Translation
ms.sourcegitcommit: 705a5fd040b3cba1d3e8be1ac9e2a22ef1f98eb9
ms.openlocfilehash: 8e21a77e42a90571c73ff0f207f5d799ff722bd3
ms.lasthandoff: 04/05/2017

---
# <a name="visual-c-language-conformance"></a>Conformité du langage Visual C++ 
Cette rubrique récapitule la conformité aux normes de langage ISO C++03, C++11, C++14 et C++17 (ébauche) des fonctionnalités du compilateur et des fonctionnalités de la bibliothèque standard (STL) pour Visual C++ dans Visual Studio 2017 et versions antérieures. À chaque nom de fonctionnalité du compilateur et de la bibliothèque STL correspond un lien vers le document de proposition de norme ISO C++ qui décrit la fonctionnalité en question (sous réserve de disponibilité de ce document au moment de la publication). La colonne Prise en charge indique la première version de Visual Studio à prendre en charge la fonctionnalité.  
  
Pour plus d’informations sur les améliorations de la conformité et les autres changements dans Visual Studio 2017, consultez [Améliorations de la conformité de C++ dans Visual Studio 2017](cpp-conformance-improvements-2017.md) et [Nouveautés de Visual C++ dans Visual Studio 2017](what-s-new-for-visual-cpp-in-visual-studio.md). Pour passer en revue les changements de conformité dans les versions antérieures, consultez [Historique des modifications de Visual C++](porting/visual-cpp-change-history-2003-2015.md) et [Nouveautés de Visual C++ entre 2003 et 2015](porting/visual-cpp-what-s-new-2003-through-2015.md). Pour connaître l’actualité de l’équipe C++, visitez le [blog de l’équipe Visual C++](http://blogs.msdn.microsoft.com/vcblog/).  

 > [!NOTE]
 > Aucune modification importante n’a été apportée au niveau des binaires entre Visual Studio 2015 et Visual Studio 2017.
  
## <a name="compiler-features"></a>Fonctionnalités du compilateur  
  
|Domaine de fonctionnalités| |  
|----|---|  
|__Fonctionnalités du langage principal C++03/11__|__Prise en charge__|
|&nbsp;&nbsp;Tout le reste|VS 2015 <sup>[1](#note_1)</sup>|
|&nbsp;&nbsp;Recherche de noms en deux phases|Non|
|&nbsp;&nbsp;[N2634 SFINAE sur les expressions](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2634.html)|Partielle <sup>[2](#note_2)</sup>|
|&nbsp;&nbsp;[N1653 Préprocesseur C99](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1653.htm)|Partielle <sup>[3](#note_3)</sup>|
|&nbsp;&nbsp;[N1988 Types entiers étendus](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1988.pdf)|N/A <sup>[4](#note_4)</sup>|
|__Fonctionnalités du langage principal C++14__|__Prise en charge__|
|&nbsp;&nbsp;[N3664 Prévention/fusion des allocations](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3664.html)|N/A <sup><sup>[5](#note_5)</sup></sup>|
|&nbsp;&nbsp;[N3323 Formulation optimisée pour les conversions contextuelles](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3323.pdf)|VS 2013|
|&nbsp;&nbsp;[N3472 Littéraux binaires](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3472.pdf)|VS 2015|
|&nbsp;&nbsp;[N3638 Types de retour auto et decltype(auto)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3638.html)|VS 2015|
|&nbsp;&nbsp;[N3648 init-captures](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3648.html)|VS 2015|
|&nbsp;&nbsp;[N3649 Expressions lambda génériques](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3649.html)|VS 2015|
|&nbsp;&nbsp;[N3651 Modèles de variables](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3651.pdf)|VS 2015.2|
|&nbsp;&nbsp;[N3652 Fonctions constexpr étendues](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html)|VS 2017|
|&nbsp;&nbsp;[N3653 NSDMI pour agrégats](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3653.html)|VS 2017|
|&nbsp;&nbsp;[N3760 Attribut [[deprecated]]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3760.html)|VS 2015|
|&nbsp;&nbsp;[N3778 Désallocation dimensionnée](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html)|VS 2015|
|&nbsp;&nbsp;[N3781 Séparateurs de chiffres](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3781.pdf)|VS 2015|
|__C++17 Fonctionnalités du langage principal C++17__|__Prise en charge__|
|&nbsp;&nbsp;[N3922 Nouvelles règles pour auto avec braced-init-lists](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)|VS 2015|
|&nbsp;&nbsp;[N3928 static_assert court](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf)|VS 2017 [*](#note_star)|
|&nbsp;&nbsp;[N4051 typename dans les paramètres template template](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)|VS 2015|
|&nbsp;&nbsp;[N4086 Suppression des trigraphes](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)|VS 2010|
|&nbsp;&nbsp;[N4230 Définitions d’espaces de noms imbriqués](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4230.html)|VS 2015.3 [*](#note_star)|
|&nbsp;&nbsp;[N4261 Correction des conversions de qualifications](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4261.html)|Non|
|&nbsp;&nbsp;[N4266 Attributs pour espaces de noms et énumérateurs](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)|VS 2015|
|&nbsp;&nbsp;[N4267 Littéraux de caractère u8](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)|VS 2015|
|&nbsp;&nbsp;[N4268 Autorisation de plusieurs arguments de modèle sans type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4268.html)|Non|
|&nbsp;&nbsp;[N4295 Expressions fold](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4295.html)|Non|
|&nbsp;&nbsp;[P0036R0 Suppression de certaines réductions unaires vides](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0036r0.pdf)|Non|
|&nbsp;&nbsp;[P0001R1 Suppression du mot clé register](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html)|VS 2017.x [*](#note_star)|
|&nbsp;&nbsp;[P0002R1 Suppression de l’opérateur ++ pour bool](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html)|Non|
|&nbsp;&nbsp;[P0012R1 Ajout de noexcept au système de type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0012r1.html)|Non|
|&nbsp;&nbsp;[P0017R1 Initialisation d’agrégats étendue](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html)|Non|
|&nbsp;&nbsp;[P0018R3 Capture de *this par valeur](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html)|VS 2017.x [*](#note_star)|
|&nbsp;&nbsp;[P0061R1 __has_include](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0061r1.html)|Non|
|&nbsp;&nbsp;[P0136R1 Reformulation de l’héritage des constructeurs](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html)|Non|
|&nbsp;&nbsp;[P0138R2 direct-list-init des énumérations fixes à partir d’entiers](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf)|VS 2017.x [*](#note_star)|
|&nbsp;&nbsp;[P0170R1 Expressions lambda de constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0170r1.pdf)|Non|
|&nbsp;&nbsp;[P0184R0 Boucles For basées sur une plage généralisées](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html)|VS 2017|
|&nbsp;&nbsp;[P0188R1 Attribut [[fallthrough]]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r1.pdf)|VS 2017 [*](#note_star)|
|&nbsp;&nbsp;[P0189R1 Attribut [[nodiscard]]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0189r1.pdf)|Non|
|&nbsp;&nbsp;[P0212R1 Attribut [[maybe_unused]]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0212r1.pdf)|VS 2017.x [*](#note_star)|
|&nbsp;&nbsp;[P0245R1 Littéraux hexadécimaux à virgule flottante](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0245r1.html)|Non|
|&nbsp;&nbsp;[P0028R4 Utilisation d’espaces de noms d’attribut sans répétition](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0028r4.html)|Non|
|&nbsp;&nbsp;[P0035R4 Allocation de mémoire dynamique à alignement accru](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0035r4.html)|Non|
|&nbsp;&nbsp;[P0091R3 Déduction d’arguments de modèle pour les modèles de classe](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)|Non|
|&nbsp;&nbsp;[P0127R2 Déclaration de paramètres de modèle sans type avec auto](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)|Non|
|&nbsp;&nbsp;[P0135R1 Élision de copie garantie](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0135r1.html)|Non|
|&nbsp;&nbsp;[P0145R3 Affinement de l’ordre d’évaluation des expressions](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0145r3.pdf)|Non|
|&nbsp;&nbsp;[P0217R3 Liaisons structurées](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0217r3.html)|Non|
|&nbsp;&nbsp;[P0283R2 Écartement d’attributs non reconnus](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0283r2.html)|Non|
|&nbsp;&nbsp;[P0292R2 Instructions if constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0292r2.html)|Non|
|&nbsp;&nbsp;[P0305R1 Instructions de sélection avec des initialiseurs](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0305r1.html)|Non|
|&nbsp;&nbsp;[P0386R2 Variables inline](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0386r2.pdf)|Non|
|&nbsp;&nbsp;[P0522R0 Mise en correspondance de paramètres template template avec des arguments compatibles](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0522r0.html)|Non|
|&nbsp;&nbsp;[P0003R5 Suppression des spécifications d’exceptions dynamiques](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|Non|
|&nbsp;&nbsp;[P0195R2 Expansions de pack dans les déclarations using](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0195r2.html)|Non|

## <a name="standard-library--stl-features"></a>Fonctionnalités STL/de bibliothèque standard

|Domaine de fonctionnalités| |
|---|---|
|__Fonctionnalités de bibliothèque standard C++17__|__Prise en charge__|
|&nbsp;&nbsp;P0433R2Guides de déduction pour la bibliothèque STL|Non|
|&nbsp;&nbsp;P0607R0 Variables inline pour la bibliothèque STL (options A et B2)|Non|
|&nbsp;&nbsp;[P0258R2 has_unique_object_representations](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0258r2.html)|Non|
|&nbsp;&nbsp;[P0426R1 constexpr pour char_traits](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html)|Non|
|&nbsp;&nbsp;P0604R0 Remplacement de is\_callable/result\_of par is\_invocable/invoke\_result (options A et B)|Non|
|&nbsp;&nbsp;P0156R2 Changement de nom de l’élément variadique lock\_guard en scoped\_lock|Non|
|&nbsp;&nbsp;P0558R1 Résolution des incohérences des classes de base nommées atomic<T>|Non|
|&nbsp;&nbsp;P0298R3 std::byte|Non|
|&nbsp;&nbsp;[P0063R3 Bibliothèque standard C11](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0063r3.html)|Non|
|&nbsp;&nbsp;[P0030R1 hypot(x, y, z)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf)|Non|
|&nbsp;&nbsp;[P0435R1 Remaniant de common_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0435r1.pdf)<br />&nbsp;&nbsp;P0548R1 Adaptation de common\_type et de duration|Non|
|&nbsp;&nbsp;[P0513R0 Empoisonnement du hachage](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0513r0.pdf)<br />&nbsp;&nbsp;P0599R1 Hash noexcept|Non|
|&nbsp;&nbsp;[P0033R1 Reformulation d’enable_shared_from_this](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html)|Non|
|&nbsp;&nbsp;[P0220R1 Spécification Library Fundamentals V1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html)|Partielle <sup>[6](#note_6)</sup>|
|&nbsp;&nbsp;[P0414R2 shared_ptr\<T[]>, shared_ptr\<T[N]>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html)<br />&nbsp;&nbsp;[P0497R0 Résolution de shared_ptr pour les tableaux](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html)|Non|
|&nbsp;&nbsp;[P0084R2 Type de retour emplace](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0084r2.pdf)|Non|
|&nbsp;&nbsp;[P0083R3 Transfert de mappages et d’ensembles](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf)<br />&nbsp;&nbsp;[P0508R0 Clarification d’insert_return_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html)|Non|
|&nbsp;&nbsp;[P0031R0 constexpr pour \<array> (de nouveau) et \<iterator>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0031r0.html)|Non|
|&nbsp;&nbsp;[P0505R0 constexpr pour \<chrono> (de nouveau)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0505r0.html)|Non|
|&nbsp;&nbsp;[P0005R4 not_fn()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html)<br />&nbsp;&nbsp;[P0358R1 Correctifs pour not_fn()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html)|Non|
|&nbsp;&nbsp;[P0295R0 gcd(), lcm()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0295r0.pdf)|Non|
|&nbsp;&nbsp;[P0154R1 hardware_destructive_interference_size, etc.](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0154r1.html)|Non|
|&nbsp;&nbsp;[P0067R5 Conversions de chaîne élémentaires](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0067r5.html)|Non|
|&nbsp;&nbsp;[N4562 Notions de base des bibliothèques : Boyer-Moore search()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#func.searchers.boyer_moore)<br/>&nbsp;&nbsp;[P0253R1 Résolution des types de retour de la fonction de recherche](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0253r1.pdf)|Non|
|&nbsp;&nbsp;P0618R0 Dépréciation de \<codecvt>|Non|
|&nbsp;&nbsp;[P0521R0 Dépréciation de shared_ptr::unique()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0521r0.html)|Non|
|&nbsp;&nbsp;[P0174R2 Dépréciation de composants de bibliothèque rudimentaires](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html)|Non|
|&nbsp;&nbsp;[P0003R5 Suppression des spécifications d’exceptions dynamiques](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|Non|
|&nbsp;&nbsp;[P0302R1 Suppression de la prise en charge d’un allocateur dans std::function](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html)|Non|
|&nbsp;&nbsp;[P0040R3 Extension des outils de gestion de mémoire](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0040r3.html)|Non|
|&nbsp;&nbsp;[N4562 Notions de base des bibliothèques : \<memory_resource>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#memory.resource.synop)<br />&nbsp;&nbsp;[P0337R0 Suppression de l’affectation polymorphic_allocator](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0337r0.html)|Non|
|&nbsp;&nbsp;[P0024R2 Algorithmes parallèles](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html)<br />&nbsp;&nbsp;[P0336R1 Renommage des stratégies d’exécution parallèle](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0336r1.pdf)<br />&nbsp;&nbsp;[P0394R4 Les algorithmes parallèles doivent utiliser terminate() pour les exceptions](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0394r4.html)<br />&nbsp;&nbsp;P0452R1 Unification des algorithmes parallèles \<numeric>|Non|
|&nbsp;&nbsp;[P0226R1 Fonctions mathématiques spéciales](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0226r1.pdf)|Non|
|&nbsp;&nbsp;[P0218R1 \<système de fichiers>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html)<br />&nbsp;&nbsp;[P0219R1 Chemins relatifs du système de fichiers](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0219r1.html)<br />&nbsp;&nbsp;[P0392R0 Prise en charge de string_view dans les chemins du système de fichiers](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0392r0.pdf)<br />&nbsp;&nbsp;P0430R2 Prise en charge des systèmes de fichiers non-POSIX<br />&nbsp;&nbsp;P0492R2 Résolution des commentaires NB pour le système de fichiers|Non <sup>[7](#note_7)</sup>|
|&nbsp;&nbsp;[P0152R1 atomic::is_always_lock_free](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0152r1.html)|VS 2017.x|
|&nbsp;&nbsp;[P0403R1 UDL pour \<string_view> ("meow"sv, etc.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0403r1.html)|VS 2017.x|
|&nbsp;&nbsp;[P0418R2 Spécifications compare_exchange memory_order atomiques](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0418r2.html)|VS 2017.x|
|&nbsp;&nbsp;[P0516R0 Marquage de la copie de shared_future comme noexcept](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0516r0.html)|VS 2017.x|
|&nbsp;&nbsp;[P0517R0 Construction de future_error à partir de future_errc](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0517r0.html)|VS 2017.x|
|&nbsp;&nbsp;[N4562 Notions de base des bibliothèques : \<algorithm> sample()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#alg.random.sample)|VS 2017|
|&nbsp;&nbsp;[N4562 Notions de base des bibliothèques : \<any>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#any)|VS 2017|
|&nbsp;&nbsp;[N4562 Notions de base des bibliothèques : \<optional>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#optional)|VS 2017|
|&nbsp;&nbsp;[N4562 Notions de base des bibliothèques : \<string_view>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#string.view)|VS 2017|
|&nbsp;&nbsp;[N4562 Notions de base des bibliothèques : \<tuple> apply()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#tuple)|VS 2017|
|&nbsp;&nbsp;[P0032R3 Interface homogène pour variant/any/optional](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0032r3.pdf)|VS 2017|
|&nbsp;&nbsp;[P0077R2 is_callable, is_nothrow_callable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0077r2.html)|VS 2017|
|&nbsp;&nbsp;[P0088R3 \<variant>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0088r3.html)|VS 2017|
|&nbsp;&nbsp;[P0163R0 shared_ptr::weak_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0163r0.html)|VS 2017|
|&nbsp;&nbsp;[P0209R2 make_from_tuple()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0209r2.pdf)|VS 2017|
|&nbsp;&nbsp;[P0254R2 Intégration de string_view et std::string](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0254r2.pdf)|VS 2017|
|&nbsp;&nbsp;[P0307R2 Fonctionnalité optional>=](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0307r2.pdf)|VS 2017|
|&nbsp;&nbsp;[P0393R3 Variante supériorité/égalité](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0393r3.html)|VS 2017|
|&nbsp;&nbsp;[P0504R0 Retour sur in_place_t/in_place_type_t\<T>/in_place_index_t\<I>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0504r0.html)|VS 2017|
|&nbsp;&nbsp;[P0510R0 Rejet des variantes vides, de tableaux, de références et de types incomplets](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0510r0.html)|VS 2017|
|&nbsp;&nbsp;[P0025R1 clamp()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0025r1.html)|VS 2015.3|
|&nbsp;&nbsp;[P0185R1 is_swappable, is_nothrow_swappable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0185r1.html)|VS 2015.3|
|&nbsp;&nbsp;[P0272R1 Non-const basic_string::data()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0272r1.html)|VS 2015.3|
|&nbsp;&nbsp;[N4387 Amélioration de pair et tuple](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4387.html)|VS 2015.2|
|&nbsp;&nbsp;[N4508 shared_mutex (sans contrainte de temps)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4508.html)|VS 2015.2|
|&nbsp;&nbsp;[P0004R1 Suppression d’alias iostreams déconseillés](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0004r1.html)|VS 2015.2|
|&nbsp;&nbsp;[P0006R0 Modèles de variable pour les caractéristiques de type (is_same_v, etc.).](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0006r0.html)|VS 2015.2|
|&nbsp;&nbsp;[P0007R1 as_const()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0007r1.html)|VS 2015.2|
|&nbsp;&nbsp;[P0013R1 Caractéristiques de type des opérateurs logiques (association, etc.).](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0013r1.html)|VS 2015.2|
|&nbsp;&nbsp;[P0074R0 owner_less\<>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0074r0.html)|VS 2015.2|
|&nbsp;&nbsp;[P0092R1 \<chrono> floor(), ceil(), round(), abs()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0092r1.html)|VS 2015.2|
|&nbsp;&nbsp;[P0156R0 lock_guard variadique](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0156r0.html)|VS 2015.2|
|&nbsp;&nbsp;[N3911 void_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3911.pdf)|VS 2015|
|&nbsp;&nbsp;[N4089 Conversions sécurisées dans unique_ptr\<T[]>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4089.pdf)|VS 2015|
|&nbsp;&nbsp;[N4169 invoke()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4169.html)|VS 2015|
|&nbsp;&nbsp;[N4190 Suppression d’auto_ptr, random_shuffle() et du matériau \<functional> ancien](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4190.htm)|VS 2015|
|&nbsp;&nbsp;[N4258 Nettoyages noexcept](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4258.pdf)|VS 2015|
|&nbsp;&nbsp;[N4259 uncaught_exceptions()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4259.pdf)|VS 2015|
|&nbsp;&nbsp;[N4277 reference_wrapper copiable de manière triviale](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4277.html)|VS 2015|
|&nbsp;&nbsp;[N4279 insert_or_assign()/try_emplace() pour map/unordered_map](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4279.html)|VS 2015|
|&nbsp;&nbsp;[N4280 size(), empty(), data()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4280.pdf)|VS 2015|
|&nbsp;&nbsp;[N4366 Affectation unique_ptr contrainte de façon précise](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4366.html)|VS 2015|
|&nbsp;&nbsp;[N4389 bool_constant](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4389.html)|VS 2015|
|&nbsp;&nbsp;[N4510 Prise en charge des types incomplets dans vector/list/forward_list](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4510.html)|VS 2013|
|&nbsp;&nbsp;[N4284 Itérateurs contigus](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4284.html)|N/A|
|&nbsp;&nbsp;[P0175R1 Scénarios pour la bibliothèque C](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0175r1.html)|N/A|
|&nbsp;&nbsp;[P0180R2 Réservation d’espaces de noms pour la normalisation future](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0180r2.html)|N/A|
|&nbsp;&nbsp;[P0346R1 Ajustement de la nomenclature \<random>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0346r1.pdf)|N/A|
|&nbsp;&nbsp;[P0371R1 Utilisation déconseillée de memory_order_consume](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0371r1.html)|N/A|
|&nbsp;&nbsp;P0467R2 Obligation d’utiliser des itérateurs en avant pour les algorithmes parallèles|N/A|
|&nbsp;&nbsp;[P0502R0 Les algorithmes parallèles doivent généralement utiliser terminate() pour les exceptions](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0502r0.html)|N/A|
|&nbsp;&nbsp;[P0503R0 Correction de l’utilisation de « type littéral » dans la bibliothèque](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0503r0.html)|N/A|
|&nbsp;&nbsp;[P0509R1 Mise à jour des restrictions liées à la gestion des exceptions](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0509r1.pdf)|N/A|
|&nbsp;&nbsp;P0518R1 Copie d’éléments de construction de copie dans des algorithmes parallèles de manière triviale|N/A|
|&nbsp;&nbsp;P0523R1 Assouplissement des exigences de complexité des algorithmes parallèles (général)|N/A|
|&nbsp;&nbsp;P0574R1 Assouplissement des exigences de complexité des algorithmes parallèles (spécifique)|N/A|
|&nbsp;&nbsp;P0623R0 Correctifs apportés aux algorithmes parallèles dans C++17 (version finale)|N/A|
|__Fonctionnalités de bibliothèque standard C++14__|__Prise en charge__|
|&nbsp;&nbsp;[N3462 Utilisation de result_of compatible avec SFINAE](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3462.html)|VS 2015.2|
|&nbsp;&nbsp;[N3302 constexpr pour \<complex>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2011/n3302.html)|VS 2015|
|&nbsp;&nbsp;[N3469 constexpr pour \<chrono>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3469.html)|VS 2015|
|&nbsp;&nbsp;[N3470 constexpr pour \<array>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3470.html)|VS 2015|
|&nbsp;&nbsp;[N3471 constexpr pour \<initializer_list>, \<tuple>, \<utility>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3471.html)|VS 2015|
|&nbsp;&nbsp;[N3545 integral_constant::operator()()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3545.pdf)|VS 2015|
|&nbsp;&nbsp;[N3642 UDL pour \<chrono>, \<string> (1729ms, "meow"s, etc.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3642.pdf)|VS 2015|
|&nbsp;&nbsp;[N3644 Itérateurs « en avant » null](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3644.pdf)|VS 2015|
|&nbsp;&nbsp;[N3654 quoted()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3654.html)|VS 2015|
|&nbsp;&nbsp;[N3657 Recherche associative hétérogène](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3657.htm)|VS 2015|
|&nbsp;&nbsp;[N3658 integer_sequence](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3658.html)|VS 2015|
|&nbsp;&nbsp;[N3659 shared_mutex (avec contrainte de temps)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3659.html)|VS 2015|
|&nbsp;&nbsp;[N3668 exchange()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3668.html)|VS 2015|
|&nbsp;&nbsp;[N3669 Résolution des fonctions membres constexpr sans const](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3669.pdf)|VS 2015|
|&nbsp;&nbsp;[N3670 get\<T>()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3670.html)|VS 2015|
|&nbsp;&nbsp;[N3671 equal(), is_permutation(), mismatch() à double plage](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3671.html)|VS 2015|
|&nbsp;&nbsp;[N3778 Désallocation dimensionnée](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html)|VS 2015|
|&nbsp;&nbsp;[N3779 UDL pour \<complex> (3.14i, etc.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3779.pdf)|VS 2015|
|&nbsp;&nbsp;[N3789 constexpr pour \<functional>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3789.htm)|VS 2015|
|&nbsp;&nbsp;[N3887 tuple_element_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3887.pdf)|VS 2015|
|&nbsp;&nbsp;[N3891 Renommage de shared_mutex (avec contrainte de temps) en shared_timed_mutex](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3891.htm)|VS 2015|
|&nbsp;&nbsp;[N3346 Spécifications minimales d’éléments conteneurs](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3346.pdf)|VS 2013|
|&nbsp;&nbsp;[N3421 Foncteurs d’opérateurs transparents (less\<>, etc.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3421.htm)|VS 2013|
|&nbsp;&nbsp;[N3655 Modèles d’alias pour \<type_traits> (decay_t, etc.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3655.pdf)|VS 2013|
|&nbsp;&nbsp;[N3656 make_unique()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3656.htm)|VS 2013|
|&nbsp;&nbsp;[N3924 Utilisation déconseillée de rand()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3924.pdf)|N/A|  
  
Un groupe de documents répertoriés ensemble indique qu’une fonctionnalité a été approuvée dans la norme, puis qu’un ou plusieurs documents visant à améliorer ou à développer cette fonctionnalité ont aussi été approuvés. Ces fonctionnalités sont implémentées ensemble.  
  
### <a name="supported-values"></a>Valeurs prises en charge  
__Non__ signifie que la fonctionnalité n’est pas encore implémentée.  
__Partielle__ signifie que l’implémentation dans Visual Studio 2017 est incomplète. Pour plus d’informations, consultez la section Notes.  
__N/A__ signifie que les documents de proposition ne décrivent pas de fonctionnalités. Ces documents ont modifié le langage de la norme, mais n’ont entraîné aucun travail pour les implémenteurs. Ils sont répertoriés ici par souci d’exhaustivité.  
__VS 2010__ indique des fonctionnalités prises en charge dans Visual Studio 2010.  
__VS 2013__ indique des fonctionnalités prises en charge dans Visual Studio 2013.  
__VS 2015__ indique des fonctionnalités prises en charge dans Visual Studio 2015 RTM.  
__Visual Studio 2015.2__ et __VS 2015.3__ indiquent des fonctionnalités prises en charge dans Visual Studio 2015 Update 2 et Visual Studio 2015 Update 3, respectivement.  
__VS 2017__ indique des fonctionnalités prises en charge dans Visual Studio 2017 RTM.  
__Visual Studio 2017.x__ indique des fonctionnalités prévues pour une future mise à jour de Visual Studio 2017.  
  
### <a name="notes"></a>Notes  
<a name="note_1"></a>__1__ Ignore les spécifications d’exceptions dynamiques de C++03, qui ont été dépréciées dans C++11. Comme il n’existe aucun plan pour les implémenter, il est prévu qu’elles soient retirées d’un prochain standard C++.  
<a name="note_2"></a>__2__ La prise en charge par le compilateur de SFINAE sur les expressions est suffisante pour la bibliothèque standard à partir de Visual Studio 2015 Update 2, mais elle demeure incomplète.  
<a name="note_3"></a>__3__ La prise en charge par le compilateur des règles de préprocesseur C99 est incomplète dans Visual Studio 2017. Les macros variadiques sont prises en charge, mais le comportement du préprocesseur présente de nombreux bogues.  
<a name="note_4"></a>__4__ Cette fonctionnalité est marquée comme non applicable, car les compilateurs sont autorisés, mais pas obligatoires, pour prendre en charge les types entiers étendus.  Comme GCC et Clang, nous avons choisi ne pas les prendre en charge.  
<a name="note_5"></a>__5__ De même, cette fonctionnalité est marquée comme non applicable, car les compilateurs sont autorisés, mais pas obligatoires, pour implémenter cette optimisation.  
<a name="note_6"></a>__6__ Les fonctionnalités qui n’ont pas été terminées dans Visual Studio 2015 sont indiquées autre part dans ce tableau.  
<a name="note_7"></a>__7__ La spécification technique du système de fichiers est implémentée dans \<experimental/filesystem> et \<filesystem> pour des raisons historiques, mais vous devez corriger son implémentation pour déplacer son espace de noms. Tant que cette opération n’est pas effectuée, la fonctionnalité est marquée comme non encore implémentée.  
<a name="note_star"></a>__*__ Ces fonctionnalités sont protégées par l’option de compilateur [/std:c++latest](./build/reference/std-specify-language-standard-version.md).  
  
## <a name="see-also"></a>Voir aussi  
[Informations de référence sur le langage C++](cpp/cpp-language-reference.md)  
[Bibliothèque standard C++](standard-library/cpp-standard-library-reference.md)   
[Améliorations de la conformité de C++ dans Visual Studio 2017](cpp-conformance-improvements-2017.md)  
[Nouveautés de Visual C++ dans Visual Studio 2017](what-s-new-for-visual-cpp-in-visual-studio.md)  
[Historique des modifications de Visual C++ entre 2003 et 2015](porting/visual-cpp-change-history-2003-2015.md)  
[Nouveautés de Visual C++ entre 2003 et 2015](porting/visual-cpp-what-s-new-2003-through-2015.md)  
[Blog de l’équipe Visual C++](http://blogs.msdn.microsoft.com/vcblog/)  

