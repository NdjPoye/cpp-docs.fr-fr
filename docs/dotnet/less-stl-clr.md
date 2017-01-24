---
title: "less (STL/CLR) | Microsoft Docs"
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
  - "cliext::less"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "less (fonction) (STL/CLR)"
ms.assetid: fae56216-af66-4cb9-a688-be58a7c7edbb
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# less (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un foncteur qui, lorsqu'il est appelé, renvoie vrai uniquement si le premier argument est inférieur au second.  Vous l'utilisez pour spécifier un objet fonction au niveau de son type d'argument.  
  
## Syntaxe  
  
```  
template<typename Arg>  
    ref class less  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    less();  
    less(less<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### Paramètres  
 Arg  
 Type des arguments.  
  
## Fonctions membres  
  
|Définition de type|Description|  
|------------------------|-----------------|  
|delegate\_type|Le type du délégué générique.|  
|first\_argument\_type|Le type du premier argument de foncteur|  
|result\_type|Le type du résultat du foncteur.|  
|second\_argument\_type|Le type du deuxième argument de foncteur.|  
  
|Membre|Description|  
|------------|-----------------|  
|less|Construit le foncteur.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|\(\) \(opérateur\)|Calcule la fonction souhaitée.|  
|operator delegate\_type^|Convertit le foncteur en un délégué.|  
  
## Notes  
 La classe du modèle décrit un foncteur à deux arguments.  Elle définit l'opérateur membre `operator()` afin que, lorsque l'objet est appelé en tant que fonction, il renvoie true uniquement si le premier argument est inférieur au second.  
  
 Vous pouvez également transmettre l'objet comme argument de fonction dont le type est `delegate_type^` et il sera converti de façon appropriée.  
  
## Exemple  
  
```  
// cliext_less.cpp   
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
    c2.push_back(4);   
    c2.push_back(4);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 4 4"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::less<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **4 4**  
 **0 1**   
## Configuration requise  
 **En\-tête :** \<cliext\/functional\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [greater\_equal](../dotnet/greater-equal-stl-clr.md)