---
title: "binder1st (STL/CLR) | Microsoft Docs"
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
  - "cliext::binder1st"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binder1st (fonction) (STL/CLR)"
ms.assetid: a989c9cc-a485-45d9-bd19-519018e6974b
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# binder1st (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un functor d'un argument qui, lorsqu'il est appelé, retourne son functor à deux arguments appelé avec le premier argument stocké et le deuxième argument fourni.  Vous utilisez pour spécifier un objet fonction au niveau de son functor stocké.  
  
## Syntaxe  
  
```  
template<typename Fun>  
    ref class binder1st  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::first_argument_type first_argument_type;  
    typedef typename Fun::second_argument_type second_argument_type;  
    typedef typename Fun:result_type result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        second_argument_type, result_type>  
        delegate_type;  
  
    binder1st(Fun% functor, first_argument_type left);  
    binder1st(binder1st<Arg>% right);  
  
    result_type operator()(second_argument_type right);  
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
|premier\_type\_argument|Le type du premier argument de foncteur|  
|resultat\_type|Le type du premier argument du résultat du foncteur.|  
|second\_type\_argument|Le type du deuxième argument de foncteur.|  
|type\_de\_fonction\_stocké|Type du foncteur.|  
  
|Membre|Description|  
|------------|-----------------|  
|binder1st|Construit le foncteur.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|\(\) \(opérateur\)|Calcule la fonction souhaitée.|  
|opérateur type\_délégué^\(\)|Convertit le foncteur en un délégué.|  
  
## Notes  
 La classe du modèle décrit un functor d'une argument qui stocke un functor de deux arguments et un premier argument.  Elle définit l'opérateur membre `operator()` afin que, lorsque l'objet est appelé en tant que fonction, elle retourne le résultat de l'appel du functor stockées au premier argument stocké et le deuxième argument fourni.  
  
 Vous pouvez également transmettre l'objet comme argument de fonction dont le type est `delegate_type^` et il sera converti de façon appropriée.  
  
## Exemple  
  
```  
// cliext_binder1st.cpp   
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
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        subfrom3);   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        bind1st(sub_op, 3));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **\-1 0**  
 **\-1 0**   
## Configuration requise  
 **En\-tête :** \<cliext\/functional\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [bind1st](../dotnet/bind1st-stl-clr.md)