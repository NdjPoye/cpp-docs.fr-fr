---
title: "Collections (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 914da30b-aac5-4cd7-9da3-a5ac08cdd72c
caps.latest.revision: 35
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 35
---
# Collections (C++/CX)
Dans un programme [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\), vous pouvez utiliser librement les conteneurs STL \(Standard Template Library\) ou tout autre type de collection défini par l'utilisateur. Toutefois, lorsque vous passez des collections dans les deux sens à travers l'interface binaire d'application \(ABI\) [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], par exemple à un contrôle XAML ou à un client JavaScript, vous devez utiliser des types de collection [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)].  
  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] définit les interfaces pour les collections et les types associés et [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] fournit les implémentations C\+\+ concrètes dans le fichier d'en\-tête collection.h. Cette illustration montre les relations entre les types de collection :  
  
 ![Arborescence d'héritage C&#43;&#43;&#47;CX pour les types de collection](../cppcx/media/cppcxcollectionsinheritancetree.png "CPPCXCollectionsInheritanceTree")  
  
-   La [classe Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) ressemble à la [classe std::vector](../Topic/vector%20Class%201.md).  
  
-   La [classe Platform::Collections::Map](../cppcx/platform-collections-map-class.md) ressemble à la [classe std::map](../standard-library/map-class.md).  
  
-   La [classe Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md) et la[classe Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md) sont des versions en lecture seule de `Vector` et `Map`.  
  
-   Les itérateurs sont définis dans [Platform::Collections Namespace](../cppcx/platform-collections-namespace.md). Ces itérateurs répondent aux spécifications des itérateurs STL et permettent d’utiliser [std::find](http://msdn.microsoft.com/library/021e9ef9-8817-409f-92ee-cd7104867361), [std::count\_if](http://msdn.microsoft.com/library/b785887c-83cd-4099-becc-3284dee05295) et d’autres algorithmes STL sur n’importe quel type d’interface [Windows::Foundation::Collections](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.aspx) ou type concret [Platform::Collections](../cppcx/platform-collections-namespace.md). Cela signifie, par exemple, que vous pouvez itérer une collection dans un composant [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] qui est créé en C\# et lui appliquer un algorithme STL.  
  
    > [!IMPORTANT]
    >  Les itérateurs de proxy `VectorIterator` et `VectorViewIterator` utilisent les objets proxy `VectoryProxy<T>` et `ArrowProxy<T>` pour activer l'utilisation avec des conteneurs STL. Pour plus d'informations, consultez « Éléments VectorProxy » dans la suite de cet article.  
  
-   Les types de collection [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] prennent en charge les mêmes garanties de sécurité que les conteneurs STL.  
  
-   [Windows::Foundation::Collections::IObservableVector](http://msdn.microsoft.com/library/windows/apps/br226052.aspx) et [Windows::Foundation::Collections::IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) définissent des événements qui sont déclenchés quand la collection est modifiée de différentes manières. En implémentant ces interfaces, [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) et [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) prennent en charge la liaison de données avec les collections XAML. Par exemple, si vous avez un vecteur `Vector`qui est lié aux données à un `Grid`, lorsque vous ajoutez un élément à une collection, la modification est répercutée dans la grille de l'interface utilisateur.  
  
## Utilisation de Vector  
 Quand votre classe doit passer un conteneur de séquence à un autre composant [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], utilisez [Windows::Foundation::Collections:: IVector\<T\>](http://msdn.microsoft.com/library/windows/apps/br206631.aspx) comme type de paramètre ou de retour et [Platform::Collections::Vector\<T\>](../cppcx/platform-collections-vector-class.md) comme implémentation concrète. Si vous tentez d'utiliser un type `Vector` dans une valeur ou un paramètre de retour, l'erreur de compilateur C3986 est générée. Vous pouvez corriger l'erreur en remplaçant le `Vector` par un `IVector`.  
  
> [!IMPORTANT]
>  Si vous passez une séquence dans le cadre de votre propre programme, utilisez `Vector` ou `std::vector` car ils sont plus efficaces que `IVector`. Utilisez `IVector` uniquement lorsque vous passez le conteneur à travers l'ABI.  
>   
>  Le système de types Windows Runtime ne prend pas en charge le concept des tableaux en escalier et vous ne pouvez donc pas utiliser un IVector\<Platform::Array\<T\>\> comme valeur de retour ou paramètre de méthode. Pour passer un tableau en escalier ou une séquence de séquences à travers l'ABI, utilisez `IVector<IVector<T>^>`.  
  
 `Vector<T>` fournit les méthodes requises pour ajouter, supprimer les éléments et y accéder dans la collection, et il est implicitement convertible en `IVector<T>`. Vous pouvez également utiliser les algorithmes STL sur les instances de `Vector<T>`. L'exemple ci\-dessous illustre l'utilisation de base. Les fonctions [begin](../cppcx/begin-function.md) et [end](../cppcx/end-function.md) sont issues ici de l'espace `Platform::Collections` au lieu de l'espace `std`.  
  
 [!code-cpp[cx_collections#01](../snippets/cpp/VS_Snippets_Misc/cx_collections/cpp/class1.cpp#01)]  
  
 Si le code existant utilise `std::vector` et que vous souhaitez le réutiliser dans un composant [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], il suffit d'utiliser l'un des constructeurs `Vector` qui accepte un `std::vector` ou une paire d'itérateurs pour construire un `Vector` au point où vous passez la collection à travers l'ABI. L'exemple ci\-dessous indique comment utiliser le constructeur de déplacement `Vector` pour une initialisation efficace à partir d'un `std::vector`. Une fois l'opération de déplacement terminée, la variable `vec` d'origine n'est plus valide.  
  
 [!code-cpp[cx_collections#02](../snippets/cpp/VS_Snippets_Misc/cx_collections/cpp/class1.cpp#02)]  
  
 Si vous avez un vecteur de chaînes que vous devez passer à travers l'ABI à un futur point, vous devez décider s'il faut créer des chaînes initialement en tant que types `std::wstring` ou `Platform::String^`. Si vous devez effectuer un important traitement sur les chaînes, utilisez `wstring`. Sinon, créez les chaînes en tant que types `Platform::String^` et évitez ainsi d'avoir à les convertir ultérieurement. Vous devez également décider s'il faut placer ces chaînes dans `std:vector` ou `Platform::Collections::Vector` en interne. De manière générale, utilisez `std::vector` et créez ensuite `Platform::Vector` à partir de ce dernier uniquement lorsque vous passez le conteneur à travers l'ABI.  
  
## Types de valeur relatifs au vecteur  
 Tout élément à stocker dans [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) doit prendre en charge la comparaison d'égalité, implicitement ou à l'aide d'un comparateur [std::equal\_to](../standard-library/equal-to-struct.md) personnalisé que vous fournissez. Tous les types de références et tous les types scalaires prennent en charge implicitement les comparaisons d'égalité. Pour les types de valeurs non scalaires tels que [Windows::Foundation::DateTime](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx), ou pour les comparaisons personnalisées, par exemple, `objA->UniqueID == objB->UniqueID`, vous devez fournir un objet de fonction personnalisé.  
  
  
  
## Éléments VectorProxy  
 [Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md) et [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) permettent d’utiliser des boucles et des algorithmes `range for` comme [std::sort](http://msdn.microsoft.com/library/9b0a4fc1-5131-4c73-9c2e-d72211f2d0ae) avec un conteneur [IVector\<T\>](http://msdn.microsoft.com/en-us/library/windows/apps/br206631.aspx). Toutefois, les éléments `IVector` ne sont pas accessibles par l’intermédiaire du déréférencement de pointeur C\+\+. Ils sont accessibles uniquement avec les méthodes [GetAt](http://msdn.microsoft.com/library/windows/apps/br206634.aspx) et [SetAt](http://msdn.microsoft.com/library/windows/apps/br206642.aspx). Par conséquent, ces itérateurs utilisent les classes proxy `Platform::Details::VectorProxy<T>` et `Platform::Details::ArrowProxy<T>` pour fournir l'accès aux différents éléments via les opérateurs `*`, `->` et `[]`, selon les exigences de STL. À proprement parler, avec un `IVector<Person^> vec`, le type de `*begin(vec)` est `VectorProxy<Person^>`. Toutefois, l'objet proxy est presque toujours transparent pour votre code. Ces objets proxy ne sont pas documentés car ils servent uniquement à un usage interne par les itérateurs, mais il est utile de savoir comment le mécanisme fonctionne.  
  
 Lorsque vous utilisez une boucle `range for` sur les conteneurs `IVector`, utilisez `auto&&` pour permettre à la variable d'itérateur d'effectuer une liaison correcte avec les éléments `VectorProxy`. Si vous utilisez `auto` ou `auto&`, l'avertissement de compilateur C4239 est déclenché et `VectoryProxy` est mentionné dans le texte d'avertissement.  
  
 L'illustration suivante montre une boucle `range for` sur un `IVector<Person^>`. Notez que l'exécution est interrompue sur le point d'arrêt à la ligne 64. La fenêtre **Espion express** indique que la variable d'itérateur `p` est en fait un `VectorProxy<Person^>` qui a les variables membres `m_v` et `m_i`. Toutefois, lorsque vous appelez la méthode `GetType` sur cette variable, elle retourne le type identique à l'instance `Person``p2`. Le principal avantage est que, bien que `VectorProxy` et `ArrowProxy` puissent apparaître dans **Espion express**, le débogueur de certaines erreurs de compilateur, il n'est pas nécessaire en général de coder explicitement pour eux.  
  
 ![VectorProxy dans une boucle for basée sur une plage](../cppcx/media/vectorproxy-1.png "VectorProxy\_1")  
  
 Un scénario dans lequel vous devez coder autour de l'objet proxy est lorsque vous devez effectuer un `dynamic_cast` sur les éléments, par exemple lorsque vous recherchez des objets XAML d'un type particulier dans une collection d'éléments `UIElement`. Dans ce cas, vous devez commencer par caster l'élément en [Platform::Object](../cppcx/platform-object-class.md)puis effectuer le cast dynamique :  
  
```  
  
void FindButton(UIElementCollection^ col)  
{  
    // Use auto&& to avoid warning C4239  
    for (auto&& elem : col)  
    {  
        Button^ temp = dynamic_cast<Button^>(static_cast<Object^>(elem));  
        if (nullptr != temp)  
        {  
            // Use temp...  
        }  
    }  
}  
```  
  
## Utilisation de Map  
 Cet exemple montre comment insérer des éléments et les consulter dans [Platform::Collections::Map](../cppcx/platform-collections-map-class.md), puis retourner `Map` sous forme d’un type [Windows::Foundation::Collections::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) en lecture seule.  
  
 [!code-cpp[cx_collections#04](../snippets/cpp/VS_Snippets_Misc/cx_collections/cpp/class1.cpp#04)]  
  
 En général, pour les fonctionnalités de carte intégrées, préférez le type `std::map` pour des raisons de performance. Si vous devez passer le conteneur à travers l’ABI, construisez un [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) à partir de [std::map](../standard-library/map-class.md) et retournez le `Map` sous forme de [Windows::Foundation::Collections::IMap](http://msdn.microsoft.com/library/windows/apps/br226042.aspx). Si vous tentez d'utiliser un type `Map` dans une valeur ou un paramètre de retour, l'erreur de compilateur C3986 est générée. Vous pouvez corriger l'erreur en remplaçant le `Map` par un `IMap`. Dans certains cas, par exemple si vous n'effectuez pas un grand nombre de recherches ou d'insertions et que vous passez fréquemment la collection à travers l'ABI, il peut être moins coûteux d'utiliser `Platform::Collections::Map` et d'éviter ainsi le coût de conversion de `std::map`. Dans tous les cas, évitez les recherches et insertions sur un `IMap`, car c'est le moins performant des trois types. Effectuez une conversion en `IMap` uniquement au point où vous passez le conteneur à travers l'ABI.  
  
## Types de valeur relatifs au mappage  
 Les éléments contenus dans [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) sont classés. Tout élément à stocker dans `Map` doit prendre en charge la comparaison « inférieur à » avec le classement faible strict, implicitement ou à l'aide d'un comparateur personnalisé [stl::less](../standard-library/less-struct.md) que vous fournissez. Les types scalaires prennent en charge la comparaison implicitement. Pour les types de valeurs non scalaires tels que `Windows::Foundation::DateTime`, ou pour les comparaisons personnalisées, par exemple, `objA->UniqueID < objB->UniqueID`, vous devez fournir un comparateur personnalisé.  
  
## Types de collections  
 Les collections sont classées en quatre catégories : versions modifiables et versions en lecture seule des collections séquentielles et associatives. En outre, [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] améliore les collections en fournissant trois classes d'itérateur qui simplifient l'accès aux collections. Pour une brève présentation des itérateurs, consultez [Itérateurs](../standard-library/iterators.md).  
  
 Les éléments d'une collection modifiable peuvent être modifiés, mais les éléments d'une collection en lecture seule, appelée *vue*, peuvent uniquement être lus. Les éléments d'une collection [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) ou[Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md) sont accessibles à l'aide d'un itérateur ou de la [Vector::GetAt \(méthode\)](../cppcx/vector-getat-method.md) de la collection et d'un index. Les éléments d'une collection associative sont accessibles à l'aide de la [Map::Lookup \(méthode\)](../cppcx/map-lookup-method.md) de la collection et d'une clé.  
  
 [Platform::Collections::Map, classe](../cppcx/platform-collections-map-class.md)  
 Collection associative modifiable. Les éléments de mappage sont des paires clé\/valeur. La recherche d'une clé pour récupérer sa valeur associée et l'itération sur toutes les paires clé\/valeur sont toutes deux prises en charge.  
  
 `Map` et `MapView` sont basés sur un modèle de `<K, V, C = std::less<K>>` ; vous pouvez donc personnaliser le comparateur.  En outre, `Vector` et `VectorView` sont basés sur des modèles de `<T, E = std::equal_to<T>>` pour vous permettre de personnaliser le comportement de `IndexOf()`. C'est important principalement pour le `Vector` et le `VectorView` des structures de valeur. Par exemple, pour créer Vector\<Windows::Foundation::DateTime\>, vous devez fournir un comparateur personnalisé, car DateTime ne surcharge pas l'opérateur \=\=.  
  
 [Platform::Collections::MapView, classe](../cppcx/platform-collections-mapview-class.md)  
 Version en lecture seule d'un `Map`.  
  
 [Platform::Collections::Vector, classe](../cppcx/platform-collections-vector-class.md)  
 Collection de séquence modifiable.`Vector<T>` prend en charge les opérations d'accès aléatoire en temps constant et les opérations d'[ajout](../cppcx/vector-append-method.md) en temps constant amorti.  
  
 [Platform::Collections::VectorView, classe](../cppcx/platform-collections-vectorview-class.md)  
 Version en lecture seule d'un `Vector`.  
  
 [Platform::Collections::InputIterator, classe](../cppcx/platform-collections-inputiterator-class.md)  
 Itérateur STL qui satisfait aux spécifications d'un itérateur d'entrée STL.  
  
 [Platform::Collections::VectorIterator, classe](../cppcx/platform-collections-vectoriterator-class.md)  
 Itérateur STL qui répond aux spécifications d'un itérateur à accès aléatoire mutable STL.  
  
 [Platform::Collections::VectorViewIterator, classe](../cppcx/platform-collections-vectorviewiterator-class.md)  
 Itérateur STL qui répond aux spécifications d'un itérateur à accès aléatoire `const` STL.  
  
### Fonctions begin\(\) et end\(\)  
 Pour simplifier l'utilisation du STL pour traiter `Vector`, `VectorView`, `Map`, `MapView` et les objets `Windows::Foundation::Collections` arbitraires, [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] prend en charge les surcharges des fonctions non membres [begin \(fonction\)](../cppcx/begin-function.md) et [end \(fonction\)](../cppcx/end-function.md).  
  
 Le tableau ci\-dessous répertorie les itérateurs et fonctions disponibles.  
  
|Itérateurs|Fonctions|  
|----------------|---------------|  
|[Platform::Collections::VectorIterator\<T\>](../cppcx/platform-collections-vectoriterator-class.md)<br /><br /> \(Stocke en interne [Windows::Foundation::Collections : : IVector\<T\>](http://msdn.microsoft.com/library/windows/apps/br206631.aspx) et int.\)|[begin](../cppcx/begin-function.md)\/ [end](../cppcx/end-function.md)\([Windows::Foundation::Collections:: IVector\<T\>](http://msdn.microsoft.com/library/windows/apps/br206631.aspx)\)|  
|[Platform::Collections::VectorViewIterator\<T\>](../cppcx/platform-collections-vectorviewiterator-class.md)<br /><br /> \(Stocke en interne [IVectorView\<T\>](http://msdn.microsoft.com/library/windows/apps/br226058.aspx)^ et int.\)|[begin](../cppcx/begin-function.md)\/ [end](../cppcx/end-function.md) \([IVectorView\<T\>](http://msdn.microsoft.com/library/windows/apps/br226058.aspx)^\)|  
|[Platform::Collections::InputIterator\<T\>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> \(Stocke en interne [IIterator\<T\>](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ et T.\)|[begin](../cppcx/begin-function.md)\/ [end](../cppcx/end-function.md) \([IIterable\<T\>](http://msdn.microsoft.com/library/windows/apps/br226024.aspx)\)|  
|[Platform::Collections::InputIterator\<IKeyValuePair\<K, V\>^\>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> \(Stocke en interne [IIterator\<T\>](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ et T.\)|[begin](../cppcx/begin-function.md)\/ [end](../cppcx/end-function.md) \([IMap\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226042.aspx).|  
|[Platform::Collections::InputIterator\<IKeyValuePair\<K, V\>^\>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> \(Stocke en interne [IIterator\<T\>](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ et T.\)|[begin](../cppcx/begin-function.md)\/ [end](../cppcx/end-function.md) \([Windows::Foundation::Collections::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx)\)|  
  
### Événements de modification de collection  
 `Vector` et `Map` prennent en charge la liaison des données dans les collections XAML en implémentant des événements qui se produisent lorsqu'un objet de collection est changé ou réinitialisé, ou lorsque l'élément d'une collection est inséré, supprimé ou modifié. Vous pouvez écrire vos propres types qui prennent en charge la liaison de données, bien que vous ne puissiez pas hériter de `Map` ou de `Vector` car ces types sont verrouillés.  
  
 Les délégués [Windows::Foundation::Collections::VectorChangedEventHandler](http://msdn.microsoft.com/library/windows/apps/br206656.aspx) et [Windows::Foundation::Collections::MapChangedEventHandler](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) spécifient les signatures des gestionnaires d’événements pour les événements de modification de collection. La classe d’énumération publique [Windows::Foundation::Collections::CollectionChange](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx), ainsi que les classes ref  `Platform::Collection::Details::MapChangedEventArgs` et `Platform::Collections::Details::VectorChangedEventArgs` stockent les arguments d’événement pour déterminer ce qui a déclenché l’événement. Les types \*`EventArgs` sont définis dans l'espace de noms `Details` car vous n'avez pas besoin de les construire ni de les utiliser explicitement lorsque vous utilisez `Map` ou `Vector`.  
  
## Voir aussi  
 [système de type](../cppcx/type-system-c-cx.md)   
 [Built\-in Types](http://msdn.microsoft.com/fr-fr/acc196fd-09da-4882-b554-6c94685ec75f)   
 [Référence du langage Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Référence aux espaces de noms](../cppcx/namespaces-reference-c-cx.md)