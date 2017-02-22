---
title: "D&#233;claration d&#39;un type de classe manag&#233;e | Microsoft Docs"
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
  - "types _gc"
  - "__value (mot clé)"
  - "class (mot clé C++), CLR"
  - "classes (C++), managé"
  - "classe d'interface (mot clé)"
  - "classes managées"
  - "ref (mot clé C++)"
  - "value (mot clé C++)"
  - "types valeur, déclarer"
ms.assetid: 16de9c94-91d7-492f-8ac7-f0729cc627e9
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# D&#233;claration d&#39;un type de classe manag&#233;e
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La façon de déclarer un type de classe de référence a été modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 En Extensions managées, un type de classe référence se préface à l'aide du mot clé `__gc`.  Dans la nouvelle syntaxe, le mot clé `__gc` est remplacé par l'un des deux mots clés espacés : `ref class` ou `ref struct`.  Le choix de `struct` ou de `class` indique simplement le niveau d'accès par défaut, public \(pour `struct`\) ou privé \(pour `class`\), de ses membres déclarés dans une section initiale sans étiquette du corps du type.  
  
 De même, un type de classe value se préface à l'aide du mot clé `__value` en Extensions managées.  Dans la nouvelle syntaxe, le mot clé `__value` est remplacé par l'un des deux mots clés espacés : `value class` ou `value struct`.  
  
 Un type interface, en Extensions managées, était indiqué par le mot clé `__interface`.  Dans la nouvelle syntaxe, celui\-ci est remplacé par `interface class`.  
  
 Par exemple, les déclarations de classe suivantes en Extensions managées :  
  
```  
public __gc class Block {};     // reference class  
public __value class Vector {}; // value class  
public __interface IFooBar {};  // interface class  
```  
  
 Dans la nouvelle syntaxe, celles\-ci sont déclarées de façon équivalente comme suit :  
  
```  
public ref class Block {};         // reference class  
public value class Vector {};      // value class  
public interface class IFooBar {}; // interface class  
```  
  
## Spécification de la classe comme abstraite  
 Sous les extensions managées, le mot clé `__abstract` est placé avant le mot clé `class` \(soit avant soit après le `__gc`\) pour indiquer que la classe est incomplète et que les objets de la classe ne peuvent pas être créés dans le programme :  
  
```  
public __gc __abstract class Shape {};  
public __gc __abstract class Shape2D: public Shape {};  
```  
  
 Dans la nouvelle syntaxe, le mot clé contextuel `abstract` est spécifié à la suite du nom de la classe et avant le corps de classe, la liste de la dérivation de la classe de base ou le point\-virgule.  
  
```  
public ref class Shape abstract {};  
public ref class Shape2D abstract : public Shape{};  
```  
  
 Naturellement, la signification sémantique reste inchangée.  
  
## Spécifier la classe comme sealed  
 Sous les extensions managées, le mot clé `__sealed` est placé avant le mot clé `class` \(soit avant soit après `__gc`\) pour indiquer que les objets de la classe ne peuvent pas être hérités de :  
  
```  
public __gc __sealed class String {};  
```  
  
 Dans la nouvelle syntaxe, le mot clé contextuel `sealed` est spécifié à la suite du nom de la classe et avant le corps de classe, la liste de la dérivation de la classe de base ou le point\-virgule.  
  
 Vous pouvez à la fois dériver une classe et la sceller.  Par exemple, la classe `String` est dérivée implicitement de `Object`.  L'avantage de sceller une classe est que cette opération autorise la résolution statique \(à savoir lors de la compilation\) de tous les appels de fonctions virtuelles à travers l'objet de classe de référence sealed.  Cela s'explique parce que le spécificateur `sealed` garantit que le handle de suivi `String` ne peut pas faire référence à une classe dérivée ultérieurement qui pourrait fournir une instance de substitution de la méthode virtuelle appelée.  Voici un exemple de classe sealed dans nouvelle syntaxe :  
  
```  
public ref class String sealed {};  
```  
  
 On peut également spécifier une classe comme étant à la fois abstraite et scellée \(sealed\) ; c'est une condition spéciale qui indique une classe statique.  Cela est décrit dans la documentation du CLR comme suit :  
  
 « Un type qui est à la fois `abstract` et `sealed` ne doit avoir que des membres statiques et sert de ce que certains langages appellent un espace de noms ».  
  
 Par exemple, voici une déclaration d'une classe abstraite scellée sous la syntaxe d'Extensions managées :  
  
```  
public __gc __sealed __abstract class State {  
public:  
   static State() {}  
   static bool inParamList();  
  
private:  
   static bool ms_inParam;  
};  
```  
  
 et voici cette déclaration traduite dans la nouvelle syntaxe :  
  
```  
public ref class State abstract sealed {  
public:  
   static State();  
   static bool inParamList();  
  
private:  
   static bool ms_inParam;  
};  
```  
  
## Héritage CLR : spécification de la classe de base  
 Sous le modèle objet du CLR, seul l'héritage public seul est pris en charge.  Toutefois, les Extensions managées ont conservé l'interprétation par défaut d'ISO\-C\+\+ d'une classe de base sans mot clé d'accès spécifiant une dérivation privée.  Cela signifiait que chaque déclaration de l'héritage CLR devait fournir le mot clé `public` pour substituer l'interprétation par défaut.  
  
```  
// Managed Extensions: error: defaults to private derivation  
__gc class Derived : Base {};  
```  
  
 Dans la nouvelle syntaxe de la définition, l'absence d'un mot clé d'accès indique une dérivation publique dans une définition d'héritage CLR.  Ainsi, le mot clé d'accès `public` est maintenant facultatif.  Bien que cela n'exige aucune modification du code d'Extensions managées pour C\+\+, je note ici ce changement par souci d'exhaustivité.  
  
```  
// New syntax: ok: defaults to public derivation  
ref class Derived : Base{};  
```  
  
## Voir aussi  
 [Types managés \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)   
 [abstract](../windows/abstract-cpp-component-extensions.md)   
 [sealed](../windows/sealed-cpp-component-extensions.md)