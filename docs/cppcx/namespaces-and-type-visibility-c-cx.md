---
title: "Visibilit&#233; des espaces de noms et des types (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cbc01a3a-3b69-4ded-9c42-ecbf0fd0a00e
caps.latest.revision: 13
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 13
---
# Visibilit&#233; des espaces de noms et des types (C++/CX)
Un espace de noms est une construction C\+\+ standard qui sert à grouper les types qui ont des fonctionnalités associées et à empêcher les collisions de noms dans les bibliothèques. Le système de type [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] requiert que tous les types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] publics, y compris ceux de votre propre code, soient déclarés dans un espace de noms, dans la portée espace de noms. Les types publics déclarés au niveau de la portée globale ou imbriqués au sein d'une autre classe génèrent une erreur de compilation.  
  
 Un fichier .winmd doit avoir le même nom que l'espace de noms racine. Par exemple, une classe nommée A.B.C.MyClass peut être instanciée uniquement si elle est définie dans un fichier de métadonnées nommé A.winmd, A.B.winmd ou A.B.C.winmd. Il n'est pas requis que le nom de l'exécutable corresponde au nom du fichier .winmd.  
  
## Visibilité du type  
 Dans un espace de noms, les types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] \(à la différence des types C\+\+ standard\) ont soit une accessibilité privée soit publique. Par défaut, l'accessibilité est privée. Seul un type public visible aux métadonnées est utilisable à partir d'applications et de composants qui peuvent être écrits dans d'autres langages que C\+\+. En général, les règles pour les types visibles sont plus restrictives que les règles pour les types non visibles car les types visibles ne peuvent pas exposer des concepts spécifiques C\+\+ qui ne sont pas pris en charge dans les langages .NET ou JavaScript.  
  
> [!NOTE]
>  Les métadonnées sont utilisées uniquement au moment de l'exécution par les langages.NET et JavaScript. Lorsque l'application ou le composant C\+\+ communique avec une autre application ou un autre composant C\+\+ \(comprenant les composants Windows qui sont tous écrits en C\+\+\), aucune consommation d'exécution des métadonnées n'est requise.  
  
## Accessibilité membre et visibilité  
 Dans une classe ref, une interface ou un délégué privé, aucun membre n'est émis vers des métadonnées, même s'ils ont une accessibilité publique. Dans les classes ref publiques, vous pouvez contrôler la visibilité des membres dans les métadonnées indépendamment de leur accessibilité dans votre code source. Comme dans le langage C\+\+ standard, appliquez le principe de privilège minimum ; ne rendez pas les membres visibles dans les métadonnées sauf nécessité absolue.  
  
 Utilisez les modificateurs d'accès suivants pour contrôler la visibilité des métadonnées et l'accessibilité du code source.  
  
||||  
|-|-|-|  
|Modificateur|Signification|Émis vers des métadonnées ?|  
|private|Accessibilité par défaut. Même signification que dans le langage C\+\+ standard.|Non|  
|protected|Même signification qu'en C\+\+ standard, à la fois dans l'application ou le composant et dans les métadonnées.|Oui|  
|public|Même signification que dans le langage C\+\+ standard.|Oui|  
|`public protected` ou `protected public`|Accessibilité protégée dans les métadonnées, publique dans l'application ou le composant.|Oui|  
|`protected private` ou `private protected`|Non visible dans les métadonnées ; accessibilité protégée dans l'application ou le composant.||  
|`internal` ou `private public`|Le membre est public dans l'application ou le composant, mais n'est pas visible dans les métadonnées.|Non|  
  
## Espaces de noms [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]  
 L'API Windows se compose de types qui sont déclarés dans les espaces de noms Windows::\*. Ces espaces de noms sont réservés à windows et aucun type ne peut y être ajouté. Dans l'**Explorateur d'objets**, vous pouvez consulter ces espaces de noms dans le fichier windows.winmd. Pour obtenir la documentation relative à ces espaces de noms, consultez [Informations de référence sur les API Windows des applications Windows Runtime](http://msdn.microsoft.com/library/windows/apps/br211377).  
  
## Espaces de noms [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]  
 Les [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) définissent certains types dans ces espaces de noms dans le cadre de la projection du système de type [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)].  
  
|||  
|-|-|  
|**Espace de noms**|**Description**|  
|default|Contient les types numérique et char16 intégrés. Ces types sont dans la portée dans chaque espace de noms et une instruction `using` n'est jamais requise.|  
|Plateforme|Contient les types essentiellement publics qui correspondent aux types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], par exemple `Array<T>`, `String`, `Guid` et `Boolean`. Inclut également les types d'assistance spécialisés tels que `Platform::Agile<T>` et `Platform::Box<T>`.|  
|Platform::Collections|Contient les classes de collection concrètes qui implémentent les interfaces de collection [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], `IVector`, etc. de `IMap`. Ces types ne sont pas définis dans platform.winmd mais dans le fichier d'en\-tête collection.h.|  
|Platform::Details|Contient les types qui sont utilisés par le compilateur et ne sont pas destinés à la consommation publique.|  
  
## Voir aussi  
 [Système de type \(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)