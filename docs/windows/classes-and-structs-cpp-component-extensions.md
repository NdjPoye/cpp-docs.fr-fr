---
title: "Classes and Structs  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "public"
  - "ref struct"
  - "value_CPP"
  - "ref class"
  - "value struct"
  - "ref struct_cpp"
  - "ref class_cpp"
  - "value class_cpp"
  - "value struct_cpp"
  - "value class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ref class keyword [C++]"
  - "value class keyword [C++]"
  - "value struct keyword [C++]"
  - "ref struct keyword [C++]"
ms.assetid: 5c360764-b229-49c6-9357-66213afbc372
caps.latest.revision: 32
caps.handback.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes and Structs  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Déclare une classe ou un struct dont la *durée de vie des objets* est automatiquement administrée.  Quand l'objet n'est plus accessible ou qu'il est hors de portée, Visual C\+\+ ignore automatiquement la mémoire allouée à cet objet.  
  
## Tous les runtimes  
 **Syntaxe**  
  
```  
  
          class_access ref class    name modifier :  inherit_access base_type {};  
class_access ref struct   name modifier :  inherit_access base_type {};  
class_access value class  name modifier :  inherit_access base_type {};  
class_access value struct name modifier :  inherit_access base_type {};  
  
```  
  
 **Paramètres**  
  
 *accès\_classe* \(facultatif\)  
 Accessibilité de la classe ou du struct en dehors de l'assembly.  Les valeurs possibles sont **public** et `private` \(`private` est la valeur par défaut\).  Les classes ou structs imbriqués ne peuvent pas avoir de spécificateur *accès\_classe*.  
  
 *name*  
 Nom de la classe ou du struct.  
  
 *modificateur* \(facultatif\)  
 [abstract](../windows/abstract-cpp-component-extensions.md) et [sealed](../windows/sealed-cpp-component-extensions.md) sont des modificateurs valides.  
  
 *hériter\_accès* \(facultatif\)  
 Accessibilité de `base_type`.  La seule accessibilité autorisée est `public` \(`public` est la valeur par défaut\).  
  
 *type\_base* \(facultatif\)  
 Type de base.  Toutefois, un type valeur ne peut pas agir comme un type de base.  
  
 Pour plus d'informations, consultez les descriptions propres aux langages de ce paramètre dans les sections [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] et [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)].  
  
 **Notes**  
  
 L'accessibilité des membres par défaut d'un objet déclaré avec **classe ref** ou **classe value** est `private`.  Et l'accessibilité des membres par défaut d'un objet déclaré avec **classe ref** ou **value struct** est `public`.  
  
 Quand un type référence hérite d'un autre type référence, les fonctions virtuelles dans la classe de base doivent être explicitement remplacées \(avec [override](../windows/override-cpp-component-extensions.md)\) ou masquées \(avec [new \(new slot in vtable\)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)\).  Les fonctions de classes dérivées doivent également être marquées explicitement comme `virtual`.  
  
 Pour détecter au moment de la compilation si un type est un `ref class` ou `ref struct`, ou un `value class` ou `value struct`, utilisez `__is_ref_class (``type``)`, `__is_value_class (``type``)` ou `__is_simple_value_class (``type``)`.  Pour plus d'informations, voir [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 Pour plus d'informations sur les classes et structs, consultez  
  
-   [Instanciation de classes et structs](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)  
  
-   [Sémantiques de ce pointeur dans les types valeur et référence](../misc/semantics-of-the-this-pointer-in-value-and-reference-types.md)  
  
-   [Sémantique de pile C\+\+ pour les types de référence](../dotnet/cpp-stack-semantics-for-reference-types.md)  
  
-   [Classes, structures et unions](../cpp/classes-and-structs-cpp.md)  
  
-   [public et privé sur des classes natives](../misc/how-to-declare-public-and-private-on-native-classes.md)  
  
-   [Classes implicitement abstraites](../misc/implicitly-abstract-classes.md)  
  
-   [Définir des constructeurs statiques dans une classe ou un struct](../misc/how-to-define-static-constructors-in-a-class-or-struct.md)  
  
-   [Il est possible que le constructeur de copie ne soit pas généré](../misc/copy-constructor-may-not-be-generated.md)  
  
-   [Fonctions Hide\-by\-Signature dans les types de référence](../misc/hide-by-signature-functions-in-reference-types.md)  
  
-   [Destructeurs et finaliseurs dans Visual C\+\+](../misc/destructors-and-finalizers-in-visual-cpp.md)  
  
-   [Visibilité de type et de membre](../misc/type-and-member-visibility.md)  
  
-   [Opérateurs définis par l'utilisateur](../dotnet/user-defined-operators-cpp-cli.md)  
  
-   [Conversions définies par l'utilisateur](../dotnet/user-defined-conversions-cpp-cli.md)  
  
-   [Comment : inclure une classe native dans un wrapper pour une utilisation par C\#](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)  
  
-   [Generic Classes \(C\+\+\/CLI\)](../windows/generic-classes-cpp-cli.md)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Notes**  
  
 Consultez [Classes et structures de référence](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx) et [Classes et structures de valeur](http://msdn.microsoft.com/library/windows/apps/hh699861.aspx).  
  
 **Paramètres**  
  
 *type\_base* \(facultatif\)  
 Type de base.  Une `ref class` ou un `ref struct` peuvent hériter de zéro interface ou plus et de zéro ou un type `ref`.  Une `value class` ou un `value struct` peuvent uniquement hériter de zéro interface ou plus.  
  
 Quand vous déclarez un objet à l'aide de mots clés `ref class` ou `ref struct`, l'objet est accessible par un handle, autrement dit, un pointeur de compteur de référence vers l'objet.  Quand la variable déclarée est hors de portée, le compilateur supprime automatiquement l'objet sous\-jacent.  Quand l'objet est utilisé en tant que paramètre dans un appel ou qu'il est stocké dans une variable, un handle vers l'objet est réellement transmis ou stocké.  
  
 Quand vous déclarez un objet à l'aide des mots clés `value class` ou `value struct`, la durée de vie de l'objet déclaré n'est pas contrôlée.  L'objet est comme toute autre classe ou tout autre struct C\+\+ standard.  
  
### Spécifications  
 Option du compilateur : **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Notes**  
  
 Le tableau suivant répertorie les différences spécifiques à C\+\+\/CLI par rapport à la syntaxe indiquée dans la section **Tous les runtimes**.  
  
 **Paramètres**  
  
 *type\_base* \(facultatif\)  
 Type de base.  Une `ref class` ou un `ref struct` peuvent hériter de zéro interface managée ou plus et de zéro ou un type référence.  Une `value class` ou un `value struct` peuvent uniquement hériter de zéro interface managée ou plus.  
  
 Les mots clés `ref class` et `ref struct` indiquent au compilateur que la classe ou le struct doivent être alloués sur le tas.  Quand l'objet est utilisé en tant que paramètre dans un appel ou qu'il est stocké dans une variable, une référence à l'objet est réellement transmise ou stockée.  
  
 Les mots clés `value class` et `value struct` indiquent au compilateur que la valeur de la classe allouée ou du struct alloué est transmise aux fonctions ou stockée dans les membres.  
  
### Spécifications  
 Option du compilateur : **\/clr**  
  
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)