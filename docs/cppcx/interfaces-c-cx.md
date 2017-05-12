---
title: "Interfaces (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 11034314-d54a-426d-923b-5ab7a6b9f8ce
caps.latest.revision: 20
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 20
---
# Interfaces (C++/CX)
Même si une classe ref peut hériter au plus d'une classe concrète, elle peut implémenter n'importe quel nombre de classes interface. Une classe interface \(ou struct d'interface\) lui\-même peut hériter \(ou\) nécessiter plusieurs classes d'interface, peuvent surcharger ses fonctions membres, et peut avoir des paramètres de type.  
  
## Caractéristiques  
 Une interface possède les caractéristiques suivantes :  
  
-   Une classe interface \(ou struct\) doit être déclarée dans un espace de noms et peut avoir une accessibilité publique ou privée. Seules les interfaces publiques sont émises aux métadonnées.  
  
-   Les membres d'une interface peuvent inclure des propriétés, des méthodes et des événements.  
  
-   Tous les membres d'interface sont implicitement publics et virtuels.  
  
-   Les champs et les membres statiques ne sont pas autorisés.  
  
-   Les types utilisés comme propriétés, paramètres de méthode ou valeurs de retour ne peuvent être que des types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. Cela inclut les types fondamentaux et les types de classe d'énumération.  
  
## Déclaration et utilisation  
 L'exemple suivant montre comment déclarer une interface. Notez qu'une interface peut être déclarée comme type de classe ou de structure.  
  
 [!code-cpp[cx_interfaces#01](../snippets/cpp/VS_Snippets_Misc/cx_interfaces/cpp/class1.h#01)]  
  
 Pour implémenter une interface, une classe ref ou une structure ref déclare et implémente les méthodes et les propriétés virtuelles. L'interface et la classe ref d'implémentation doivent utiliser les mêmes noms de paramètres de méthode, comme illustré dans cet exemple :  
  
 [!code-cpp[cx_interfaces#02](../snippets/cpp/VS_Snippets_Misc/cx_interfaces/cpp/class1.h#02)]  
  
## Hiérarchies d'héritage d'interface  
 Une interface peut hériter d'une ou de plusieurs interfaces. Mais contrairement à une classe ou une structure ref, une interface ne déclare pas les membres d'interface hérités. Si l’interface B hérite de l’interface A et que la classe ref C hérite de B, C doit implémenter A et B. Ceci est illustré dans l’exemple suivant.  
  
 [!code-cpp[cx_interfaces#03](../snippets/cpp/VS_Snippets_Misc/cx_interfaces/cpp/class1.h#03)]  
  
## Implémentation des propriétés et des événements d'interface  
 Comme indiqué dans l'exemple précédent, utilisez les propriétés virtuelles triviales pour implémenter les propriétés d'interface. Fournissez également des méthodes getter et setter personnalisées dans la classe d'implémentation.  Les méthodes getter et setter doivent être publiques dans une propriété d'interface.  
  
 [!code-cpp[cx_interfaces#04](../snippets/cpp/VS_Snippets_Misc/cx_interfaces/cpp/class1.h#04)]  
  
 Si une interface déclare une propriété Get uniquement ou Set uniquement, la classe d'implémentation doit alors fournir explicitement une méthode getter ou une méthode setter.  
  
 [!code-cpp[cx_interfaces#05](../snippets/cpp/VS_Snippets_Misc/cx_interfaces/cpp/class1.h#05)]  
  
 Implémentez également des méthodes d'ajout et de suppression d'événements dans la classe d'implémentation.  
  
## Implémentation d'interface explicite  
 Lorsqu'une classe ref implémente plusieurs interfaces, et ces interfaces ont des méthodes dont les noms et les signatures sont identiques au compilateur, vous pouvez utiliser la syntaxe suivante pour indiquer explicitement la méthode d'interface qu'une méthode de classe implémente.  
  
 [!code-cpp[cx_interfaces#06](../snippets/cpp/VS_Snippets_Misc/cx_interfaces/cpp/class1.h#06)]  
  
## Interfaces génériques  
 Dans [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)], le mot clé `generic` est utilisé pour représenter un type paramétré [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. Un type paramétré est émis dans les métadonnées et peut être consommé par le code écrit dans n'importe quel langage qui prend en charge les paramètres de type. Le [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] définit certaines interfaces génériques \(par exemple, [Windows::Foundation::Collections::IVector\<T\>](Windows::Foundation::Collections::IVector)\), mais il ne prend pas en charge la création d’interfaces génériques publiques définies par l’utilisateur en [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]. Toutefois, vous pouvez créer des interfaces génériques privées.  
  
 Voici comment les types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] peuvent être utilisés pour créer une interface générique :  
  
-   Une `interface class` générique définie par l'utilisateur ne peut pas émettre dans son fichier de métadonnées Windows ; par conséquent, elle ne peut pas avoir un accès public, et le code client dans d'autres fichiers .winmd ne peut pas l'implémenter. Elle peut être implémentée par les classes ref non publiques dans le même composant. Une classe ref publique peut avoir un type d'interface générique comme membre privé.  
  
     L'extrait de code suivant indique comment déclarer une `interface class` générique puis l'implémenter dans une classe ref privée et utiliser la classe ref comme membre privé dans une classe ref publique.  
  
     [!code-cpp[cx_interfaces#07](../snippets/cpp/VS_Snippets_Misc/cx_interfaces/cpp/class1.h#07)]  
  
-   Une interface générique doit respecter les règles d'interface standard qui régissent l'accessibilité, les membres, *requiert* les relations, les classes de base, etc.  
  
-   Une interface générique peut prendre un ou plusieurs paramètres de type générique précédés par `typename` ou `class`. Les paramètres sans type ne sont pas pris en charge.  
  
-   Un paramètre de type peut être de n'importe quel type [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. Autrement dit, le paramètre de type peut être un type référence, un type valeur, une classe d'interface, un délégué, un type fondamental ou une classe d'énumération publique.  
  
-   Une *interface générique fermée* est une interface qui hérite d'une interface générique et spécifie les arguments de type concret pour tous les paramètres de type. Elle peut être utilisée partout où une interface privée non générique peut être utilisée.  
  
-   Une *interface générique ouverte* est une interface qui possède un ou plusieurs paramètres de type pour lesquels aucun type concret n'est encore fourni. Elle peut être utilisée partout où un type peut être utilisé. Cela inclut l'utilisation comme argument de type d'une autre interface générique.  
  
-   Paramétrez uniquement la totalité d'une interface, et non des méthodes individuelles.  
  
-   Les paramètres de type ne peuvent pas être contraints.  
  
-   Une interface générique fermée possède un UUID généré implicitement. Un utilisateur ne peut pas spécifier un UUID.  
  
-   Dans l'interface, il est supposé que toute référence à l'interface actuelle, dans un paramètre de méthode, une valeur de retour ou une propriété, fait référence à l'instanciation actuelle. Par exemple, *IMyIntf* signifie  *IMyIntf\<T\>*.  
  
-   Lorsque le type d'un paramètre de méthode est un paramètre de type, la déclaration de ce paramètre ou de cette variable utilise le nom du paramètre de type sans pointeur, référence native ou déclarateur de handle. En d'autres termes, vous ne devez jamais écrire « T^ ».  
  
-   Les classes ref basées sur un modèle doivent être privées. Elles peuvent implémenter des interfaces génériques et passer le paramètre de modèle *T* à l’argument générique *T*. Chaque instanciation d'une classe ref basée sur un modèle est elle\-même une classe ref.  
  
## Voir aussi  
 [système de type](../cppcx/type-system-c-cx.md)   
 [Référence du langage Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Référence aux espaces de noms](../cppcx/namespaces-reference-c-cx.md)