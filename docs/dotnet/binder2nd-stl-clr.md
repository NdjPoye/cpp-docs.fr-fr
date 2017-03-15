---
title: "binder2nd (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::binder2nd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binder2nd (fonction) (STL/CLR)"
ms.assetid: f4be8722-1778-4cb9-9ec7-ad1443f6899f
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# binder2nd (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un functor d'un argument qui, lorsqu'il est appelé, retourne son functor à deux arguments appelé avec le premier argument fourni et le deuxième argument stockée.  Vous utilisez pour spécifier un objet fonction au niveau de son functor stocké.  
  
## Syntaxe  
  
```  
template<typename Fun>  
    ref class binder2nd  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::first_argument_type first_argument_type;  
    typedef typename Fun::second_argument_type second_argument_type;  
    typedef typename Fun:result_type result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        first_argument_type, result_type>  
        delegate_type;  
  
    binder2nd(Fun% functor, second_argument_type left);  
    binder2nd(binder2nd<Arg>% right);  
  
    result_type operator()(first_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### Paramètres  
 Fun  
 Le type de functor stocké.  
  
## Fonctions membres  
  
|Définition de type|Description|  
|------------------------|-----------------|  
|delegate\_type|Le type du délégué générique.|  
|first\_argument\_type|Le type du premier argument de foncteur|  
|result\_type|Le type du premier argument du résultat du foncteur.|  
|second\_argument\_type|Le type du deuxième argument de foncteur.|  
|type\_de\_fonction\_stocké|Type du functor.|  
  
|Membre|Description|  
|------------|-----------------|  
|binder2nd|Construit le foncteur.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|\(\) \(opérateur\)|Calcule la fonction souhaitée.|  
|opérateur type\_délégué^\(\)|Convertit le foncteur en un délégué.|  
  
## Notes  
 La classe du modèle décrit un functor d'une argument qui stocke un functor de deux arguments et un second argument.  Elle définit l'opérateur membre `operator()` afin que, lorsque l'objet est appelé en tant que fonction, elle retourne le résultat de l'appel du functor stockées au premier argument fourni et le deuxième argument stockée.  
  
 Vous pouvez également transmettre l'objet comme argument de fonction dont le type est `delegate_type^` et il sera converti de façon appropriée.  
  
## Exemple  
  
```  
// cliext_binder2nd.cpp   
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
    Myvector c3(2, 0);   
  
// display initial contents " 4 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::minus<int> sub_op;   
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        sub4);   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        bind2nd(sub_op, 4));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **0 \-1**  
 **0 \-1**   
## Configuration requise  
 **En\-tête :** \<cliext\/functional\>  
  
 **Espace de nommage:** cliext  
  
## Voir aussi  
 [bind2nd](../dotnet/bind2nd-stl-clr.md)