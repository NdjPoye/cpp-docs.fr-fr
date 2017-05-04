---
title: "Classes et structures de r&#233;f&#233;rence (C++-CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d736b82-0bf0-48cf-bac1-cc9d110b70d1
caps.latest.revision: 42
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 42
---
# Classes et structures de r&#233;f&#233;rence (C++-CX)
[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) prend en charge les *classes ref* et les *structs ref* définis par l'utilisateur, ainsi que les *classes value* et les *structs value* définis par l'utilisateur. Ces structures de données sont des conteneurs principaux par lesquels [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] prend en charge le système de type [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. Leur contenu est émis vers des métadonnées selon certaines règles spécifiques, et cela leur permet d'être passées entre les composants [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] et les applications du [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] qui sont écrites en C\+\+ ou dans d'autres langages.  
  
 Une classe ref ou un struct ref comporte les caractéristiques essentielles suivantes :  
  
-   Elle\/il doit être déclaré\(e\) dans un espace de noms, dans la portée de l'espace de noms. En outre, au sein de cet espace de noms, elle\/il peut disposer d'un accès public ou privé. Seuls les types publics sont émis vers les métadonnées. Les définitions de classes publiques imbriquées ne sont pas autorisées, notamment les classes [enum](../cppcx/enums-c-cx.md) publiques imbriquées. Pour plus d'informations, consultez [Visibilité des espaces de noms et des types](../cppcx/namespaces-and-type-visibility-c-cx.md).  
  
-   Elle\/il peut contenir en tant que membres des éléments [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] incluant les classes ref, les classes value, les structs ref, les structs value et les structs value de type Nullable. Elle\/il peut également contenir des types scalaires tels que float64, bool, etc. Elle\/il peut également contenir des types C\+\+ standard tels que `std::vector` ou une classe personnalisée, tant qu'ils ne sont pas publics. Les constructions [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] peuvent avoir une accessibilité `public`, `protected`, `internal`, `private` ou `protected private`. Tous les membres `public` ou `protected` sont émis vers les métadonnées. Les types C\+\+ standard doivent avoir une accessibilité `private`, `internal` ou `protected private`, ce qui les empêche d'être émis vers les métadonnées.  
  
-   Elle peut implémenter une ou plusieurs *classes d'interface* ou *structures d'interface*.  
  
-   Elle peut hériter d'une classe de base, et les classes de base elles\-mêmes ont des restrictions supplémentaires. L'héritage dans les hiérarchies de classes ref publiques comporte plus de restrictions que l'héritage dans les classes ref privées.  
  
-   Il ne peut être déclaré comme générique. S'il a une accessibilité privée, il peut s'agir d'un modèle.  
  
-   Sa durée de vie est gérée par un comptage de références automatique.  
  
## Déclaration  
 Le fragment de code suivant déclare la classe ref `Person`. Notez que le type C\+\+ standard `std::map` est utilisé dans les membres privés et que l’interface [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]`IMapView` est utilisée dans l’interface publique. Notez également que « ^ » est ajouté aux déclarations de types de référence.  
  
 [!code-cpp[cx_classes#03](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#03)]  
  
## Implémentation  
 Cet exemple de code montre une implémentation de la classe ref `Person` :  
  
 [!code-cpp[cx_classes#04](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.cpp#04)]  
  
## Utilisation  
 L'exemple de code suivant montre comment le code client utilise la classe ref `Person`.  
  
 [!code-cpp[cx_classes#05](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.cpp#05)]  
  
 Vous pouvez également utiliser la sémantique de pile pour déclarer une variable de classe ref locale. Un tel objet se comporte comme une variable de pile même si la mémoire est toujours allouée dynamiquement. Une différence importante est que vous ne pouvez pas assigner une référence de suivi \(%\) à une variable qui est déclarée à l'aide de la sémantique de pile, ce qui garantit que le nombre de références est décrémenté à zéro lorsque la fonction s'arrête. Cet exemple montre un `Uri` de classe ref de base et une fonction qui l'utilise avec la sémantique de pile :  
  
 [!code-cpp[cx_classes#06](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.cpp#06)]  
  
## Gestion de la mémoire  
 Vous pouvez allouer une classe ref dans la mémoire dynamique à l'aide du mot clé `ref new`.  
  
 [!code-cpp[cx_classes#01](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#01)]  
  
 L'opérateur handle\-to\-object ^ est connu sous le nom de « chapeau » et constitue fondamentalement un pointeur intelligent C\+\+. La mémoire vers laquelle il pointe est automatiquement détruite lorsque le dernier chapeau se trouve hors de portée ou est défini explicitement dans `nullptr`.  
  
 Par définition, une classe ref comporte la sémantique de référence. Lorsque vous assignez une variable de classe ref, c'est le handle qui est copié et non l'objet lui\-même. Dans l'exemple suivant, après l'assignation, `myClass` et `myClass2` pointent toutes les deux vers le même emplacement de mémoire.  
  
 [!code-cpp[cx_classes#02](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#02)]  
  
 Quand une classe ref C\+\+\/CX est instanciée, sa mémoire est initialisée à zéro avant que son constructeur ne soit appelé ; ainsi, il n'est pas nécessaire d'initialiser à zéro les membres individuels, propriétés incluses. Si la classe C\+\+\/CX dérive d'une classe WRL \(Windows Runtime C\+\+ Library\), seule la partie de la classe C\+\+\/CX dérivée est initialisée à zéro.  
  
## Membres  
 Une classe ref peut contenir des membres de fonction `public`, `protected` et `private`. Seuls les membres `public` et `protected` sont émis vers les métadonnées. Les classes imbriquées et les classes ref sont autorisées mais ne peuvent pas être `public`. Les champs publics ne sont pas autorisés ; les données membres publiques doivent être déclarées comme des propriétés. Les membres de données internes privés ou protégés peuvent être des champs. Par défaut, dans une classe ref, l'accessibilité de tous les membres est `private`.  
  
 Un struct ref \(structure de référence\) est identique à une classe ref, sauf que ses membres ont par défaut une accessibilité `public`.  
  
 Une classe ref ou un struct ref `public` est émis vers les métadonnées, mais pour être utilisable à partir d'autres applications [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] et composants [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], elle\/il doit avoir au moins un constructeur public ou protégé. Une classe ref publique qui comporte un constructeur public doit être également déclarée comme `sealed` pour éviter toute dérivation ultérieure via l'interface binaire d'application \(ABI, Application Binary Interface\).  
  
 Les membres publics peuvent ne pas être déclarés comme const car le système de types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] ne prend pas en charge const. Vous pouvez utiliser une propriété statique pour déclarer des données membres publiques avec une valeur constante.  
  
 Lorsque vous définissez une classe ref publique ou un struct ref public, le compilateur applique les attributs nécessaires à la classe et stocke ces informations dans le fichier .winmd de l'application. Toutefois, lorsque vous définissez une classe ref déverrouillée publique, appliquez manuellement l'attribut `Windows::Foundation::Metadata::WebHostHidden` pour vous assurer que la classe n'est pas visible aux applications [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] écrites en JavaScript.  
  
 Une classe ref peut avoir des types standard C\+\+, notamment des types `const`, dans tout membre `private`, `internal` ou `protected private`.  
  
 Les classes ref publiques qui ont des paramètres de type ne sont pas autorisées. Les classes ref génériques définies par l'utilisateur ne sont pas autorisées. Une classe ref privée, interne ou protégée peut être un modèle.  
  
## Destructeurs  
 Dans [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)], l'appel de `delete` sur un destructeur public appelle le destructeur quel que soit le nombre de références de l'objet. Ce comportement vous permet de définir un destructeur qui effectue un nettoyage personnalisé des ressources autres que RAII \(Resource Acquisition Is Initialization\) de façon déterministe. Toutefois, même dans ce cas, l'objet lui\-même n'est pas supprimé de la mémoire. La mémoire de l'objet est libérée uniquement lorsque le nombre de références atteint zéro.  
  
 Si le destructeur d'une classe n'est pas public, il est uniquement appelé lorsque le nombre de références atteint zéro. Si vous appelez `delete` sur un objet qui a un destructeur privé, le compilateur génère l'avertissement C4493, qui indique que « l'expression delete est sans effet, car le destructeur de \<nom\_type\> n'a pas d'accessibilité 'public'. »  
  
 Les destructeurs de classe ref peuvent être déclarés uniquement comme suit :  
  
-   publics et virtuels \(autorisés sur les types verrouillés ou déverrouillés\/ouverts\)  
  
-   privés protégés et non virtuels \(uniquement autorisés sur les types déverrouillés\)  
  
-   privés et non virtuels \(autorisés uniquement sur les types verrouillés\)  
  
 Il ne fournit aucune autre combinaison d'accessibilité, de virtualité et de verrouillage.  Si vous ne déclarez pas explicitement un destructeur, le compilateur génère un destructeur virtuel public si la classe de base ou un membre du type comporte un destructeur public. Sinon, le compilateur génère un destructeur non virtuel privé protégé pour les types déverrouillés, ou un destructeur non virtuel privé pour les types verrouillés.  
  
 Le comportement n'est pas défini si vous tentez d'accéder aux membres d'une classe dont le destructeur a déjà été exécuté ; il provoquera très probablement l'arrêt système du programme. Appeler `delete t` sur un type qui ne comporte aucun destructeur public n'a aucun effet. Appeler `delete this` sur un type ou une classe de base qui comporte un destructeur `private` ou `protected private` connu à partir de sa hiérarchie de types n'a également aucun effet.  
  
 Lorsque vous déclarez un destructeur public, le compilateur génère le code afin que la classe ref implémente `Platform::IDisposable` et que le destructeur implémente la méthode `Dispose`.`Platform::IDisposable` est la projection [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] de `Windows::Foundation::IClosable`. N'implémentez jamais explicitement ces interfaces.  
  
## Héritage  
 Platform::Object est la classe de base universelle pour toutes les classes ref. Toutes les classes ref sont implicitement convertibles en Platform::Object et peuvent remplacer [Object::ToString](../cppcx/object-tostring-method-c-cx.md). Toutefois, le modèle d'héritage [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] n'est pas conçu comme un modèle d'héritage général. Dans C\+\+\/CX, cela signifie qu'une classe ref publique définie par l'utilisateur ne peut pas servir de classe de base.  
  
 Si vous créez un contrôle utilisateur XAML et que l'objet participe au système de propriétés de dépendance, vous pouvez utiliser `Windows::UI::Xaml::DependencyObject` comme classe de base.  
  
 Après avoir défini une classe `MyBase` déverrouillée qui hérite de `DependencyObject`, d'autres classes ref publiques ou privées de votre composant ou de votre application peuvent hériter de `MyBase`. L'héritage dans les classes ref publiques doit être effectué pour prendre en charge des substitutions de méthodes virtuelles, d'identités polymorphes et d'encapsulation.  
  
 Une classe ref de base privée n'est pas obligatoire pour dériver d'une classe non verrouillée existante. Si vous avez besoin d'une hiérarchie d'objets pour modéliser votre propre structure de programme ou pour activer la réutilisation de code, utilisez les classes ref privées ou internes, ou mieux encore, les classes C\+\+ standard. Vous pouvez exposer la fonctionnalité de la hiérarchie d'objets privée via un wrapper de classe ref verrouillée publique.  
  
 Une classe ref qui a un constructeur public ou protégé dans [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] doit être déclarée comme verrouillé. Cette restriction signifie qu'il n'y a aucun moyen pour les classes écrites dans d'autres langages tels que C\# ou Visual Basic d'hériter des types que vous déclarez dans un composant [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] écrit en [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)].  
  
 Voici les principes de base en matière d'héritage dans [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] :  
  
-   Les classes ref peuvent hériter directement au plus d'une classe ref de base, mais peuvent implémenter un nombre quelconque d'interfaces.  
  
-   Si une classe est dotée d'un constructeur public, elle doit être déclarée comme verrouillée pour empêcher une dérivation supplémentaire.  
  
-   Vous pouvez créer des classes de base déverrouillée qui ont des constructeurs privés ou internes protégés, à condition que la classe de base dérive directement ou indirectement d'une classe de base déverrouillée existante comme `Windows::UI::Xaml::DependencyObject`. L'héritage de classes ref définies par l'utilisateur dans les fichiers .winmd n'est pas pris en charge ; toutefois, une classe ref peut hériter d'une interface définie dans un autre fichier .winmd. Vous pouvez créer des classes dérivées d'une classe ref de base définie par l'utilisateur uniquement dans le même composant [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] ou la même application [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)].  
  
-   Pour les classes ref, seul l'héritage public est pris en charge.  
  
     [!code-cpp[cx_classes#08](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#08)]  
  
 L'exemple suivant montre comment exposer une classe ref publique qui dérive d'autres classes ref dans une hiérarchie d'héritage.  
  
 [!code-cpp[cx_classes#09](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#09)]  
  
## Voir aussi  
 [système de type](../cppcx/type-system-c-cx.md)   
 [Classes de valeur et structures de valeur](../cppcx/value-classes-and-structs-c-cx.md)   
 [Référence du langage Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Référence aux espaces de noms](../cppcx/namespaces-reference-c-cx.md)