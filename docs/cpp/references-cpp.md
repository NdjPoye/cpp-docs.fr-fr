---
title: Références (C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- objects [C++], referencing
- references [C++]
- references, to pointers
- declarations, references
- references, declaring
- referencing objects, declarator syntax
ms.assetid: 68156f7f-97a0-4b66-b26d-b25ade5e3bd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe60a849cb1b14420ab83af77362ddda433884a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="references-c"></a>Références (C++)
Une référence, comme un pointeur, stocke l'adresse d'un objet situé ailleurs dans la mémoire. Contrairement à un pointeur, une référence après son initialisation ne peut pas être définie pour faire référence à un autre objet ni prendre la valeur null. Il existe deux types de références : les références lvalue qui font référence à un nommé variable et les références rvalue qui font référence à un [objet temporaire](../cpp/temporary-objects.md). L'opérateur & désigne une référence lvalue et l'opérateur && désigne une référence rvalue ou une référence universelle (rvalue ou lvalue) en fonction du contexte.  
  
 Les références peuvent être déclarées à l'aide de la syntaxe suivante :  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers   
[ms-modifier] declarator [= expression];  
```  
  
 Tout déclarateur valide spécifiant une référence peut être utilisé. La syntaxe simplifiée suivante s'applique, sauf si la référence est une référence à un type de fonction ou à un type tableau :  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers [& or &&]   
[cv-qualifiers] identifier [= expression];  
```  
  
 Les références sont déclarées à l'aide de la séquence suivante :  
  
 1. Les spécificateurs de déclaration :  
  
-   Spécificateur de classe de stockage facultatif.  
  
-   Facultatif **const** et/ou `volatile` qualificateurs.  
  
-   Spécificateur de type : nom d'un type.  
  
-   2. Déclarateur :  
  
-   Modificateur spécifique Microsoft facultatif. Pour plus d’informations, consultez [modificateurs spécifiques Microsoft](../cpp/microsoft-specific-modifiers.md).  
  
-   Opérateur & ou &&  
  
-   Facultatif **const** et/ou `volatile` qualificateurs.  
  
-   Identificateur.  
  
 3. Initialiseur facultatif.  
  
 Les formulaires de déclarateurs plus complexes pour des pointeurs vers des tableaux et les fonctions s’appliquent également aux références à des tableaux et les fonctions, consultez [pointeurs](../cpp/pointers-cpp.md) et [déclarateurs](http://msdn.microsoft.com/en-us/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838).  
  
 Plusieurs déclarateurs et initialiseurs peuvent apparaître dans une liste séparée par des virgules après un spécificateur de déclaration unique. Par exemple :  
  
```  
int &i;   
int &i, &j;   
```  
  
 Les références, les pointeurs et les objets peuvent être déclarés ensemble :  
  
```  
int &ref, *ptr, k;   
```  
  
 Une référence contient l'adresse d'un objet, mais se comporte syntaxiquement comme un objet.  
  
 Dans le programme suivant, notez que le nom de l'objet, `Today`, et la référence à l'objet, `TodayRef`, peuvent être utilisés de la même manière dans les programmes :  
  
## <a name="example"></a>Exemple  
  
```  
// references.cpp  
#include <stdio.h>  
struct S {  
   short i;  
};  
  
int main() {  
   S  s;   // Declare the object.  
   S& SRef = s;   // Declare the reference.  
   s.i = 3;  
  
   printf_s("%d\n", s.i);  
   printf_s("%d\n", SRef.i);  
  
   SRef.i = 4;  
   printf_s("%d\n", s.i);  
   printf_s("%d\n", SRef.i);  
}  
```  
  
```Output  
3  
3  
4  
4  
```  
  
## <a name="comment"></a>Commentaire  
 Rubriques de cette section :  
  
-   [Arguments de fonction de type référence](../cpp/reference-type-function-arguments.md)  
  
-   [Retours de fonction de type référence](../cpp/reference-type-function-returns.md)  
  
-   [Références aux pointeurs](../cpp/references-to-pointers.md)  
  
