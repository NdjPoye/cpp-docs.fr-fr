---
title: "Conteneurs et objets parall&#232;les | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "objets parallèles"
  - "conteneurs parallèles"
  - "conteneurs simultanés"
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
caps.latest.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 34
---
# Conteneurs et objets parall&#232;les
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La bibliothèque de modèles parallèles (PPL) inclut plusieurs conteneurs et objets qui fournissent un accès thread-safe à leurs éléments.  
  
 Un *conteneur simultané* fournit l’accès concurrentiel pour les opérations les plus importantes. Les fonctionnalités de ces conteneurs ressemblent à celles qui sont fournies par la bibliothèque STL (Standard Template). Par exemple, le [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) ressemble à la [std::vector](vector%20Class.md) classe, à ceci près que la `concurrent_vector` classe vous permet d’ajouter des éléments en parallèle. Utilisez des conteneurs simultanés lorsque vous avez du code parallèle qui requiert à la fois en lecture et accès en écriture au même conteneur.  
  
 Un *objet simultané* partagé simultanément entre composants. Un processus qui calcule l’état d’un objet simultané en parallèle produit le même résultat qu’un autre processus qui calcule le même état de façon séquentielle. Le [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) classe est un exemple d’un type d’objet simultané. La `combinable` classe vous permet d’effectuer des calculs en parallèle, puis combine ces calculs dans un résultat final. Utilisez des objets simultanés lorsque vous utiliseriez sinon un mécanisme de synchronisation, par exemple, un mutex, pour synchroniser l’accès à une variable partagée ou une ressource.  
  
##  <a name="a-nametopa-sections"></a><a name="top"></a> Sections  
 Cette rubrique décrit les conteneurs parallèles suivants et les objets en détail.  
  
 Conteneurs simultanés :  
  
-   [Classe concurrent_vector](#vector)  
  
    -   [Différences entre concurrent_vector et Vector](#vector-differences)  
  
    -   [Opérations d’accès concurrentiel sécurisé](#vector-safety)  
  
    -   [Sécurité des exceptions](#vector-exceptions)  
  
-   [concurrent_queue (classe)](#queue)  
  
    -   [Différences entre concurrent_queue et file d’attente](#queue-differences)  
  
    -   [Opérations d’accès concurrentiel sécurisé](#queue-safety)  
  
    -   [Prise en charge de l’itérateur](#queue-iterators)  
  
-   [concurrent_unordered_map, classe](#unordered_map)  
  
    -   [Unordered_map et différences entre concurrent_unordered_map](#map-differences)  
  
    -   [Opérations d’accès concurrentiel sécurisé](#map-safety)  
  
-   [concurrent_unordered_multimap, classe](#unordered_multimap)  
  
-   [concurrent_unordered_set, classe](#unordered_set)  
  
-   [concurrent_unordered_multiset, classe](#unordered_multiset)  
  
 Objets simultanés :  
  
-   [combinable (classe)](#combinable)  
  
    -   [Méthodes et fonctionnalités](#combinable-features)  
  
    -   [Exemples](#combinable-examples)  
  
##  <a name="a-namevectora-concurrentvector-class"></a><a name="vector"></a> Classe concurrent_vector  
 Le [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) classe est une classe de conteneur de séquence qui, tout comme le [std::vector](vector%20Class.md) de classe, vous permet d’accéder aléatoirement à ses éléments. La `concurrent_vector` permet de classe concurrentiel ajouter et élément accéder aux opérations. Ajouter des opérations n’invalident pas les pointeurs ou itérateurs existants. Opérations d’accès et du parcours d’itérateur sont également accès concurrentiel.  
  
###  <a name="a-namevector-differencesa-differences-between-concurrentvector-and-vector"></a><a name="vector-differences"></a> Différences entre concurrent_vector et Vector  
 La `concurrent_vector` classe ressemble étroitement à la `vector` classe. La complexité des opérations d’accès itérateur, l’accès aux éléments et ajouter un `concurrent_vector` objet sont les mêmes que pour un `vector` objet. Les points suivants illustrent où `concurrent_vector` diffère de `vector`:  
  
-   Ajouter l’accès aux éléments, les itérateurs et les opérations de parcours d’itérateur sur une `concurrent_vector` objet sont concurrentiel.  
  
-   Vous pouvez ajouter des éléments uniquement à la fin d’une `concurrent_vector` objet. La `concurrent_vector` classe ne fournit pas la `insert` méthode.  
  
-   Un `concurrent_vector` objet n’utilise pas [la sémantique de déplacement](../../cpp/rvalue-reference-declarator-amp-amp.md) lorsque vous ajoutez à celui-ci.  
  
-   Le `concurrent_vector` ne fournit pas de classe le `erase` ou `pop_back` méthodes. Comme avec `vector`, utilisez la [Effacer](../Topic/concurrent_vector::clear%20Method.md) méthode pour supprimer tous les éléments d’un `concurrent_vector` objet.  
  
-   La `concurrent_vector` classe ne stocke pas les ses éléments de façon contiguë en mémoire. Par conséquent, vous ne pouvez pas utiliser la `concurrent_vector` classe dans toutes les méthodes que vous pouvez utiliser un tableau. Par exemple, pour une variable nommée `v` de type `concurrent_vector`, l’expression `&v[0]+2` produit un comportement non défini.  
  
-   La `concurrent_vector` classe définit les [grow_by](../Topic/concurrent_vector::grow_by%20Method.md) et [grow_to_at_least](../Topic/concurrent_vector::grow_to_at_least%20Method.md) méthodes. Ces méthodes ressemblent à la [redimensionner](../Topic/concurrent_vector::resize%20Method.md) (méthode), à ceci près qu’elles soient concurrentiel.  
  
-   Un `concurrent_vector` objet ne déplace pas ses éléments lorsque vous redimensionnez ou ajoutez. Ainsi, les pointeurs existants et les itérateurs de rester valides pendant les opérations simultanées.  
  
-   Le runtime ne définit pas une version spécialisée de `concurrent_vector` de type `bool`.  
  
###  <a name="a-namevector-safetya-concurrency-safe-operations"></a><a name="vector-safety"></a> Opérations d’accès concurrentiel sécurisé  
 Toutes les méthodes qui ajoutent à ou augmentent la taille d’un `concurrent_vector` de l’objet, ou accéder à un élément dans un `concurrent_vector` d’objets, sont concurrentiel. L’exception à cette règle est la `resize` méthode.  
  
 Le tableau suivant présente le common `concurrent_vector` méthodes et opérateurs sont concurrentiel.  
  
||||  
|-|-|-|  
|[à](../Topic/concurrent_vector::at%20Method.md)|[fin](../Topic/concurrent_vector::end%20Method.md)|[opérateur &#91 ; &#93 ;](../Topic/concurrent_vector::operatorOperator.md)|  
|[commencer](../Topic/concurrent_vector::begin%20Method.md)|[premier plan](../Topic/concurrent_vector::front%20Method.md)|[push_back](../Topic/concurrent_vector::push_back%20Method.md)|  
|[Précédent](../Topic/concurrent_vector::back%20Method.md)|[grow_by](../Topic/concurrent_vector::grow_by%20Method.md)|[rbegin](../Topic/concurrent_vector::rbegin%20Method.md)|  
|[capacité](../Topic/concurrent_vector::capacity%20Method.md)|[grow_to_at_least](../Topic/concurrent_vector::grow_to_at_least%20Method.md)|[rend)](../Topic/concurrent_vector::rend%20Method.md)|  
|[vide](../Topic/concurrent_vector::empty%20Method.md)|[max_size](../Topic/concurrent_vector::max_size%20Method.md)|[taille](../Topic/concurrent_vector::size%20Method.md)|  
  
 Les opérations que le runtime fournit pour la compatibilité avec la bibliothèque STL, par exemple, `reserve`, ne sont pas compatibles avec la concurrence. Le tableau suivant indique les méthodes et les opérateurs qui ne sont pas concurrentiel courants.  
  
|||  
|-|-|  
|[attribuer](../Topic/concurrent_vector::assign%20Method.md)|[réserve](../Topic/concurrent_vector::reserve%20Method.md)|  
|[Effacer](../Topic/concurrent_vector::clear%20Method.md)|[redimensionner](../Topic/concurrent_vector::resize%20Method.md)|  
|[opérateur =](../Topic/concurrent_vector::operator=%20Operator.md)|[shrink_to_fit](../Topic/concurrent_vector::shrink_to_fit%20Method.md)|  
  
 Les opérations qui modifient la valeur des éléments existants ne sont pas concurrentiel. Utiliser un objet de synchronisation comme un [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) objet à synchroniser la lecture simultanée et les opérations d’écriture dans le même élément de données. Pour plus d’informations sur les objets de synchronisation, consultez la page [des Structures de données de synchronisation](../../parallel/concrt/synchronization-data-structures.md).  
  
 Lorsque vous convertissez un code existant qui utilise `vector` pour utiliser `concurrent_vector`, opérations simultanées peuvent provoquer un comportement de votre application à modifier. Par exemple, considérez le programme suivant qui effectue simultanément deux tâches sur un `concurrent_vector` objet. La première tâche ajoute des éléments supplémentaires à un `concurrent_vector` objet. La deuxième tâche calcule la somme de tous les éléments dans le même objet.  
  
 [!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_1.cpp)]  
  
 Bien que le `end` méthode est concurrentiel, un appel simultané à la [push_back](../Topic/concurrent_vector::push_back%20Method.md) méthode provoque la valeur retournée par `end` pour modifier. Le nombre d’éléments parcourus par l’itérateur est indéterminé. Par conséquent, ce programme peut produire un résultat différent à chaque fois que vous l’exécutez.  
  
###  <a name="a-namevector-exceptionsa-exception-safety"></a><a name="vector-exceptions"></a> Sécurité des exceptions  
 Si une opération d’assignation ou de croissance lève une exception, l’état de la `concurrent_vector` objet devient non valide. Le comportement d’un `concurrent_vector` objet qui se trouve dans un état non valide n’est pas défini, sauf spécification contraire. Toutefois, le destructeur libère toujours la mémoire allouée par l’objet, même si l’objet est dans un état non valide.  
  
 Le type de données des éléments vectoriels, `T`, doivent respecter les conditions suivantes. Sinon, le comportement de la `concurrent_vector` classe n’est pas définie.  
  
-   Le destructeur ne doit pas lever.  
  
-   Si le constructeur de copie ou par défaut lève, le destructeur ne doit pas être déclaré à l’aide de la `virtual` (mot clé) et il doivent fonctionner correctement avec une mémoire initialisée à zéro.  
  
 [[Haut](#top)]  
  
##  <a name="a-namequeuea-concurrentqueue-class"></a><a name="queue"></a> concurrent_queue (classe)  
 Le [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) classe, comme le [std::queue](../../standard-library/queue-class.md) de classe, vous permet d’accéder à l’avant et sauvegarder des éléments. La `concurrent_queue` classe active concurrentiel enqueue et dequeue operations. La `concurrent_queue` classe fournit également un support itérateur qui n’est pas concurrentiel.  
  
###  <a name="a-namequeue-differencesa-differences-between-concurrentqueue-and-queue"></a><a name="queue-differences"></a> Différences entre concurrent_queue et file d’attente  
 La `concurrent_queue` classe ressemble étroitement à la `queue` classe. Les points suivants illustrent où `concurrent_queue` diffère de `queue`:  
  
-   File d’attente et la file d’attente des opérations sur un `concurrent_queue` objet sont concurrentiel.  
  
-   La `concurrent_queue` classe prend en charge d’itérateur qui n’est pas concurrentiel.  
  
-   Le `concurrent_queue` ne fournit pas de classe le `front` ou `pop` méthodes. La `concurrent_queue` classe remplace ces méthodes en définissant le [try_pop](../Topic/concurrent_queue::try_pop%20Method.md) méthode.  
  
-   La `concurrent_queue` classe ne fournit pas la `back` méthode. Par conséquent, vous ne peut pas faire référence à la fin de la file d’attente.  
  
-   La `concurrent_queue` classe fournit le [unsafe_size](../Topic/concurrent_queue::unsafe_size%20Method.md) méthode plutôt que la `size` (méthode). Le `unsafe_size` méthode n’est pas concurrentiel.  
  
###  <a name="a-namequeue-safetya-concurrency-safe-operations"></a><a name="queue-safety"></a> Opérations d’accès concurrentiel sécurisé  
 Toutes les méthodes à cette file d’attente ou la file d’attente à partir d’un `concurrent_queue` objet sont concurrentiel.  
  
 Le tableau suivant présente le common `concurrent_queue` méthodes et opérateurs sont concurrentiel.  
  
|||  
|-|-|  
|[vide](../Topic/concurrent_queue::empty%20Method.md)|[push](../Topic/concurrent_queue::push%20Method.md)|  
|[get_allocator](../Topic/concurrent_queue::get_allocator%20Method.md)|[try_pop](../Topic/concurrent_queue::try_pop%20Method.md)|  
  
 Bien que le `empty` méthode est concurrentiel, une opération simultanée peut provoquer la file d’attente agrandir ou réduire avant le `empty` méthode retourne.  
  
 Le tableau suivant indique les méthodes et les opérateurs qui ne sont pas concurrentiel courants.  
  
|||  
|-|-|  
|[Effacer](../Topic/concurrent_queue::clear%20Method.md)|[unsafe_end](../Topic/concurrent_queue::unsafe_end%20Method.md)|  
|[unsafe_begin](../Topic/concurrent_queue::unsafe_begin%20Method.md)|[unsafe_size](../Topic/concurrent_queue::unsafe_size%20Method.md)|  
  
###  <a name="a-namequeue-iteratorsa-iterator-support"></a><a name="queue-iterators"></a> Prise en charge de l’itérateur  
 Le `concurrent_queue` fournit des itérateurs qui ne sont pas compatibles avec la concurrence. Nous vous recommandons d’utiliser ces itérateurs uniquement pour le débogage.  
  
 Un `concurrent_queue` itérateur parcourt des éléments dans la direction vers l’avant uniquement. Le tableau suivant répertorie les opérateurs que chaque itérateur prend en charge.  
  
|Opérateur|Description|  
|--------------|-----------------|  
|[operator ++](http://msdn.microsoft.com/fr-fr/4cfdd07e-927a-42f8-aaa0-d6881687f413)|Avance jusqu'à l’élément suivant dans la file d’attente. Cet opérateur est surchargé pour fournir une sémantique incrément préalables et postérieures à l’incrémentation.|  
|[* (opérateur)](http://msdn.microsoft.com/fr-fr/a0e671fc-76e6-4fb4-b95c-ced4dd2b2017)|Récupère une référence à l’élément actuel.|  
|[operator ->](http://msdn.microsoft.com/fr-fr/41fa393d-ae1e-4a38-bb4b-19e8df709ca9)|Récupère un pointeur vers l’élément actuel.|  
  
 [[Haut](#top)]  
  
##  <a name="a-nameunorderedmapa-concurrentunorderedmap-class"></a><a name="unordered_map"></a> concurrent_unordered_map, classe  
 Le [lien HYPERTEXTE « file:///C :\\\Users\\\thompet\\\AppData\\\Local\\\Temp\\\DxEditor\\\DduePreview\\\Default\\\798d7037-df37-4310-858b-6f590bbf6ebf\\\HTM\\\html\\\a217b4ac-af2b-4d41-94eb-09a75ee28622 « concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) classe est une classe de conteneur associatifs que, tout comme le [std::unordered_map](../../standard-library/unordered-map-class.md) de classe, le contrôle une séquence de longueur variable d’éléments de type [std::pair \< clé const, Ty >](../../standard-library/pair-structure.md). Considérez une carte non ordonnée en tant que dictionnaire que vous pouvez ajouter une paire clé / valeur à ou rechercher une valeur par clé. Cette classe est utile lorsque vous avez plusieurs threads ou tâches qui doivent accéder à un conteneur partagé, insérer dans ce dernier ou mettre à jour simultanément.  
  
 L’exemple suivant montre la structure de base pour l’utilisation de `concurrent_unordered_map`. Cet exemple insère des touches de caractère dans la plage ['a', ' i']. Étant donné que l’ordre des opérations est indéterminé, la valeur finale de chaque clé est également indéterminée. Toutefois, il est possible d’effectuer des insertions en parallèle sans.  
  
 [!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_2.cpp)]  
  
 Pour obtenir un exemple qui utilise `concurrent_unordered_map` pour effectuer un mappage et réduire l’opération en parallèle, consultez [Comment : effectuer un mappage et réduire les opérations en parallèle](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).  
  
###  <a name="a-namemap-differencesa-differences-between-concurrentunorderedmap-and-unorderedmap"></a><a name="map-differences"></a> Unordered_map et différences entre concurrent_unordered_map  
 La `concurrent_unordered_map` classe ressemble étroitement à la `unordered_map` classe. Les points suivants illustrent où `concurrent_unordered_map` diffère de `unordered_map`:  
  
-   Le `erase`, `bucket`, `bucket_count`, et `bucket_size` méthodes sont nommés `unsafe_erase`, `unsafe_bucket`, `unsafe_bucket_count`, et `unsafe_bucket_size`, respectivement. Le `unsafe_` convention d’affectation de noms indique que ces méthodes ne sont pas concurrentiel. Pour plus d’informations sur la sécurité d’accès concurrentiel, consultez [concurrentiel Operations](#map-safety).  
  
-   Les opérations d’insertion n’invalident pas les pointeurs ou itérateurs existants, ni de leur évolution l’ordre des éléments qui existent déjà dans la carte. Insérer et de parcourir les opérations se déroulent simultanément.  
  
-   `concurrent_unordered_map` prend en charge transférer par itération.  
  
-   Insertion de ne pas invalider ou mettre à jour les itérateurs qui sont retournées par `equal_range`. Insertion, ajoutez les éléments inégaux à la fin de la plage. L’itérateur begin pointe vers un élément égal.  
  
 Afin d’éviter le blocage, aucune méthode de `concurrent_unordered_map` détient un verrou lorsqu’il appelle l’allocateur de mémoire, les fonctions de hachage ou un autre code défini par l’utilisateur. En outre, vous devez vous assurer que la fonction de hachage évalue toujours les clés égales à la même valeur. Les meilleures fonctions de hachage répartir uniformément les clés dans l’espace de code de hachage.  
  
###  <a name="a-namemap-safetya-concurrency-safe-operations"></a><a name="map-safety"></a> Opérations d’accès concurrentiel sécurisé  
 La `concurrent_unordered_map` classe permet les opérations d’insertion et d’accès à l’élément de concurrentiel. Les opérations d’insertion n’invalident pas les pointeurs ou itérateurs existants. Opérations d’accès et du parcours d’itérateur sont également accès concurrentiel. Le tableau suivant présente les communément utilisées `concurrent_unordered_map` méthodes et opérateurs sont concurrentiel.  
  
|||||  
|-|-|-|-|  
|[à](../Topic/concurrent_unordered_map::at%20Method.md)|`count`|`find`|[key_eq](../Topic/concurrent_unordered_map::key_eq%20Method.md)|  
|`begin`|`empty`|`get_allocator`|`max_size`|  
|`cbegin`|`end`|`hash_function`|[opérateur &#91 ; &#93 ;](../Topic/concurrent_unordered_map::operatorOperator.md)|  
|`cend`|`equal_range`|[Insérer](../Topic/concurrent_unordered_map::insert%20Method.md)|`size`|  
  
 Bien que le `count` méthode peut être appelée en toute sécurité à partir de l’exécution simultanée de threads, des threads différents peuvent recevoir des résultats différents si une nouvelle valeur est insérée simultanément dans le conteneur.  
  
 Le tableau suivant montre les méthodes couramment utilisées et les opérateurs qui ne sont pas compatibles avec la concurrence.  
  
||||  
|-|-|-|  
|`clear`|`max_load_factor`|`rehash`|  
|`load_factor`|[opérateur =](../Topic/concurrent_unordered_map::operator=%20Operator.md)|[échange](../Topic/concurrent_unordered_map::swap%20Method.md)|  
  
 Outre ces méthodes, toute méthode qui commence par `unsafe_` n’est pas aussi concurrentiel.  
  
 [[Haut](#top)]  
  
##  <a name="a-nameunorderedmultimapa-concurrentunorderedmultimap-class"></a><a name="unordered_multimap"></a> concurrent_unordered_multimap, classe  
 Le [concurrency::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) classe ressemble étroitement à la `concurrent_unordered_map` sauf qu’elle autorise les valeurs multiples mapper à la même clé. Elle diffère également de `concurrent_unordered_map` comme suit :  
  
-   Le [concurrent_unordered_multimap::insert](../Topic/concurrent_unordered_multimap::insert%20Method.md) méthode retourne un itérateur au lieu de `std::pair<iterator, bool>`.  
  
-   Le `concurrent_unordered_multimap` ne fournit pas de classe `operator[]` ni le `at` (méthode).  
  
 L’exemple suivant montre la structure de base pour l’utilisation de `concurrent_unordered_multimap`. Cet exemple insère des touches de caractère dans la plage ['a', ' i']. `concurrent_unordered_multimap` permet une clé à valeurs multiples.  
  
 [!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_3.cpp)]  
  
 [[Haut](#top)]  
  
##  <a name="a-nameunorderedseta-concurrentunorderedset-class"></a><a name="unordered_set"></a> concurrent_unordered_set, classe  
 Le [concurrency::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) classe ressemble étroitement à la `concurrent_unordered_map` sauf qu’il gère des valeurs au lieu de paires clé / valeur. Le `concurrent_unordered_set` ne fournit pas de classe `operator[]` ni le `at` (méthode).  
  
 L’exemple suivant montre la structure de base pour l’utilisation de `concurrent_unordered_set`. Cet exemple insère les valeurs de caractères dans la plage ['a', ' i']. Il est recommandé d’effectuer les insertions en parallèle.  
  
 [!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_4.cpp)]  
  
 [[Haut](#top)]  
  
##  <a name="a-nameunorderedmultiseta-concurrentunorderedmultiset-class"></a><a name="unordered_multiset"></a> concurrent_unordered_multiset, classe  
 Le [concurrency::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) classe ressemble étroitement à la `concurrent_unordered_set` sauf qu’elle autorise les valeurs en double. Elle diffère également de `concurrent_unordered_set` comme suit :  
  
-   Le [concurrent_unordered_multiset::insert](../Topic/concurrent_unordered_multiset::insert%20Method.md) méthode retourne un itérateur au lieu de `std::pair<iterator, bool>`.  
  
-   Le `concurrent_unordered_multiset` ne fournit pas de classe `operator[]` ni le `at` (méthode).  
  
 L’exemple suivant montre la structure de base pour l’utilisation de `concurrent_unordered_multiset`. Cet exemple insère les valeurs de caractères dans la plage ['a', ' i']. `concurrent_unordered_multiset` permet à une valeur à se produire plusieurs fois.  
  
 [!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_5.cpp)]  
  
 [[Haut](#top)]  
  
##  <a name="a-namecombinablea-combinable-class"></a><a name="combinable"></a> combinable (classe)  
 Le [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) classe fournit un stockage local des threads réutilisable qui vous permet d’effectuer des calculs affinés puis de fusionner ces calculs dans un résultat final. Vous pouvez considérer un objet `combinable` comme une variable de réduction.  
  
 La `combinable` classe est utile lorsque vous avez une ressource qui est partagée entre plusieurs threads ou tâches. La `combinable` classe vous aide à éliminer l’état partagé en fournissant l’accès aux ressources partagées sans verrou. Par conséquent, cette classe fournit une alternative à l’aide d’un mécanisme de synchronisation, par exemple, un mutex, pour synchroniser l’accès aux données partagées à partir de plusieurs threads.  
  
###  <a name="a-namecombinable-featuresa-methods-and-features"></a><a name="combinable-features"></a> Méthodes et fonctionnalités  
 Le tableau suivant répertorie certaines des méthodes importantes de la `combinable` classe. Pour plus d’informations sur tous les `combinable` méthodes de la classe, consultez [combinable, classe](../../parallel/concrt/reference/combinable-class.md).  
  
|Méthode|Description|  
|------------|-----------------|  
|[local](../Topic/combinable::local%20Method.md)|Récupère une référence à la variable locale qui est associée au contexte de thread actuel.|  
|[Effacer](../Topic/combinable::clear%20Method.md)|Supprime toutes les variables locales de thread à partir de la `combinable` objet.|  
|[combiner](../Topic/combinable::combine%20Method.md)<br /><br /> [combine_each](../Topic/combinable::combine_each%20Method.md)|Utilise la fonction combine fournie pour générer une valeur finale de l’ensemble de tous les calculs de thread local.|  
  
 La `combinable` classe est une classe de modèle paramétrable sur le résultat fusionné final. Si vous appelez le constructeur par défaut, le `T` type de paramètre de modèle doit avoir un constructeur par défaut et un constructeur de copie. Si le `T` type de paramètre de modèle n’a pas de constructeur par défaut, appelez la version surchargée du constructeur qui prend une fonction d’initialisation comme paramètre.  
  
 Vous pouvez stocker des données supplémentaires dans un `combinable` de l’objet après l’appel à la [combiner](../Topic/combinable::combine%20Method.md) ou [combine_each](../Topic/combinable::combine_each%20Method.md) méthodes. Vous pouvez également appeler le `combine` et `combine_each` méthodes plusieurs fois. Si aucune valeur locale dans un `combinable` l’objet de modifications, la `combine` et `combine_each` méthodes produisent le même résultat chaque fois qu’elles sont appelées.  
  
###  <a name="a-namecombinable-examplesa-examples"></a><a name="combinable-examples"></a> Exemples  
 Pour obtenir des exemples sur l’utilisation du `combinable` de classe, consultez les rubriques suivantes :  
  
-   [Comment : utiliser la classe combinable pour améliorer les performances](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
  
-   [Comment : utiliser la classe combinable pour combiner des ensembles](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
  
 [[Haut](#top)]  
  
## <a name="related-topics"></a>Rubriques connexes  
 [Comment : utiliser des conteneurs parallèles pour une efficacité accrue](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)  
 Montre comment utiliser des conteneurs parallèles pour stocker et accéder aux données en parallèle.  
  
 [Comment : utiliser la classe combinable pour améliorer les performances](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
 Montre comment utiliser la `combinable` classe pour éliminer l’état partagé et ainsi améliorer les performances.  
  
 [Comment : utiliser la classe combinable pour combiner des ensembles](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
 Montre comment utiliser un `combine` fonction pour fusionner des jeux de données locales de thread.  
  
 [Bibliothèque de modèles parallèles (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)  
 Décrit la bibliothèque PPL, qui fournit un modèle de programmation impérative qui encourage l’extensibilité et la facilité d’utilisation pour le développement d’applications simultanées.  
  
## <a name="reference"></a>Référence  
 [Classe concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)  
  
 [concurrent_queue (classe)](../../parallel/concrt/reference/concurrent-queue-class.md)  
  
 [concurrent_unordered_map, classe](../../parallel/concrt/reference/concurrent-unordered-map-class.md)  
  
 [concurrent_unordered_multimap, classe](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)  
  
 [concurrent_unordered_set, classe](../../parallel/concrt/reference/concurrent-unordered-set-class.md)  
  
 [concurrent_unordered_multiset, classe](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)  
  
 [combinable (classe)](../../parallel/concrt/reference/combinable-class.md)
