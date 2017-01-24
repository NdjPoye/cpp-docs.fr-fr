---
title: "Classes et structs (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes (C++)"
  - "structures, C++ (classes)"
  - "types définis par l'utilisateur"
  - "types définis par l'utilisateur, C++ (classes)"
  - "Visual C++, classes"
ms.assetid: 516dd496-13fb-4f17-845a-e9ca45437873
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes et structs (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette section présente les classes et structs C\+\+.  Les deux constructions sont identiques en C\+\+ sauf que l'accessibilité par défaut est publique dans les structs, alors qu'elle est privée dans les classes.  
  
```  
  
```  
  
 Les classes et structs sont les constructions par lesquels vous définissez vos propres types.  Les classes et structs peuvent tous deux contenir des données membres et des fonctions membres, qui vous permettent de décrire l'état et le comportement du type.  
  
 Les rubriques suivantes sont incluses :  
  
-   [de classes](../cpp/class-cpp.md)  
  
-   [struct](../cpp/struct-cpp.md)  
  
-   [Vue d'ensemble des membres de classe](../cpp/class-member-overview.md)  
  
-   [Contrôle d'accès aux membres](../cpp/member-access-control-cpp.md)  
  
-   [Héritage](../cpp/inheritance-cpp.md)  
  
-   [Membres static](../cpp/static-members-cpp.md)  
  
-   [Conversions](../cpp/user-defined-type-conversions-cpp.md)  
  
-   [Membres de données mutables \(spécificateur mutable\)](../cpp/mutable-data-members-cpp.md)  
  
-   [Déclarations de classes imbriquées](../cpp/nested-class-declarations.md)  
  
-   [Types de classe anonymes](../cpp/anonymous-class-types.md)  
  
-   [Pointeurs vers membres](../cpp/pointers-to-members.md)  
  
-   [Pointeur this](../cpp/this-pointer.md)  
  
-   [Champs de bits C\+\+](../cpp/cpp-bit-fields.md)  
  
 Les trois types de classes sont la structure, la classe et l'union.  Ils sont déclarés à l'aide des mots clés [struct](../cpp/struct-cpp.md), [class](../cpp/class-cpp.md) et [union](../cpp/unions.md) \(consultez [Définition des types de classes](http://msdn.microsoft.com/fr-fr/e8c65425-0f3a-4dca-afc2-418c3b1e57da)\).  Le tableau suivant montre les différences entre les trois types de classes.  
  
 Pour plus d'informations sur les unions, consultez [Unions](../cpp/unions.md).  Pour plus d'informations sur les classes et les structures managées, consultez [Classes et structures](../windows/classes-and-structs-cpp-component-extensions.md).  
  
### Contrôle d'accès et contraintes de structures, de classes et d'unions  
  
|Structures|Classes|Unions|  
|----------------|-------------|------------|  
|la clé de la classe est `struct`|la clé de la classe est **class**|la clé de la classe est **union**|  
|L'accès par défaut est public|L'accès par défaut est privé|L'accès par défaut est public|  
|Aucune contrainte d'utilisation|Aucune contrainte d'utilisation|Utilisation d'un seul membre à la fois|  
  
## Voir aussi  
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)