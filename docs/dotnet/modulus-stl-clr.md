---
title: "modulus (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::modulus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "modulus (fonction) (STL/CLR)"
ms.assetid: 49907edd-6e32-4c81-8ef2-e9c6f512437f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# modulus (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle décrit un foncteur qui, lorsqu'il est appelé, retourne le premier argument modulo le second.  Vous l'utilisez pour spécifier un objet fonction au niveau de son type d'argument.  
  
## Syntaxe  
  
```  
template<typename Arg>  
    ref class modulus  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef Arg result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    modulus();  
    modulus(modulus<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### Paramètres  
 Arg  
 Type des arguments et valeur de retour.  
  
## Fonctions membres  
  
|Définition de type|Description|  
|------------------------|-----------------|  
|delegate\_type|Le type du délégué générique.|  
|first\_argument\_type|Le type du premier argument de foncteur|  
|result\_type|Le type du premier argument du résultat du foncteur.|  
|second\_argument\_type|Le type du deuxième argument de foncteur.|  
  
|Membre|Description|  
|------------|-----------------|  
|modulus|Construit le foncteur.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|operator\(\)|Calcule la fonction souhaitée.|  
|opérateur delegate\_type^|Convertit le foncteur en un délégué.|  
  
## Notes  
 La classe du modèle décrit un foncteur à deux arguments.  Elle définit l'opérateur membre `operator()` afin que, lorsque l'objet est appelé en tant que fonction, elle retourne le premier argument modulo le second.  
  
 Vous pouvez également transmettre l'objet comme argument de fonction dont le type est `delegate_type^` et il sera converti de façon appropriée.  
  
## Exemple  
  
```  
// cliext_modulus.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(2);   
    Myvector c2;   
    c2.push_back(3);   
    c2.push_back(1);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 2" and " 3 1"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::modulus<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 2**  
 **3 1**  
 **1 0**   
## Configuration requise  
 **En\-tête :** \<cliext\/functional\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [divides](../dotnet/divides-stl-clr.md)   
 [multiplies](../dotnet/multiplies-stl-clr.md)