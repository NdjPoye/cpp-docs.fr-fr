---
title: reference_wrapper, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- reference_wrapper
- std::reference_wrapper
- functional/std::reference_wrapper
- type_traits/std::reference_wrapper
- xrefwrap/std::reference_wrapper
- type_traits/std::reference_wrapper::get
- type_traits/std::reference_wrapper::operator()
dev_langs:
- C++
helpviewer_keywords:
- reference_wrapper class
- reference_wrapper
ms.assetid: 90b8ed62-e6f1-44ed-acc7-9619bd58865a
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: f0e7b22e4fbd6f54d390adfe70f7bfb99e4bc5df
ms.openlocfilehash: 1b6968f2300e5214575cc5385c136d6f27bab10a
ms.lasthandoff: 02/24/2017

---
# <a name="referencewrapper-class"></a>reference_wrapper, classe
Encapsule une référence.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Ty>  
class reference_wrapper  
{  
public:  
    typedef Ty type;  
 
    reference_wrapper(Ty&) noexcept;
    operator Ty&() const noexcept;
    Ty& get() const noexcept;

    template <class... Types> 
    auto operator()(Types&&... args) const ->
        decltype(std::invoke(get(), std::forward<Types>(args)...));
 
private:  
    Ty *ptr; // exposition only  
};  
```  
  
## <a name="remarks"></a>Notes  
Un `reference_wrapper<Ty>` est un wrapper constructible par copie et assignable par copie autour d’une référence à un objet ou une fonction de type `Ty`. Il contient un pointeur vers un objet de ce type. Un `reference_wrapper` peut être utilisé pour stocker des références dans des conteneurs standard et passer des objets par référence à `std::bind`.  
  
Le type `Ty` doit être un type d’objet ou un type de fonction. Sinon, une assertion statique échoue au moment de la compilation.  
  
Les fonctions d’assistance [std::ref](functional-functions.md#ref_function) et [std::cref](functional-functions.md#cref_function) peuvent être utilisées pour créer des objets `reference_wrapper`.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[reference_wrapper::reference_wrapper](#reference_wrapper)|Construit un objet `reference_wrapper`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[reference_wrapper::result_type](#result_type)|Type de résultat faible de la référence encapsulée.|  
|[reference_wrapper::type](#type)|Type de la référence encapsulée.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[reference_wrapper::get](#get)|Obtient la référence encapsulée.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[reference_wrapper::operator Ty&amp;](#operator_ty_amp_)|Obtient un pointeur vers la référence encapsulée.|  
|[reference_wrapper::operator()](#operator_call)|Appelle la référence encapsulée.|  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<functional>  
  
 **Espace de noms :** std  
  
##  <a name="a-namegeta--referencewrapperget"></a><a name="get"></a>  reference_wrapper::get  
 Obtient la référence encapsulée.  
  
```  
Ty& get() const noexcept;
```  
  
### <a name="remarks"></a>Notes  
La fonction membre retourne la référence incluse dans un wrapper.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__functional__reference_wrapper_get.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << rwi << std::endl;   
    rwi.get() = -1;   
    std::cout << "i = " << i << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
i = -1  
```  
  
##  <a name="a-nameoperatortyampa--referencewrapperoperator-tyamp"></a><a name="operator_ty_amp_"></a>  reference_wrapper::operator Ty&amp;  
 Obtient la référence incluse dans un wrapper.  
  
```  
operator Ty&() const noexcept;
```  
  
### <a name="remarks"></a>Notes  
 L’opérateur membre retourne `*ptr`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__functional__reference_wrapper_operator_cast.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "(int)rwi = " << (int)rwi << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
(int)rwi = 1  
```  
  
##  <a name="a-nameoperatorcalla--referencewrapperoperator"></a><a name="operator_call"></a>  reference_wrapper::operator()  
 Appelle la référence encapsulée.  
  
```  
template <class... Types>  
auto operator()(Types&&... args);
```  
  
### <a name="parameters"></a>Paramètres  
 `Types`  
 Types de la liste d’arguments.  
  
 `args`  
 Liste d’arguments.  
  
### <a name="remarks"></a>Notes  
 Le membre de modèle `operator()` retourne `std::invoke(get(), std::forward<Types>(args)...)`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__functional__reference_wrapper_operator_call.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    std::reference_wrapper<int (int)> rwi(neg);   
  
    std::cout << "rwi(3) = " << rwi(3) << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
rwi(3) = -3  
```  
  
##  <a name="a-namereferencewrappera--referencewrapperreferencewrapper"></a><a name="reference_wrapper"></a>  reference_wrapper::reference_wrapper  
 Construit un objet `reference_wrapper`.  
  
```  
reference_wrapper(Ty& val) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Ty`  
 Type à inclure dans un wrapper.  
  
 `val`  
 Valeur à inclure dans un wrapper.  
  
### <a name="remarks"></a>Notes  
 Le constructeur définit la valeur stockée `ptr` à `&val`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__functional__reference_wrapper_reference_wrapper.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << rwi << std::endl;   
    rwi.get() = -1;   
    std::cout << "i = " << i << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
i = -1  
```  
  
##  <a name="a-nameresulttypea--referencewrapperresulttype"></a><a name="result_type"></a>  reference_wrapper::result_type  
 Type de résultat faible de la référence encapsulée.  
  
```  
typedef R result_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le typedef `result_type` est un synonyme pour le type de résultat faible d’une fonction incluse dans un wrapper. Ce typedef est significatif uniquement pour les types de fonction.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__functional__reference_wrapper_result_type.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    typedef std::reference_wrapper<int (int)> Mywrapper;   
    Mywrapper rwi(neg);   
    Mywrapper::result_type val = rwi(3);   
  
    std::cout << "val = " << val << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
val = -3  
```  
  
##  <a name="a-nametypea--referencewrappertype"></a><a name="type"></a>  reference_wrapper::type  
 Type de la référence encapsulée.  
  
```  
typedef Ty type;  
```  
  
### <a name="remarks"></a>Notes  
 Le typedef est un synonyme de l'argument de modèle `Ty`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__functional__reference_wrapper_type.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    int i = 1;   
    typedef std::reference_wrapper<int> Mywrapper;   
    Mywrapper rwi(i);   
    Mywrapper::type val = rwi.get();   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << val << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
```  
  
## <a name="see-also"></a>Voir aussi  
 [cref, fonction](../standard-library/functional-functions.md#cref_function)   
 [ref, fonction](../standard-library/functional-functions.md#ref_function)


