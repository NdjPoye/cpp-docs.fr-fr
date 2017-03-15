---
title: "D&#233;clarateur de r&#233;f&#233;rence Lvalue&#160;: &amp; | Microsoft Docs"
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
  - "&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& (opérateur), opérateur de référence"
  - "opérateur de référence"
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;clarateur de r&#233;f&#233;rence Lvalue&#160;: &amp;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Contient l'adresse d'un objet mais se comporte syntaxiquement comme un objet.  
  
## Syntaxe  
  
```  
  
type-id & cast-expression  
```  
  
## Notes  
 Vous pouvez considérer une référence lvalue comme un autre nom d'un objet.  Une déclaration de référence lvalue se compose d'une liste facultative de spécificateurs suivie d'un déclarateur de référence.  Une référence doit être initialisée et ne peut pas être modifiée.  
  
 Tout objet dont l'adresse peut être convertie en un type pointeur donné peut également être converti en type référence similaire.  Par exemple, tout objet dont l'adresse peut être convertie en type `char *` peut également être converti en type `char &`.  
  
 Ne confondez pas les déclarations de référence avec l'utilisation de l'[opérateur\-d'adresse](../cpp/address-of-operator-amp.md).  Quand l'`&`*identificateur* est précédé d'un type, comme `int` ou `char`, l'*identificateur* est déclaré comme une référence au type.  Quand l'`&`*identificateur* n'est pas précédé d'un type, l'utilisation est celle de l'opérateur d'adresse.  
  
## Exemple  
 L'exemple suivant illustre le déclarateur de référence en déclarant un objet `Person` et une référence à cet objet.  `rFriend` étant une référence à `myFriend`, la mise à jour de l'une ou l'autre variable modifie le même objet.  
  
```  
// reference_declarator.cpp  
// compile with: /EHsc  
// Demonstrates the reference declarator.  
#include <iostream>  
using namespace std;  
  
struct Person  
{  
    char* Name;  
    short Age;  
};  
  
int main()  
{  
   // Declare a Person object.  
   Person myFriend;  
  
   // Declare a reference to the Person object.  
   Person& rFriend = myFriend;  
  
   // Set the fields of the Person object.  
   // Updating either variable changes the same object.  
   myFriend.Name = "Bill";  
   rFriend.Age = 40;  
  
   // Print the fields of the Person object to the console.  
   cout << rFriend.Name << " is " << myFriend.Age << endl;  
}  
```  
  
  **Bill a 40 ans**   
## Voir aussi  
 [Références](../cpp/references-cpp.md)   
 [Arguments de fonction de type référence](../cpp/reference-type-function-arguments.md)   
 [Retours de fonction de type référence](../cpp/reference-type-function-returns.md)   
 [Références aux pointeurs](../cpp/references-to-pointers.md)