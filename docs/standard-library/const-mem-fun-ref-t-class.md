---
title: const_mem_fun_ref_t, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::const_mem_fun_ref_t
- const_mem_fun_ref_t
- std.const_mem_fun_ref_t
- xfunctional/std::const_mem_fun_ref_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun_ref_t class
ms.assetid: 316ddbaa-9f46-4931-8eba-ea4ca66360ef
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
translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: cb5fd219cb69b7cd6edd2d5eb5b9abd0ab819369
ms.lasthandoff: 02/24/2017

---
# <a name="constmemfunreft-class"></a>const_mem_fun_ref_t, classe
Classe d’adaptateur qui permet à une fonction membre **const** qui n’accepte aucun argument d’être appelée comme objet de fonction unaire en cas d’initialisation avec un argument de référence.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Result, class Type>
class const_mem_fun_ref_t
 : public unary_function<Type, Result>  
{
    explicit const_mem_fun_t(Result (Type::* Pm)() const);
    Result operator()(const Type& left) const;
 };
```  
  
#### <a name="parameters"></a>Paramètres  
 `Pm`  
 Pointeur vers la fonction membre de la classe **Type** à convertir en objet de fonction.  
  
 `left`  
 Objet sur lequel la fonction membre `Pm` est appelée.  
  
## <a name="return-value"></a>Valeur de retour  
 Fonction unaire adaptable.  
  
## <a name="remarks"></a>Notes  
 La classe de modèle stocke une copie de `Pm`, qui doit être un pointeur vers une fonction membre de la classe **Type**, dans un objet de membre privé. Elle définit sa fonction membre `operator()` comme retournant ( **left**.\* `Pm`)() **const**.  
  
## <a name="example"></a>Exemple  
 Le constructeur de `const_mem_fun_ref_t` n’est généralement pas utilisé directement ; la fonction d’assistance `mem_fun_ref` est utilisée pour adapter les fonctions membres. Pour obtenir un exemple d’utilisation des adaptateurs de fonction membre, consultez [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref_function).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<functional>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)




