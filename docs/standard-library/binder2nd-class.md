---
title: binder2nd, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xfunctional/std::binder2nd
dev_langs:
- C++
helpviewer_keywords:
- binder2nd class
ms.assetid: b2a9c1d1-dfc4-4ca9-a10e-ae84e195a62d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f635ee95b80c6ca8325248bc0161d359291ebe7
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="binder2nd-class"></a>binder2nd, classe
Classe de modèle fournissant un constructeur qui convertit un objet de fonction binaire en objet de fonction unaire en liant le second argument de la fonction binaire à une valeur spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Operation>
class binder2nd
    : public unaryFunction <typename Operation::first_argument_type,
    typename Operation::result_type>
{
public:
    typedef typename Operation::argument_type argument_type;
    typedef typename Operation::result_type result_type;
    binder2nd(
        const Operation& Func,
        const typename Operation::second_argument_type& right);

    result_type operator()(const argument_type& left) const;
    result_type operator()(argument_type& left) const;

protected:
    Operation op;
    typename Operation::second_argument_type value;
};
```  
  
#### <a name="parameters"></a>Paramètres  
 `Func`  
 Objet de fonction binaire à convertir en un objet de fonction unaire.  
  
 `right`  
 Valeur à laquelle le deuxième argument de l’objet de fonction binaire doit être lié.  
  
 `left`  
 Valeur de l’argument que l’objet binaire adapté compare à la valeur fixe du deuxième argument.  
  
## <a name="return-value"></a>Valeur de retour  
 Objet de fonction unaire qui résulte de la liaison du deuxième argument de l’objet de fonction binaire avec la valeur `right.`  
  
## <a name="remarks"></a>Notes  
 La classe de modèle stocke une copie d’un objet de fonction binaire _ *Func* dans **op** et une copie de `right` dans **value**. Elle définit sa fonction membre `operator()` comme retournant **op**( `left` **value**).  
  
 Si `Func` est un objet de type **Operation** et que c est une constante, [bind2nd](../standard-library/functional-functions.md#bind2nd) ( `Func`, `c` ) est équivalent au constructeur de classe `binder2nd` `binder2nd`\< **Operation**> ( `Func`, `c` ) et il est plus pratique.  
  
## <a name="example"></a>Exemple  
  
```cpp  
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
/* Output:  
The vector v1 = ( 0 5 10 15 20 25 )  
The number of elements in v1 greater than 10 is: 3.  
The number of elements in v1 less than 10 is: 2.  
*/  
```  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<functional>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)



