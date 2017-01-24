---
title: "operator&gt;= (multiset) (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiset::operator>="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator>= (membre) (STL/CLR)"
ms.assetid: 978cc521-e810-4f3a-85e7-880d6b45db59
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&gt;= (multiset) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comparaison « supérieur ou égal à » de listes.  
  
## Syntaxe  
  
```  
template<typename Key>  
    bool operator>=(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### Paramètres  
 left  
 Conteneur de gauche à comparer.  
  
 right  
 Conteneur de droite à comparer.  
  
## Notes  
 La fonction d'opérateur retourne `!(``left` `<` `right``)`.  Vous l'utilisez pour tester si `left` n'est pas ordonné avant `right` lorsque les deux ensembles multiples sont comparées élément par élément.  
  
## Exemple  
  
```  
// cliext_multiset_operator_ge.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] >= [a b c] is {0}",   
        c1 >= c1);   
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",   
        c1 >= c2);   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b d**  
**\[a b c\] \>\= \[a b c\] est Vrai**  
**\[a b c\] \>\= \[a b d\] est Faux**   
## Configuration requise  
 **En\-tête :** \<cliext\/set\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [operator\=\= \(multiset\)](../dotnet/operator-equality-multiset-stl-clr.md)   
 [operator\!\= \(multiset\)](../dotnet/operator-inequality-multiset-stl-clr.md)   
 [operator\< \(multiset\)](../dotnet/operator-less-than-multiset-stl-clr.md)   
 [operator\> \(multiset\)](../dotnet/operator-greater-than-multiset-stl-clr.md)   
 [operator\<\= \(multiset\)](../dotnet/operator-less-or-equal-multiset-stl-clr.md)