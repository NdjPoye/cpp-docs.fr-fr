---
title: "priority_queue::priority_queue (STL/CLR) | Microsoft Docs"
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
  - "cliext::priority_queue::priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "priority_queue (membre) (STL/CLR)"
ms.assetid: aab423d7-959e-48fd-9028-e9f45f43cb8a
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# priority_queue::priority_queue (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construit un objet d'adaptateur de conteneur.  
  
## Syntaxe  
  
```  
priority_queue();  
priority_queue(priority_queue<Value, Container> right);  
priority_queue(priority_queue<Value, Container> right);  
explicit priority_queue(value_compare^ pred);  
priority_queue(value_compare^ pred, container_type% cont);  
template<typename InIt>  
    priority_queue(InIt first, InIt last);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred, container_type% cont);  
```  
  
#### Paramètres  
 cont  
 Conteneur à copier.  
  
 first  
 Début de la plage à insérer.  
  
 last  
 Fin de la plage à insérer.  
  
 pred  
 Classer l'attribut de la séquence contrôlée.  
  
 right  
 Objet ou plage à insérer.  
  
## Notes  
 Le constructeur :  
  
 `priority_queue();`  
  
 crée un conteneur vide, avec le prédicat d'ordre par défaut.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat de classement par défaut.  
  
 Le constructeur :  
  
 `priority_queue(priority_queue<Value, Container>% right);`  
  
 crée un conteneur encapsulé qui est une copie de `right.get_container()`, avec l'attribut `right.value_comp()`.  Vous l'utilisez pour spécifier une séquence initiale contrôlée qui est une copie de la séquence contrôlée par l'objet queue `right`, avec le même prédicat de classement.  
  
 Le constructeur :  
  
 `priority_queue(priority_queue<Value, Container>^ right);`  
  
 crée un conteneur encapsulé qui est une copie de `right->get_container()`, avec l'attribut `right->value_comp()`.  Vous l'utilisez pour spécifier une séquence initiale contrôlée qui est une copie de la séquence contrôlée par l'objet queue `*right`, avec le même prédicat de classement.  
  
 Le constructeur :  
  
 `explicit priority_queue(value_compare^ pred);`  
  
 crée un conteneur vide, avec le prédicat d'ordre `pred`.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat de classement spécifié.  
  
 Le constructeur :  
  
 `priority_queue(value_compare^ pred, container_type cont);`  
  
 crée un conteneur vide, avec le prédicat d'ordre `pred`, puis met tous les éléments de `cont`. Vous l'utilisez pour spécifier une séquence contrôlée d'un conteneur existant, avec l'attribut spécifié.  
  
 Le constructeur :  
  
 `template<typename InIt>`  
  
 `priority_queue(InIt first, InIt last);`  
  
 crée un conteneur vide, inclus avec l'attribut par défaut, puis donne la séquence `[``first``,` `last``)`.  Vous l'utilisez pour spécifier une séquence contrôlée initiale d'une séquence spécifiée, avec l'attribut spécifié.  
  
 Le constructeur :  
  
 `template<typename InIt>`  
  
 `priority_queue(InIt first, InIt last,`  
  
 `value_compare^ pred);`  
  
 crée un conteneur vide, inclus avec l'attribut par défaut `pred`, puis donne la séquence `[``first``,` `last``)`.  Vous l'utilisez pour spécifier une séquence contrôlée initiale d'une séquence spécifiée, avec l'attribut spécifié.  
  
 Le constructeur :  
  
 `template<typename InIt>`  
  
 `priority_queue(InIt first, InIt last,`  
  
 `value_compare^ pred, container_type% cont);`  
  
 crée un conteneur vide, inclus avec l'attribut d'ordre `pred`, puis met tous les éléments de `cont` et la séquence `[``first``,` `last``)`.  Vous l'utilisez pour spécifier une séquence contrôlée initial d'un conteneur existant et un seqeuence spécifié, avec l'attribut d'ordre spécifié.  
  
## Exemple  
  
```  
// cliext_priority_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/deque>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
typedef cliext::deque<wchar_t> Mydeque;   
int main()   
    {   
// construct an empty container   
    Mypriority_queue c1;   
    Mypriority_queue::container_type^ wc1 = c1.get_container();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mypriority_queue c2 = cliext::greater<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    for each (wchar_t elem in wc1)   
        c2.push(elem);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule by copying an underlying container   
    Mypriority_queue c2x =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
   for each (wchar_t elem in c2x.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mypriority_queue c3(wc1->begin(), wc1->end());   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mypriority_queue c4(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>());   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range, another container, and an ordering rule   
    Mypriority_queue c5(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c5.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mypriority_queue c6(c3);   
    for each (wchar_t elem in c6.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mypriority_queue c7(%c3);   
    for each (wchar_t elem in c7.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule, by copying an underlying container   
    Mypriority_queue c8 =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c8.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **taille\(\) \= 0**  
 **c a b**  
**taille\(\) \= 0**  
 **a c b**  
 **a c b**  
 **c a b**  
 **a c b**  
 **un b c b c**  
 **c a b**  
 **c a b**  
 **a c b**   
## Configuration requise  
 **En\-tête :** \<cliext\/queue\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [priority\_queue::assign](../dotnet/priority-queue-assign-stl-clr.md)   
 [priority\_queue::generic\_container](../dotnet/priority-queue-generic-container-stl-clr.md)   
 [priority\_queue::operator\=](../dotnet/priority-queue-operator-assign-stl-clr.md)