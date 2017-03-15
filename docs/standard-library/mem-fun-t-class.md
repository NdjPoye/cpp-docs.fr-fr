---
title: mem_fun_t, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mem_fun_t
- xfunctional/std::mem_fun_t
- std::mem_fun_t
- std.mem_fun_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun_t class
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
caps.latest.revision: 19
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
ms.openlocfilehash: 0f30a83291abb804e10a6692bf0b0df54bcabc34
ms.lasthandoff: 02/24/2017

---
# <a name="memfunt-class"></a>mem_fun_t, classe
Classe d’adaptateur qui permet à une fonction membre **non_const** qui n’accepte aucun argument d’être appelée comme objet de fonction unaire en cas d’initialisation avec un argument de pointeur.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Result, class Type>
class mem_fun_t : public unary_function<Type *, Result> {
    explicit mem_fun_t(Result (Type::* _Pm)());

    Result operator()(Type* _Pleft) const;

 };
```  
  
#### <a name="parameters"></a>Paramètres  
 `_Pm`  
 Pointeur vers la fonction membre de la classe **Type** à convertir en objet de fonction.  
  
 `_Pleft`  
 Objet sur lequel la fonction membre `_Pm` est appelée.  
  
## <a name="return-value"></a>Valeur de retour  
 Fonction unaire adaptable.  
  
## <a name="remarks"></a>Notes  
 La classe de modèle stocke une copie de `_Pm`, qui doit être un pointeur vers une fonction membre de classe **Type**, dans un objet de membre privé. Elle définit sa fonction membre `operator()` comme retournant ( `_Pleft`->* `_Pm`)( ).  
  
## <a name="example"></a>Exemple  
 Le constructeur de `mem_fun_t` n’est généralement pas utilisé directement ; la fonction d’assistance `mem_fun` est utilisée pour adapter les fonctions membres. Pour obtenir un exemple d’utilisation des adaptateurs de fonction membre, consultez [mem_fun](../standard-library/functional-functions.md#mem_fun_function).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<functional>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [\<functional>](../standard-library/functional.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)




