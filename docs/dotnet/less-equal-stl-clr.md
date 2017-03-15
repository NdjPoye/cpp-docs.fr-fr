---
title: "less_equal (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::less_equal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "less_equal (fonction) (STL/CLR)"
ms.assetid: 87d5bebc-6e5a-4d70-b15c-7260d06d50f0
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# less_equal (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un functor qui, lorsqu'il est appelé, renvoie vrai uniquement si le premier argument est inférieur ou égal au second.  Vous l'utilisez pour spécifier un objet fonction au niveau de son type d'argument.  
  
## Syntaxe  
  
```  
template<typename Arg>  
    ref class less_equal  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    less_equal();  
    less_equal(less_equal<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### Paramètres  
 Arg  
 Type des arguments.  
  
## Fonctions membres  
  
|Définition de types|Description|  
|-------------------------|-----------------|  
|delegate\_type|Le type du délégué générique.|  
|first\_argument\_type|Le type du premier argument de functor.|  
|result\_type|Le type du résultat du functor.|  
|second\_argument\_type|Le type du deuxième argument du functor.|  
  
|Membre|Description|  
|------------|-----------------|  
|less\_equal|Construit le functor.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|opérateur\(\)|Calcule la fonction souhaitée.|  
|operator delegate\_type^|Convertit le functor en un délégué.|  
  
## Notes  
 La classe du modèle décrit un functor à deux arguments.  Elle définit l'opérateur membre `operator()` afin que, lorsque l'objet est appelé en tant que fonction, il renvoie vrai uniquement si le premier argument est supérieur ou égal au second.  
  
 Vous pouvez également transmettre l'objet comme argument de fonction dont le type est `delegate_type^` et il sera converti de façon appropriée.  
  
## Exemple  
  
```  
// cliext_less_equal.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(3);   
    c2.push_back(3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 3 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::less_equal<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **3 3**  
 **0 1**   
## Configuration requise  
 **En\-tête :** \<cliext\/functional\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [greater](../dotnet/greater-stl-clr.md)