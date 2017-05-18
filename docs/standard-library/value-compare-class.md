---
title: value_compare, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- value_compare
dev_langs:
- C++
helpviewer_keywords:
- value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
caps.latest.revision: 20
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 646d30d5e85c985896ee0380cac9c1630cb2ffbf
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="valuecompare-class"></a>value_compare, classe
Fournit un objet de fonction qui peut comparer les éléments d’un hash_map en comparant les valeurs de leurs clés pour déterminer leur ordre relatif dans le hash_map.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class value_compare
 : std::public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(
    const value_type& left,
    const value_type& right) const
 {
    return (comp(left.first, right.first));

 }
protected:
    value_compare(const key_compare& c) : comp (c) { }
    key_compare comp;
};
```  
  
## <a name="remarks"></a>Notes  
 Le critère de comparaison fourni par value_compare entre des **value_types** d’éléments entiers contenus par un objet hash_map est induit à partir d’une comparaison entre les clés des éléments respectifs par la construction de classe auxiliaire. L’opérateur de fonction membre utilise l’objet **comp** de type `key_compare` stocké dans l’objet de fonction fourni par value_compare pour comparer les composants de clé de tri de deux éléments.  
  
 Pour les objets hash_set et hash_multiset, qui sont des conteneurs simples dans lesquels les valeurs de clé sont identiques aux valeurs d’élément, value_compare équivaut à `key_compare` ; pour les objets hash_map et hash_multimap, ce n’est pas le cas, car la valeur des éléments `pair` de type n’est pas identique à la valeur de la clé de l’élément.  
  
 Dans Visual C++ .NET 2003, les membres des fichiers d’en-tête [<hash_map>](../standard-library/hash-map.md) et [<hash_set>](../standard-library/hash-set.md) ne sont plus dans l’espace de noms std. Ils ont été transférés dans l’espace de noms stdext. Pour plus d’informations, consultez [stdext, espace de noms](../standard-library/stdext-namespace.md).  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple [hash_map::value_comp](../standard-library/hash-map-class.md#value_comp) qui illustre comment déclarer et utiliser value_compare.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<hash_map>  
  
 **Espace de noms :** stdext  
  
## <a name="see-also"></a>Voir aussi  
 [binary_function, struct](../standard-library/binary-function-struct.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)




