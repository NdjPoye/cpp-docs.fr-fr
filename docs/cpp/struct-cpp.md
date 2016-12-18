---
title: "struct (C++) | Microsoft Docs"
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
  - "struct"
  - "struct_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "struct (constructeurs)"
ms.assetid: 3c6ba273-e248-4ff1-8c69-d2abcf1263c6
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# struct (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le mot clé `struct` définit un type structure et\/ou une variable d'un type structure.  
  
## Syntaxe  
  
```  
[template-spec] struct [ms-decl-spec] [tag [: base-list ]]  
{   
   member-list   
} [declarators];  
[struct] tag declarators;  
```  
  
#### Paramètres  
 `template-spec`  
 Spécifications de modèle facultatives.  Pour plus d'informations, consultez [Spécifications de modèle](../Topic/Template%20Specifications.md).  
  
 `struct`  
 Le mot clé `struct`.  
  
 `ms-decl-spec`  
 Spécification de classe de stockage facultative.  Pour plus d'informations, consultez le mot clé [\_\_declspec](../cpp/declspec.md).  
  
 `tag`  
 Nom de type donné à la structure.  La balise devient un mot réservé dans la portée de la structure.  La balise est facultative.  Si elle est omise, une structure anonyme est définie.  Pour plus d'informations, consultez [Types de classes anonymes](../cpp/anonymous-class-types.md).  
  
 `base-list`  
 Liste facultative des classes ou structures dont dérivent les membres de cette structure.  Pour plus d'informations, consultez [Classes de base](../cpp/base-classes.md).  Chaque nom de classe de base ou de structure peut être précédé d'un spécificateur d'accès \([public](../cpp/public-cpp.md), [private](../cpp/private-cpp.md) ou [protected](../cpp/protected-cpp.md)\) et du mot clé [virtual](../cpp/virtual-cpp.md).  Pour plus d'informations, consultez le tableau d'accès aux membres dans [Contrôle de l'accès aux membres de classe](../misc/controlling-access-to-class-members.md), pour plus d'informations.  
  
 `member-list`  
 Liste des membres de structure.  Pour plus d'informations, consultez [Vue d'ensemble des membres de classe](../cpp/class-member-overview.md).  La seule différence ici est que `struct` est utilisé à la place de `class`.  
  
 `declarators`  
 Liste des déclarateurs spécifiant les noms de la classe.  Les listes des déclarateurs déclarent une ou plusieurs instances du type structure.  Les déclarateurs peuvent inclure des listes d'initialiseurs si toutes les données membres de la classe sont `public`.  Les listes d'initialiseurs sont fréquentes dans les structures, car les membres de données sont `public` par défaut.  Pour plus d'informations, consultez [Vue d'ensemble des déclarateurs](../cpp/overview-of-declarators.md).  
  
## Notes  
 Un type structure est un type composite défini par l'utilisateur.  Il comprend des champs ou des membres qui peuvent avoir différents types.  
  
 En C\+\+, une structure est identique à une classe sauf que ses membres sont `public` par défaut.  
  
 Pour plus d'informations sur les classes et les structures managées, consultez [Classes et structures](../windows/classes-and-structs-cpp-component-extensions.md).  
  
## Utilisation d'une structure  
 En C, vous devez utiliser explicitement le mot clé `struct` pour déclarer une structure.  En C\+\+, vous n'avez pas besoin d'utiliser le mot clé `struct` après avoir défini le type.  
  
 Vous avez la possibilité de déclarer des variables lorsque le type de structure est défini en plaçant un ou plusieurs noms de variables séparés par des virgules entre l'accolade fermante et le point\-virgule.  
  
 Les variables de structure peuvent être initialisées.  L'initialisation de chaque variable doit être placée entre accolades.  
  
 Pour plus d'informations, consultez [class](../cpp/class-cpp.md), [union](../cpp/unions.md) et [enum](../cpp/enumerations-cpp.md).  
  
## Exemple  
  
```  
#include <iostream>  
using namespace std;  
  
struct PERSON {   // Declare PERSON struct type  
    int age;   // Declare member types  
    long ss;  
    float weight;  
    char name[25];  
} family_member;   // Define object of type PERSON  
  
struct CELL {   // Declare CELL bit field  
    unsigned short character  : 8;  // 00000000 ????????  
    unsigned short foreground : 3;  // 00000??? 00000000  
    unsigned short intensity  : 1;  // 0000?000 00000000  
    unsigned short background : 3;  // 0???0000 00000000  
    unsigned short blink      : 1;  // ?0000000 00000000  
} screen[25][80];       // Array of bit fields   
  
int main() {  
    struct PERSON sister;   // C style structure declaration  
    PERSON brother;   // C++ style structure declaration  
    sister.age = 13;   // assign values to members  
    brother.age = 7;  
    cout << "sister.age = " << sister.age << '\n';  
    cout << "brother.age = " << brother.age << '\n';  
  
    CELL my_cell;  
    my_cell.character = 1;  
    cout << "my_cell.character = " << my_cell.character;  
}  
// Output:  
// sister.age = 13  
// brother.age = 7  
// my_cell.character = 1  
```  
  
## Voir aussi  
 [\(NOTINBUILD\) Defining Class Types](http://msdn.microsoft.com/fr-fr/e8c65425-0f3a-4dca-afc2-418c3b1e57da)