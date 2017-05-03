---
title: "Syst&#232;me de type (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b67bee8a-b526-4872-969e-ef22724e88fe
caps.latest.revision: 28
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 28
---
# Syst&#232;me de type (C++/CX)
Avec l'architecture [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)], Visual Basic, Visual C\#, et JavaScript peuvent être utilisés pour écrire des applications et des composants qui accèdent directement à l'API Windows et interagissent avec d'autres applications et composants [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. Les applications [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] qui sont écrites en C\+\+ sont compilées en code natif qui s'exécute directement dans l'UC. Les applications [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] écrites en C\# ou Visual Basic sont compilées en langage MSIL \(Microsoft Intermediate Langage\) et exécutées en CLR \(Common Language Runtime\). Les applications [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] écrites en JavaScript sont exécutées dans un environnement d'exécution. Les composants du système d'exploitation [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] eux\-mêmes sont écrits en C\+\+ et exécutés en code natif. Tous ces composants et applications [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] communiquent directement via l'interface binaire d'application \(ABI\) [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)].  
  
 Pour activer la prise en charge du [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] dans un idiome moderne C\+\+, Microsoft a créé [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\).[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] fournit des types et implémentations de base des types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] fondamentaux qui permettent aux applications et composants C\+\+ de communiquer à travers l'ABI avec les applications écrites dans d'autres langages. Vous pouvez utiliser n'importe quel type [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] ou créer des classes, des structures, des interfaces et d'autres types définis par l'utilisateur qui peuvent être utilisés par d'autres applications et composants [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]. Une application [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] écrite dans [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] peut également utiliser les classes et structures C\+\+ normales tant qu'elles ne disposent pas d'un accès public.  
  
 Pour une discussion détaillée de la projection du langage C\+\+\/CX et de son fonctionnement réel, voir les billets de blog suivants :  
  
1.  [C\+\+\/CX Partie 0 sur \[n\] : introduction](http://blogs.msdn.com/b/vcblog/archive/2012/08/29/cxxcxpart00anintroduction.aspx)  
  
2.  [C\+\+\/CX Partie 0 sur \[n\] : introduction](http://blogs.msdn.com/b/vcblog/archive/2012/08/29/cxxcxpart00anintroduction.aspx)  
  
3.  [C\+\+\/CX Partie 2 sur \[n\] : types avec chapeau \(^\)](http://blogs.msdn.com/b/vcblog/archive/2012/09/17/cxxcxpart02typesthatwearhats.aspx)  
  
4.  [C\+\+\/CX Partie 3 sur \[n\] : en construction](http://blogs.msdn.com/b/vcblog/archive/2012/10/05/cxxcxpart03underconstruction.aspx)  
  
5.  [C\+\+\/CX Partie 4 sur \[n\] : fonctions membres static](http://blogs.msdn.com/b/vcblog/archive/2012/10/19/cxxcxpart04staticmemberfunctions.aspx)  
  
## Fichiers de métadonnées Windows \(.winmd\)  
 Lorsque vous compilez une application [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] écrite en C\+\+, le compilateur génère le fichier exécutable en code machine natif et un fichier de métadonnées Windows \(.winmd\) qui contient les descriptions des types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] publics, qui comprennent les classes, structures, énumérations, interfaces, interfaces paramétrables et délégués. Le format des métadonnées est semblable au format utilisé dans les assemblys .NET Framework.  Dans un composant C\+\+, le fichier .winmd contient uniquement des métadonnées. Le code exécutable se trouve dans un fichier distinct. C'est le cas des composants [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] inclus avec Windows. Le nom du fichier WinMD doit correspondre à l'espace de noms racine ou en être le préfixe dans le code source. \(Pour les langages .NET Framework, le fichier .winmd contient le code et les métadonnées, tout comme un assembly. NET Framework.\)  
  
 Les métadonnées du fichier .winmd représentent la surface publiée de votre code. Les types publiés sont visibles par d'autres [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)], quel que soit le langage dans lequel ces autres applications sont écrits. Par conséquent, les métadonnées ou votre code publié ne peuvent contenir que des types spécifiés par le système de type [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. Les constructions de langage propres à C\+\+, telles que les classes, tableaux, modèles ou conteneurs STL normaux, ne peuvent pas être publiées dans les métadonnées, car une application cliente Javascript ou C\# ne saura pas quoi faire avec.  
  
 La visibilité d'un type ou d'une méthode dans les métadonnées dépend des modificateurs d'accessibilité qui lui sont appliqués. Pour être visible, un type doit être déclaré dans un espace de noms et comme public. Une ref class non publique est autorisée comme type d'assistance interne dans votre code mais elle n'est pas visible dans les métadonnées. Même dans une classe ref, les membres ne sont pas tous nécessairement visibles. Le tableau suivant répertorie la relation entre les spécificateurs d'accès C\+\+ dans une classe ref publique et la visibilité des métadonnées [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] :  
  
|||  
|-|-|  
|**Publié dans les métadonnées**|**Non publié dans les métadonnées**|  
|public|private|  
|protected|internal|  
|protégé public|protégé privé|  
  
 Vous pouvez utiliser l'**Explorateur d'objets** pour afficher le contenu des fichiers .winmd. Les composants [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] inclus avec Windows se trouvent dans le fichier Windows.winmd. Le fichier default.winmd contient les types fondamentaux utilisés dans [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] et platform.winmd contient les types supplémentaires de l'espace de noms Platform. Par défaut, ces trois fichiers .winmd sont inclus dans chaque projet C\+\+ pour les applications [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)].  
  
> [!TIP]
>  Les types présents dans [Platform::Collections \(espace de noms\)](../cppcx/platform-collections-namespace.md) n'apparaissent pas dans le fichier .winmd car ils ne sont pas publics. Ce sont des implémentations propres à C\+\+ privées des interfaces définies dans `Windows::Foundation::Collections`. Une application [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] écrite en JavaScript ou C\# ne sait pas ce qu'est une [Platform::Collections::Vector, classe](../cppcx/platform-collections-vector-class.md), mais elle peut consommer `Windows::Foundation::Collections::IVector`. Les types `Platform::Collections` sont définis dans collection.h.  
  
## Système de type [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] dans [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]  
 Les sections suivantes décrivent les principales fonctionnalités du système de type [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] et comment elles sont prises en charge dans [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)].  
  
### Espaces de noms  
 Tous les types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] doivent être déclarés dans un espace de noms. L'API Windows elle\-même est organisée par espaces de noms. Un fichier .winmd doit avoir le même nom que l'espace de noms racine. Par exemple, une classe nommée A.B.C.MyClass peut être instanciée uniquement si elle est définie dans un fichier de métadonnées nommé A.winmd, A.B.winmd ou A.B.C.winmd. Il n'est pas requis que le nom de la DLL corresponde au nom du fichier .winmd.  
  
 L'API Windows elle\-même a été réinventée sous la forme d'une bibliothèque de classes correctement factorisées, organisée par espaces de noms.  Tous les composants [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] sont déclarés dans les espaces de noms Windows.\*.  
  
 Pour plus d'informations, consultez [Visibilité des espaces de noms et des types](../cppcx/namespaces-and-type-visibility-c-cx.md).  
  
### Types fondamentaux  
 Le [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] définit les types fondamentaux suivants : UInt8, Int16, UInt16, Int32, UInt32, Int64, UInt64, Single, Double, Char16, Boolean et String.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] prend en charge les types numériques fondamentaux dans son espace de noms par défaut, tels que uint16, uint32, uint64, int16, int32, int64, float32, float64 et char16. Les types Boolean et String sont également définis dans l'espace de noms Platform.  
  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] définit également uint8, équivalent à `unsigned char`, qui n'est pas pris en charge dans le [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] et ne peut pas être utilisé dans les API publiques.  
  
 Il est possible de rendre Nullable un type fondamental en l'encapsulant dans une [interface Platform::IBox](../cppcx/platform-ibox-interface.md). Pour plus d'informations, consultez [Classes de valeur et structures de valeur](../cppcx/value-classes-and-structs-c-cx.md).  
  
 Pour plus d'informations sur les types fondamentaux, consultez [Types fondamentaux](../cppcx/fundamental-types-c-cx.md).  
  
### Chaînes  
 Une chaîne [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] est une séquence immuable de caractères UNICODE 16 bits. Une chaîne [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] est projetée comme `Platform::String^`. Cette classe fournit des méthodes pour la construction, la manipulation, et la conversion des chaînes vers et à partir de `wchar_t`.  
  
 Pour plus d'informations, consultez [Chaînes](../cppcx/strings-c-cx.md).  
  
### Tableaux  
 Le [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] prend en charge les tableaux unidimensionnels de tout type. Les tableaux de tableaux ne sont pas pris en charge.  En [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)], les tableaux [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] sont projetés en tant que [Platform::Array \(classe\)](../cppcx/platform-array-class.md).  
  
 Pour plus d'informations, consultez [Array et WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)  
  
### Classes et structures de référence  
 Les classes [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] sont projetées dans [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] comme des classes ou structures ref, car elles sont copiées par référence. La gestion de mémoire pour les classes ou structures ref est traitée de façon transparente au moyen d'un décompte de références. Lorsque la dernière référence à un objet devient hors de portée, l'objet est détruit. Une classe ou structure ref peut :  
  
-   Contenir comme membres des constructeurs, méthodes, propriétés et événements. Ces membres peuvent avoir un accès public, privé, protégé ou interne.  
  
-   Contenir des définitions d'énumération, de structure ou de classe imbriquées privées.  
  
-   Hériter directement d'une classe de base et implémenter un nombre quelconque d'interfaces. Toutes les classes ref sont implicitement convertibles en [Platform::Object, classe](../cppcx/platform-object-class.md) et peuvent substituer ses méthodes virtuelles, par exemple [Object::ToString](../cppcx/object-tostring-method-c-cx.md).  
  
 Une classe de référence qui a un constructeur public doit être déclarée comme sealed, pour empêcher une dérivation supplémentaire.  
  
 Pour plus d'informations, consultez [Classes et structures de référence](../cppcx/ref-classes-and-structs-c-cx.md)  
  
### Classes de valeur et structures de valeur  
 Une classe de valeur ou une structure de valeur représente une structure de données de base et contient uniquement des champs, qui peuvent être des classes de valeur, des structures de valeur ou de type `Platform::String^`.  Les structures de valeur et les classes de valeur sont copiées par valeur.  
  
 Il est possible de rendre Nullable un struct value en l'encapsulant dans une interface IBox.  
  
 Pour plus d'informations, consultez [Classes de valeur et structures de valeur](../cppcx/value-classes-and-structs-c-cx.md).  
  
### Classes partielles  
 La fonctionnalité de classe partielle permet à une classe d'être définie sur plusieurs fichiers. Elle sert avant tout à permettre aux outils de génération de code tels que l'éditeur XAML de modifier un fichier sans toucher au fichier que vous modifiez.  
  
 Pour plus d'informations, consultez [Classes partielles](../cppcx/partial-classes-c-cx.md)  
  
### Propriétés  
 Une propriété est constituée de données membres publiques de tout type [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] et est implémentée en tant que paire de méthodes get\/set. Le code client accède à une propriété comme s'il s'agissait d'un champ public. Une propriété qui ne requiert aucun code get ou set personnalisé est appelée *propriété triviale* et peut être déclarée sans méthodes get ou set explicites.  
  
 Pour plus d'informations, consultez [Propriétés](../cppcx/properties-c-cx.md).  
  
### Collections [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] dans [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]  
 Le [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] définit un jeu d'interfaces pour les types de collection que chaque langage implémente de sa propre manière.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] fournit des implémentations dans la [Platform::Collections::Vector, classe](../cppcx/platform-collections-vector-class.md), [Platform::Collections::Map, classe](../cppcx/platform-collections-map-class.md) et d'autres types de collection concrets associés, qui sont compatibles avec leurs équivalents STL \(Standard Template Library\).  
  
 Pour plus d'informations, consultez [Collections](../cppcx/collections-c-cx.md).  
  
### Classes ref de modèle  
 Les classes ref privées et internes peuvent être basées sur un modèle et spécialisées.  
  
 Pour plus d'informations, consultez [Classes ref de modèle](../cppcx/template-ref-classes-c-cx.md).  
  
### Interfaces  
 Une interface [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] définit un ensemble de propriétés publiques, méthodes et événements qu'une classe ou structure ref doit implémenter si elle hérite de l'interface.  
  
 Pour plus d'informations, consultez [Interfaces](../cppcx/interfaces-c-cx.md).  
  
### Énumérations  
 Une classe enum dans [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] ressemble à une énumération limitée en C\+\+. Le type sous\-jacent est int32 sauf si l'attribut \[Flags\] est appliqué, auquel cas le type sous\-jacent est uint32.  
  
 Pour plus d'informations, consultez [Enums](../cppcx/enums-c-cx.md).  
  
### Délégués  
 Dans le [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], un délégué est analogue à un objet std::function en C\+\+. C'est un type spécial de classe de référence qui est utilisée pour appeler les fonctions fournies par le client qui ont des signatures compatibles.  Les délégués sont le plus souvent utilisés dans le [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] comme le type d'un événement.  
  
 Pour plus d'informations, consultez [Délégués](../cppcx/delegates-c-cx.md).  
  
### Exceptions  
 Dans C\+\+\/CX, vous pouvez intercepter les types d'exceptions personnalisés, les types [std::exception](../Topic/exception%20Class1.md) et les types [Platform::Exception](../cppcx/platform-exception-class.md).  
  
 Pour plus d'informations, consultez [Exceptions](../cppcx/exceptions-c-cx.md).  
  
### Événements  
 Un événement est un membre public d'une classe ou structure ref dont le type est un type de délégué. Un événement ne peut être appelé, c'est\-à\-dire déclenché, que par la classe propriétaire. Toutefois, le code client peut fournir ses propres fonctions, connues sous le nom de gestionnaires d'événements. Elles sont appelées lorsque la classe propriétaire déclenche l'événement.  
  
 Pour plus d'informations, consultez [Événements](../cppcx/events-c-cx.md).  
  
### Cast  
 C\+\+\/CX prend en charge les opérateurs de cast C\+\+ standard [static\_cast](../cpp/static-cast-operator.md), [dynamic\_cast](../cpp/dynamic-cast-operator.md) et [reinterpret\_cast](../cpp/reinterpret-cast-operator.md), ainsi que l'opérateur [safe\_cast](../Topic/safe_cast%20\(C++%20Component%20Extensions\).md) propre à C\+\+\/CX.  
  
 Pour plus d'informations, consultez [Effectuer un cast](../cppcx/casting-c-cx.md).  
  
### Boxing  
 Une variable convertie \(boxed\) est un type valeur encapsulé dans un type référence dans les situations où la sémantique de référence est requise.  
  
 Pour plus d'informations, consultez [Boxing](../cppcx/boxing-c-cx.md).  
  
### Attributs  
 Un attribut est une valeur de métadonnées qui peut être appliquée à un type ou membre de type [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] et peut être inspectée au moment de l'exécution.[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] définit un ensemble d'attributs communs dans l'espace de noms `Windows::Foundation::Metadata`. Les attributs définis par l'utilisateur sur les interfaces publiques ne sont pas pris en charge par [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] dans cette version.  
  
## API déconseillées  
 Décrit comment marquer les API publiques comme étant déconseillées, à l'aide du même attribut que celui utilisé par les types système [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)].  
  
 Pour plus d'informations, consultez [Déconseiller des types et des membres](../cppcx/deprecating-types-and-members-c-cx.md).  
  
## Voir aussi  
 [Référence du langage Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)