---
title: "&#201;num&#233;rations (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "enum"
  - "enum_cpp"
  - "enum class"
  - "enum struct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "déclarations, énumérations"
  - "énumérateurs, déclaration"
  - "enum (mot clé) (C++)"
  - "constantes nommées, déclarations d’énumération"
  - "déclarer des énumérations"
ms.assetid: 081829db-5dca-411e-a53c-bffef315bcb3
caps.latest.revision: 27
caps.handback.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;num&#233;rations (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une énumération est un type défini par l'utilisateur qui se compose d'un jeu de constantes intégrales nommées, appelées énumérateurs.  
  
> [!NOTE]
>  Cet article décrit le type `enum` du langage C\+\+ de norme ISO et le type `enum class` délimité \(ou fortement typé\) qui a fait son apparition dans C\+\+11.  Pour plus d'informations sur les types `public enum class` ou `private enum class` en C\+\+\/CLI et C\+\+\/CX, consultez [enum, classe](../windows/enum-class-cpp-component-extensions.md).  
  
## Syntaxe  
  
```  
// unscoped enum:  
enum [identifier] [: type]  
  
{enum-list};   
  
// scoped enum:  
enum [class|struct]   
[identifier] [: type]   
{enum-list};  
```  
  
```  
// Forward declaration of enumerations  (C++11):  
enum A : int; // non-scoped enum must have type specified  
enum class B; // scoped enum defaults to int  
enum class C : short;  
```  
  
#### Paramètres  
 `identifier`  
 Nom de type donné à l'énumération.  
  
 `type`  
 Type sous\-jacent des énumérateurs ; tous les énumérateurs ont le même type sous\-jacent.  Peut être tout type intégral.  
  
 `enum-list`  
 Liste délimitée par des virgules des énumérateurs dans l'énumération.  Chaque nom d'énumérateur ou de variable dans la portée doit être unique.  Toutefois, les valeurs peuvent être dupliquées.  Dans un enum non délimité, la portée correspond à la portée environnante ; dans un enum délimité, la portée correspond à la liste `enum-list` proprement dite.  
  
 `class`  
 En utilisant ce mot clé dans la déclaration, vous spécifiez que l'enum est délimité et qu'un `identifier` doit être fourni.  Vous pouvez aussi utiliser le mot clé `struct` à la place de `class`, car ils sont sémantiquement équivalents dans ce contexte.  
  
## Notes  
 Une énumération fournit un contexte pour décrire une plage de valeurs qui sont représentées en tant que constantes nommées, également appelées « énumérateurs ».  Dans les types d'enum C et C\+\+ d'origine, les énumérateurs non qualifiés sont visibles dans toute la portée dans laquelle l'enum est déclaré.  Dans les enums délimités, le nom de l'énumérateur doit être qualifié par le nom du type d'enum.  L'exemple suivant illustre cette différence fondamentale entre les deux genres d'enums :  
  
```cpp  
namespace CardGame_Scoped  
{  
    enum class Suit { Diamonds, Hearts, Clubs, Spades };  
  
    void PlayCard(Suit suit)  
    {  
        if (suit == Suit::Clubs) // Enumerator must be qualified by enum type  
        { /*...*/}  
    }  
}  
  
namespace CardGame_NonScoped  
{  
    enum Suit { Diamonds, Hearts, Clubs, Spades };  
  
    void PlayCard(Suit suit)  
    {  
        if (suit == Clubs) // Enumerator is visible without qualification  
        { /*...*/  
        }  
    }  
}  
```  
  
 À chaque nom d'une énumération est assignée une valeur entière qui correspond à sa place dans l'ordre des valeurs de l'énumération.  Par défaut, la première valeur est 0, la suivante 1, et ainsi de suite, mais vous pouvez définir explicitement la valeur d'un énumérateur, comme indiqué ci\-dessous :  
  
```cpp  
  
enum Suit { Diamonds = 1, Hearts, Clubs, Spades };  
  
```  
  
 L'énumérateur `Diamonds` reçoit la valeur `1`.  Les énumérateurs suivants, si aucune valeur explicite ne leur est assignée, reçoivent la valeur de l'énumérateur précédent incrémentée d'une unité.  Dans l'exemple précédent, `Hearts` aurait la valeur 2, `Clubs` aurait la valeur 3, et ainsi de suite.  
  
 Chaque énumérateur est traité comme une constante et doit avoir un nom unique dans la portée où l'`enum` est défini \(pour les enums non délimités\) ou dans l'enum proprement dit \(pour les enums délimités\).  Il n'est pas obligatoire que les valeurs fournies aux noms soient uniques.  Par exemple, si la déclaration d'un enum non délimité `Suit` est la suivante :  
  
```cpp  
enum Suit { Diamonds = 5, Hearts, Clubs = 4, Spades };  
```  
  
 Les valeurs de `Diamonds`, `Hearts`, `Clubs` et `Spades` sont respectivement 5, 6, 4 et 5.  Notez que 5 est utilisé plusieurs fois ; cela est autorisé même si ce n'est peut\-être pas prévu.  Ces règles sont les mêmes pour les enums délimités.  
  
 **Règles de transtypage**  
  
 Les constantes enum non délimitées peuvent être implicitement converties en `int`, mais une valeur `int` n'est jamais implicitement convertie en valeur enum.  L'exemple suivant montre ce qui se produit si vous essayez d'assigner à `hand` une valeur qui n'est pas un `Suit` :  
  
```cpp  
int account_num = 135692;  
Suit hand;  
hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'  
  
```  
  
 Un transtypage est nécessaire pour convertir une valeur `int` en énumérateur délimité ou non délimité.  Toutefois, vous pouvez promouvoir un énumérateur non délimité en valeur entière sans transtypage.  
  
```cpp  
int account_num = Hearts; //OK if Hearts is in a unscoped enum  
```  
  
 L'utilisation des conversions implicites de cette façon peut provoquer des effets secondaires inattendus.  Pour aider à éliminer les erreurs de programmation associées aux enums non délimités, les valeurs d'enums délimités sont fortement typées.  Les énumérateurs délimités doivent être qualifiés par le nom du type d'enum \(identificateur\) et ne peuvent pas être implicitement convertis, comme indiqué dans l'exemple suivant :  
  
```cpp  
namespace ScopedEnumConversions  
{  
    enum class Suit { Diamonds, Hearts, Clubs, Spades };  
  
    void AttemptConversions()  
    {  
        Suit hand;   
        hand = Clubs; // error C2065: 'Clubs' : undeclared identifier  
        hand = Suit::Clubs; //Correct.  
        int account_num = 135692;  
        hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'  
        hand = static_cast<Suit>(account_num); // OK, but probably a bug!!!  
  
        account_num = Suit::Hearts; // error C2440: '=' : cannot convert from 'Suit' to 'int'  
        account_num = static_cast<int>(Suit::Hearts); // OK  
}  
  
```  
  
 Notez que la ligne `hand = account_num;` provoque toujours l'erreur avec les enums non délimités, comme indiqué précédemment.  Elle est autorisée avec un transtypage explicite.  Toutefois, avec les enums délimités, la tentative de conversion dans l'instruction suivante, `account_num = Suit::Hearts;`, n'est plus autorisée sans transtypage explicite.  
  
## Voir aussi  
 [Déclarations d'énumération C](../c-language/c-enumeration-declarations.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)