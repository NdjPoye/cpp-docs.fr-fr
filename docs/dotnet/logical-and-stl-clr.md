---
title: "logical_and (STL/CLR) | Microsoft Docs"
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
  - "cliext::logical_and"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "logical_and (fonction) (STL/CLR)"
ms.assetid: ae103802-11e0-4060-a4f3-4f6fdc209e7c
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# logical_and (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un foncteur qui, lorsqu'il est appelé, renvoie true uniquement si le premier argument ET le deuxième sont testés comme true.  Vous l'utilisez pour spécifier un objet fonction au niveau de son type d'argument.  
  
## Syntaxe  
  
```  
template<typename Arg>  
    ref class logical_and  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    logical_and();  
    logical_and(logical_and<Arg>% right);  
  
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
|logical\_and|Construit le foncteur.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|\(\) \(opérateur\)|Calcule la fonction souhaitée.|  
|opérateur delegate\_type^|Convertit le foncteur en un délégué.|  
  
## Notes  
 La classe du modèle décrit un foncteur à deux arguments.  Elle définit l'opérateur membre `operator()` afin que, lorsque l'objet est appelé en tant que fonction, il renvoie true uniquement si le premier argument ET le second sont testés comme true.  
  
 Vous pouvez également transmettre l'objet comme argument de fonction dont le type est `delegate_type^` et il sera converti de façon appropriée.  
  
## Exemple  
  
```  
// cliext_logical_and.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(2);   
    c1.push_back(0);   
    Myvector c2;   
    c2.push_back(3);   
    c2.push_back(0);   
    Myvector c3(2, 0);   
  
// display initial contents " 1 0" and " 1 0"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::logical_and<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **2 0**  
 **3 0**  
 **1 0**   
## Configuration requise  
 **En\-tête :** \<cliext\/functional\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [logical\_or](../dotnet/logical-or-stl-clr.md)