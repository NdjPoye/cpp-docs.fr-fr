---
title: "binder1st, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xfunctional/std::binder1st"
  - "std::binder1st"
  - "binder1st"
  - "std.binder1st"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binder1st (classe)"
ms.assetid: 6b8ee343-c82f-48f8-867d-06f9d1d324c0
caps.latest.revision: 22
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# binder1st, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe de modèle fournissant un constructeur qui convertit un objet fonction binaire en un objet fonction unaire en liant le premier argument de la fonction binaire à une valeur spécifiée.  
  
## Syntaxe  
  
```  
template<class Operation>  
class binder1st  
   : public unary_function <  
      typename Operation::second_argument_type,  
      typename Operation::result_type>   
  {  
   public:  
   typedef typename Operation::argument_type argument_type;  
   typedef typename Operation::result_type result_type;  
   binder1st(  
      const Operation & _Func,  
      const typename Operation::first_argument_type& _Left  
   );  
   result_type operator()(  
      const argument_type& _Right  
   ) const;  
   result_type operator()(  
      const argument_type& _Right  
   ) const;  
   protected:  
   Operation op;  
   typename Operation::first_argument_type value;  
   };  
```  
  
#### Paramètres  
 `_Func`  
 L'objet de la fonction binaire à convertir en un objet de fonction unaire.  
  
 `_Left`  
 La valeur à laquelle le premier argument de l'objet de la fonction binaire doit être lié.  
  
 `_Right`  
 La valeur de l'argument que l'objet binaire approprié compare à la valeur fixe du second argument.  
  
## Valeur de retour  
 L'objet de la fonction unaire qui résulte de la liaison le premier argument de l'objet de fonction binaire à la valeur `_Left.`  
  
## Notes  
 La classe de modèle stocke une copie d'un objet binaire `_Func` de fonction dans **op**, et une copie d'`_Left` dans **valeur**.  Cette option définit la fonction membre `operator()` comme retourner **op**\(**valeur**, `_Right`\).  
  
 Si `_Func` est un objet de type **Opération** et `c` constante, puis [bind1st](../Topic/bind1st%20Function.md) \( `_Func`, `c` \) est équivalent au constructeur `binder1st`\<**Opération**\> \( `_Func`, `c` \) de la classe d'`binder1st` et plus pratique.  
  
## Exemple  
  
```  
// functional_binder1st.cpp  
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
        binder1st<less<int> >(less<int>(), 10));  
    cout << "The number of elements in v1 greater than 10 is: "  
         << result1 << "." << endl;  
  
    // Compare use of binder2nd fixing 2nd argument:  
    // count the number of integers < 10 in the vector  
    vector<int>::iterator::difference_type result2;  
    result2 = count_if(v1.begin(), v1.end(),  
        binder2nd<less<int> >(less<int>(), 10));  
    cout << "The number of elements in v1 less than 10 is: "  
         << result2 << "." << endl;  
}  
```  
  
  **Le vecteur v1 \= \(0 5 10 15 20 25\)**  
**Le nombre d'éléments dans v1 plus grand que 10 est : 3.**  
**Le nombre d'éléments dans v1 inférieur à 10 est: 2.**   
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)