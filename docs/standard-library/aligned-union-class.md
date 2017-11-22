---
title: aligned_union, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::aligned_union
dev_langs: C++
helpviewer_keywords: aligned_union
ms.assetid: 9931a44d-3a67-4f29-a0f6-d47a7cf560ac
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5b85dac1c4abccd15dbf4755026a1288a2c4ee1e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="alignedunion-class"></a>aligned_union, classe
Fournit un type POD suffisamment grand et convenablement aligné pour stocker un type union et la taille nécessaire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <std::size_t Len, class... Types>  
struct aligned_union;  
 
template <std::size_t Len, class... Types>  
using aligned_union_t = typename aligned_union<Len, Types...>::type;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Len`  
 Valeur d'alignement pour le plus grand type dans l'union.  
  
 `Types`  
 Types distincts dans l'union sous-jacente.  
  
## <a name="remarks"></a>Notes  
 Utilisez la classe de modèle pour obtenir l’alignement et la taille nécessaires pour stocker une union dans un stockage non initialisé. Le typedef de membre `type` nomme un type POD adapté au stockage de tout type répertorié dans `Types`. La taille minimale est `Len`. Le membre statique `alignment_value` de type `std::size_t` contient l’alignement le plus strict nécessaire de tous les types répertoriés dans `Types`.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser `aligned_union` pour allouer une mémoire tampon de pile alignée afin de placer une union.  
  
```  
// std__type_traits__aligned_union.cpp  
#include <iostream>  
#include <type_traits>  
  
union U_type  
{  
    int i;  
    float f;  
    double d;  
    U_type(float e) : f(e) {}  
};  
  
typedef std::aligned_union<16, int, float, double>::type aligned_U_type;  
  
int main()  
{  
    // allocate memory for a U_type aligned on a 16-byte boundary  
    aligned_U_type au;  
    // do placement new in the aligned memory on the stack  
    U_type* u = new (&au) U_type(1.0f);  
    if (nullptr != u)  
    {  
        std::cout << "value of u->i is " << u->i << std::endl;  
        // must clean up placement objects manually!  
        u->~U_type();  
    }  
}  
```  
  
```Output  
value of u->i is 1065353216  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)   
 [alignment_of, classe](../standard-library/alignment-of-class.md)