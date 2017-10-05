---
title: slice_array, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- valarray/std::slice_array
dev_langs:
- C++
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 12c40729fa9a848a87f37283277e88392fb04614
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="slicearray-class"></a>slice_array, classe
Classe de modèle interne auxiliaire qui prend en charge les objets de secteurs en fournissant des opérations entre des tableaux de sous-ensembles définis par le secteur d'un valarray.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Type>  
class slice_array : public slice {  
public:  
    typedef Type value_type;  
    void operator=(const valarray<Type>& x) const;

 
    void operator=(const Type& x) const;

 
    void operator*=(const valarray<Type>& x) const;

 
    void operator/=(const valarray<Type>& x) const;

 
    void operator%=(const valarray<Type>& x) const;

 
    void operator+=(const valarray<Type>& x) const;

 
    void operator-=(const valarray<Type>& x) const;

 
    void operator^=(const valarray<Type>& x) const;

 
    void operator&=(const valarray<Type>& x) const;

 
    void operator|=(const valarray<Type>& x) const;

 
    void operator<<=(const valarray<Type>& x) const;

 
    void operator>>=(const valarray<Type>& x) const;

 
// The rest is private or implementation defined  
}  
```  
  
## <a name="remarks"></a>Notes  
 La classe décrit un objet qui stocke une référence à un objet de la classe [valarray](../standard-library/valarray-class.md)**\<Type>**, ainsi qu’un objet de la classe [slice](../standard-library/slice-class.md), qui décrit la séquence d’éléments à sélectionner à partir de l’objet **valarray\<Type>**.  
  
 La classe de modèle est créée indirectement par certaines opérations valarray. Elle ne peut pas être utilisée directement dans le programme. Classe de modèle interne auxiliaire qui est utilisée par l’opérateur slice subscript :  
  
 `slice_array`\< **Type**> `valarray`< **Type**:: `operator[]` ( `slice`).  
  
 Vous construisez un objet **slice_array\<Type>** uniquement en écrivant une expression sous la forme [va&#91;sl&#93;](../standard-library/valarray-class.md#op_at), pour une section **sl** du valarray **va**. Les fonctions membres de la classe slice_array se comportent ensuite comme les signatures de fonctions correspondantes définies pour **valarray\<Type>**, sauf que seule la séquence d’éléments sélectionnée est affectée. La séquence contrôlée par le slice_array est définie par les trois paramètres du constructeur slice, l’index du premier élément dans la section (slice), le nombre d’éléments et la distance entre les éléments. Un slice_array coupé du valarray **va** déclaré par **va**[ `slice`(2, 5, 3)] sélectionne les éléments ayant les index 2, 5, 8, 11 et 14 dans **va**. Les index doivent être valides pour que la procédure soit valide.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple [slice::slice](../standard-library/slice-class.md#slice) pour savoir comment déclarer et utiliser un slice_array.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<valarray>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


