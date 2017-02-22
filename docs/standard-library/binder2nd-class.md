---
title: "binder2nd, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.binder2nd"
  - "binder2nd"
  - "xfunctional/std::binder2nd"
  - "std::binder2nd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binder2nd (classe)"
ms.assetid: b2a9c1d1-dfc4-4ca9-a10e-ae84e195a62d
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# binder2nd, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe de modèle fournissant un constructeur qui convertit un objet fonction binaire en un objet fonction unaire en liant le second argument de la fonction binaire à une valeur spécifiée.  
  
## Syntaxe  
  
```  
template<class Operation>  
   class binder2nd  
      : public unary_function <  
         typename Operation::first_argument_type,  
         typename Operation::result_type>   
   {  
   public:  
   typedef typename Operation::argument_type argument_type;  
   typedef typename Operation::result_type result_type;  
   binder2nd(  
      const Operation& _Func,  
      const typename Operation::second_argument_type& _Right  
   );  
   result_type operator()(  
      const argument_type& _Left  
   ) const;  
   result_type operator()(  
      argument_type& _Left  
   ) const;  
   protected:  
   Operation op;  
   typename Operation::second_argument_type value;  
   };  
```  
  
#### Paramètres  
 `_Func`  
 L'objet binaire de la fonction à convertir en un objet unaire de fonction.  
  
 `_Right`  
 La nouvelle valeur du second argument de l'objet binaire de la fonction doit être lié.  
  
 `_Left`  
 La valeur de l'argument de l'objet binaire approprié compare à la valeur fixe du second argument.  
  
## Valeur de retour  
 L'objet unaire de la fonction de résultats de la liaison le deuxième argument de l'objet binaire de fonction à la valeur `_Right.`  
  
## Notes  
 La classe de modèle stocke une copie d'un \_Func binaire de fonction dans **op**, et une copie d'`_Right` dans **valeur**.  Cette option définit la fonction membre `operator()` comme retourner **op**\(`_Left`, **valeur**\).  
  
 Si `_Func` est un objet de type **Opération** et c'est une constante, une [bind2nd](../Topic/bind2nd%20Function.md) \( `_Func`, `c` \) est équivalent au constructeur `binder2nd`\<**Opération**\> \( `_Func`, `c` \) de la classe d'`binder2nd` et plus pratique.  
  
## Exemple  
  
```  
// functional_binder2nd.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main()  
{  
    vector<int> v1;  
    vector<int>::iterator Iter;  
  
    int i;  
    for (i = 0; i <= 5; i++)  
    {  
        v1.push_back(5 * i);  
    }  
  
    cout << "The vector v1 = ( ";  
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)  
        cout << *Iter << " ";  
    cout << ")" << endl;  
  
    // Count the number of integers > 10 in the vector  
    vector<int>::iterator::difference_type result1;  
    result1 = count_if(v1.begin(), v1.end(),  
        binder2nd<greater<int> >(greater<int>(), 10));  
    cout << "The number of elements in v1 greater than 10 is: "  
         << result1 << "." << endl;  
  
    // Compare using binder1st fixing 1st argument:  
    // count the number of integers < 10 in the vector  
    vector<int>::iterator::difference_type result2;  
    result2 = count_if(v1.begin(), v1.end(),  
        binder1st<greater<int> >(greater<int>(), 10));  
    cout << "The number of elements in v1 less than 10 is: "  
         << result2 << "." << endl;  
}  
```  
  
  **Le vecteur v1 \= \(0 5 10 15 20 25\)**  
**Nombre d'éléments dans v1 supérieur à 10 est : 3.**  
**Nombre d'éléments dans v1 moins de 10 est : 2.**   
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)