---
title: "equal_to (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::equal_to"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "equal_to (fonction) (STL/CLR)"
ms.assetid: 9dd6e27d-e695-470f-b7a7-19a6db970ee5
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# equal_to (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un foncteur qui, lorsqu'il est appelé, renvoie vrai uniquement si le premier argument n'est pas égal au second.  Vous l'utilisez pour spécifier un objet fonction au niveau de son type d'argument.  
  
## Syntaxe  
  
```  
template<typename Arg>  
    ref class equal_to  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    equal_to();  
    equal_to(equal_to<Arg>% right);  
  
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
|type\_délégué|Le type du délégué générique.|  
|premier\_type\_d'argument.|Le type du premier argument de foncteur|  
|result\_type|Le type du premier argument du résultat du foncteur.|  
|deuxième\_type\_d'argument.|Le type du deuxième argument de foncteur.|  
  
|Membre|Description|  
|------------|-----------------|  
|equal\_to|Construit le foncteur.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|opérateur\(\)|Calcule la fonction souhaitée.|  
|opérateur type\_délégué^\(\)|Caste le foncteur à un délégué.|  
  
## Notes  
 La classe du modèle décrit un foncteur à deux arguments.  Elle définit l'opérateur membre `operator()` afin que, lorsque l'objet est appelé en tant que fonction, il renvoie true uniquement si le premier argument n'est pas égal au second.  
  
 Transmettez également l'objet comme argument de fonction dont le type est `delegate_type^` et il sera converti de façon appropriée.  
  
## Exemple  
  
```  
// cliext_equal_to.cpp   
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
        c2.begin(), c3.begin(), cliext::equal_to<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **4 4**  
 **1 0**   
## Configuration requise  
 **En\-tête:** \<cliext\/functional\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [not\_equal\_to](../dotnet/not-equal-to-stl-clr.md)