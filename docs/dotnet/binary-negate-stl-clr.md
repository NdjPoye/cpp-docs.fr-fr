---
title: "binary_negate (STL/CLR) | Microsoft Docs"
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
  - "cliext::binary_negate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binary_negate (fonction) (STL/CLR)"
ms.assetid: 0c3b47eb-0f37-4cb2-b879-4c9f0e57d275
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# binary_negate (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un functor qui, lorsqu'il est appelé, retourne le NOT logique de son functor stocké à deux arguments.  Vous utilisez pour spécifier un objet fonction au niveau de son functor stocké.  
  
## Syntaxe  
  
```  
template<typename Fun>  
    ref class binary_negate  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::first_argument_type first_argument_type;  
    typedef typename Fun::second_argument_type second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    explicit binary_negate(Fun% functor);  
    binary_negate(binary_negate<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### Paramètres  
 Fun  
 Le type de functor stocké.  
  
## Fonctions membres  
  
|Définition de type|Description|  
|------------------------|-----------------|  
|type\_délégué|Le type du délégué générique.|  
|premier\_type\_d'argument.|Le type du premier argument de functor.|  
|type\_de\_résultat|Le type du premier argument de functor.|  
|deuxième\_type\_d'argument.|Le type du deuxième argument de functor.|  
|type\_de\_fonction\_stocké|Type du functor.|  
  
|Membre|Description|  
|------------|-----------------|  
|binary\_negate|Construit le functor.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|opérateur\(\)|Calcule la fonction souhaitée.|  
|opérateur type\_délégué^\(\)|Convertit le functor à un délégué.|  
  
## Notes  
 La classe du modèle décrit un functor de deux arguments qui stocke un autre functor de deux arguments.  Elle définit l'opérateur membre `operator()` afin que, lorsque l'objet est appelé en tant que fonction, elle retourne un NOT logique du functor stocké appelé avec les deux arguments.  
  
 Vous pouvez également transmettre l'objet en tant qu'argument de fonction dont le type est `delegate_type^` et il sera converti correctement.  
  
## Exemple  
  
```  
// cliext_binary_negate.cpp   
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
    cliext::less<int> less_op;   
  
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(),   
        cliext::binary_negate<cliext::less<int> >(less_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::not2(less_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **4 4**  
 **1 0**  
 **1 0**   
## Configuration requise  
 **En\-tête:** \<cliext\/functional\>  
  
 **Espace de noms:** cliext  
  
## Voir aussi  
 [not2](../dotnet/not2-stl-clr.md)