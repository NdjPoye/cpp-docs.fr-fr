---
title: "queue::queue (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::queue::queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "queue (membre) (STL/CLR)"
ms.assetid: 6106c07f-d5eb-4f0b-82df-ee4e2e751047
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# queue::queue (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construit un objet d'adaptateur de conteneur.  
  
## Syntaxe  
  
```  
queue();  
queue(queue<Value, Container>% right);  
queue(queue<Value, Container>^ right);  
explicit queue(container_type% wrapped);  
```  
  
#### Paramètres  
 right  
 Objet à copier.  
  
 inclus  
 Conteneurs inclus à utiliser.  
  
## Notes  
 Le constructeur :  
  
 `queue();`  
  
 crée un conteneur encapsulé vide.  Vous l'utilisez pour spécifier une séquence contrôlée initialement vide.  
  
 Le constructeur :  
  
 `queue(queue<Value, Container>% right);`  
  
 crée un conteneur encapsulé qui est une copie de `right.get_container()`.  Vous l'utilisez pour spécifier une séquence contrôlée par initiale qui est une copie de la séquence contrôlée par l'objet en attente `right`.  
  
 Le constructeur :  
  
 `queue(queue<Value, Container>^ right);`  
  
 crée un conteneur encapsulé qui est une copie de `right->get_container()`.  Vous l'utilisez pour spécifier une séquence contrôlée par initiale qui est une copie de la séquence contrôlée par l'objet en attente `*right`.  
  
 Le constructeur :  
  
 `explicit queue(container_type wrapped);`  
  
 utilise le conteneur existant `wrapped` comme conteneurs inclus.  Vous l'utilisez pour créer une file d'attente à partir d'un conteneur existant.  
  
## Exemple  
  
```  
// cliext_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/list>   
  
typedef cliext::queue<wchar_t> Myqueue;   
typedef cliext::list<wchar_t> Mylist;   
typedef cliext::queue<wchar_t, Mylist> Myqueue_list;   
int main()   
    {   
// construct an empty container   
    Myqueue c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Mylist v2(5, L'x');   
    Myqueue_list c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myqueue_list c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Myqueue_list c4(%c2);   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **x x x x x**  
 **x x x x x**  
 **x x x x x**   
## Configuration requise  
 **En\-tête :** \<cliext\/queue\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [queue](../dotnet/queue-stl-clr.md)   
 [queue::assign](../dotnet/queue-assign-stl-clr.md)   
 [queue::generic\_container](../dotnet/queue-generic-container-stl-clr.md)   
 [queue::operator\=](../dotnet/queue-operator-assign-stl-clr.md)