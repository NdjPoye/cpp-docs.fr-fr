---
title: hash, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hash
- functional/std::hash
- bitset/std::hash
- memory/std::hash
- string/std::hash
- system_error/std::hash
- thread/std::hash
- typeindex/std::hash
- vector/std::hash
- XSTDDEF/std::hash
- xstring/std::hash
dev_langs:
- C++
helpviewer_keywords:
- hash class
ms.assetid: e1b500c6-a5c8-4f6f-ad33-7ec52eb8e2e4
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 28baed4badda4f2c1d7e5b20235fe8d40c2a7195
ms.openlocfilehash: d549fb7aeed268327122532e6c4390ac931740e7
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="hash-class"></a>hash, classe
Calcule le code de hachage pour une valeur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Ty>  
struct hash {  
    size_t operator()(Ty val) const; 
};  
```  
  
## <a name="remarks"></a>Notes  
L’objet de fonction définit une fonction de hachage appropriée pour mapper des valeurs de type *Ty* à une distribution de valeurs d’index. Le membre `operator()` retourne un code de hachage pour *val*, pouvant être utilisé avec les classes de modèle `unordered_map`, `unordered_multimap`, `unordered_set` et `unordered_multiset`. La bibliothèque standard fournit des spécialisations de types de base : *Ty* peut être tout type scalaire, notamment les types pointeur et les types énumération. De plus, il existe des spécialisations pour les types de bibliothèque `string`, `wstring`, `u16string`, `u32string`, `string_view`, `wstring_view`, `u16string_view`, `u32string_view`, `bitset`, `error_code`, `error_condition`, `optional`, `shared_ptr`, `thread`, `type_index`, `unique_ptr`, `variant` et `vector<bool>`.  
  
## <a name="example"></a>Exemple  
  
```cpp  
// std__functional__hash.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
#include <unordered_set>   
  
int main()   
    {   
    std::unordered_set<int, std::hash<int> > c0;   
    c0.insert(3);   
    std::cout << *c0.find(3) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
3  
```  
  
## <a name="requirements"></a>Spécifications  
**En-tête :** \<functional>  
  
**Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<unordered_map>](../standard-library/unordered-map.md)   
 [unordered_multimap, classe](../standard-library/unordered-multimap-class.md)   
 [unordered_multiset, classe](../standard-library/unordered-multiset-class.md)   
 [<unordered_set>](../standard-library/unordered-set.md)


