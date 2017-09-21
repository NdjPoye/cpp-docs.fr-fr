---
title: "vector::insert (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre insert [STL/CLR]"
ms.assetid: f240cabf-f9d1-40c1-9cfb-975a90955546
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# vector::insert (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ajoute les éléments à une position spécifiée.  
  
## Syntaxe  
  
```  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### Paramètres  
 count  
 Nombre d'éléments à insérer.  
  
 premier  
 Début de la plage à insérer.  
  
 last  
 Fin de la plage à insérer.  
  
 right  
 Énumération à insérer.  
  
 val  
 Valeur de l'élément à insérer.  
  
 where  
 Où insérer avant dans le conteneur.  
  
## Notes  
 Chaque méthode insère, avant l'élément pointé par `where` dans la séquence contrôlée, une séquence qui est spécifiée par les opérandes restantes.  
  
 La première méthode insère un élément qui a la valeur `val` et retourne un itérateur qui indique l'élément récemment inséré.  Vous l'utilisez pour insérer un élément avant une position indiquée par un itérateur.  
  
 La deuxième fonction membre insère une répétition des éléments `count` de la valeur `val`.  Vous l'utilisez pour insérer des zéro ou plusieurs éléments contigus qui sont tous des copies de la même valeur.  
  
 Si `InIt` est un type entier, la troisième méthode se comporte de la même manière que `insert(``where``, (size_type)``first``, (value_type)``last``)`.  Sinon, il insère la séquence `[``first``,` `last``)`.  Vous l'utilisez pour insérer zéro ou plusieurs éléments contigus copiés à partir d'une autre séquence.  
  
 La quatrième méthode insère la séquence indiquée par `right`.  Vous l'utilisez pour insérer une séquence décrite par un énumérateur.  
  
 En insérant un élément unique, le nombre de copies d'éléments est linéaire par rapport au nombre d'éléments entre le point d'insertion et la fin plus proche de la séquence. \(En insérant un ou plusieurs éléments à l'un ou l'autre bout de la séquence, la copie d'élément n'a pas lieu.\) Si `InIt` est un itérateur d'entrée, la troisième fonction membre exécute effectivement une insertion pour chaque élément de la séquence.  Autrement, quand `N` éléments sont insérés, le nombre de copies d'éléments est linéaire par rapport à `N` ainsi qu'aux nombre d'éléments entre le point d'insertion et la fin la plus proche de la séquence.  
  
## Exemple  
  
```  
// cliext_vector_insert.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using iterator   
    cliext::vector<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::vector<wchar_t> c2;   
    c2.insert(c2.begin(), 2, L'y');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    it = c1.end();   
    c2.insert(c2.end(), c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    c2.insert(c2.begin(),   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**insert\(begin\(\)\+1, L'X\) \= x**  
 **a x b c**  
 **y y**  
 **y y a x b**  
 **a x b c y y a x b**   
## Configuration requise  
 **En\-tête :** \<cliext\/vector\>  
  
 **Espace de nom** cliext  
  
## Voir aussi  
 [vecteur](../dotnet/vector-stl-clr.md)   
 [vector::assign](../dotnet/vector-assign-stl-clr.md)