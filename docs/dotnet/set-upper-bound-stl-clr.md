---
title: "set::upper_bound (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::upper_bound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre upper_bound [STL/CLR]"
ms.assetid: 874d258a-990f-486f-ac7b-757a2f7c150a
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# set::upper_bound (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Recherche la fin de la plage qui correspond à une clé spécifiée.  
  
## Syntaxe  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### Paramètres  
 key  
 Valeur de clé à rechercher.  
  
## Notes  
 La méthode détermine le dernier élément `X` dans la séquence contrôlée dont le classement est équivalent à `key`.  Si aucun élément de ce type n'existe, ou si `X` est le dernier élément de la séquence contrôlée, cela retourne [set::end](../dotnet/set-end-stl-clr.md)`()` ; sinon cela renvoie un itérateur qui indique le premier élément au delà de `X`.  Vous l'utilisez pour rechercher la fin d'une séquence d'éléments figurant actuellement dans la séquence contrôlée qui correspond à la clé spécifiée.  
  
## Exemple  
  
```  
// cliext_set_upper_bound.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*upper_bound(L'a') = {0}",   
        *c1.upper_bound(L'a'));   
    System::Console::WriteLine("*upper_bound(L'b') = {0}",   
        *c1.upper_bound(L'b'));   
    return (0);   
    }  
  
```  
  
  **a b c**  
**upper\_bound\(L'x'\)\=\=end\(\) \= Vrai**  
**\*upper\_bound\(L'a'\) \= b**  
**\*upper\_bound\(L'b'\) \= c**   
## Configuration requise  
 **En\-tête :** \<cliext\/set\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [set](../dotnet/set-stl-clr.md)   
 [set::count](../dotnet/set-count-stl-clr.md)   
 [set::equal\_range](../dotnet/set-equal-range-stl-clr.md)   
 [set::find](../dotnet/set-find-stl-clr.md)   
 [set::lower\_bound](../dotnet/set-lower-bound-stl-clr.md)