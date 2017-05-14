---
title: const_mem_fun1_ref_t, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xfunctional/std::const_mem_fun1_ref_t
- const_mem_fun1_ref_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun1_ref_t class
ms.assetid: 8220d373-fa1c-44be-a21d-96d49b3ea6bb
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
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: d66879ccf3c8fdf572b3f636706b0128a489df5c
ms.contentlocale: fr-fr
ms.lasthandoff: 04/19/2017

---
# <a name="constmemfun1reft-class"></a>const_mem_fun1_ref_t, classe
Classe d’adaptateur qui permet à une fonction membre **const** qui accepte un seul argument d’être appelée comme objet de fonction binaire en cas d’initialisation avec un argument de référence.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Result, class Type, class Arg>
class const_mem_fun1_ref_t
 : public binary_function<Type, Arg, Result> 
 {
    explicit const_mem_fun1_ref_t(Result (Type::* Pm)(Arg) const);
    Result operator()(const Type& left, Arg right) const;
 };
```  
  
#### <a name="parameters"></a>Paramètres  
 `Pm`  
 Pointeur vers la fonction membre de la classe **Type** à convertir en objet de fonction.  
  
 `left`  
 Objet **const** sur lequel la fonction membre `Pm` est appelée.  
  
 `right`  
 Argument donné à `Pm`.  
  
## <a name="return-value"></a>Valeur de retour  
 Fonction binaire adaptable.  
  
## <a name="remarks"></a>Notes  
 La classe de modèle stocke une copie de `Pm`, qui doit être un pointeur vers une fonction membre de la classe **Type**, dans un objet de membre privé. Elle définit sa fonction membre `operator()` comme retournant ( `left`.\* *Pm*)( `right`) **const**.  
  
## <a name="example"></a>Exemple  
 Le constructeur de `const_mem_fun1_ref_t` n’est généralement pas utilisé directement ; la fonction d’assistance `mem_fun_ref` est utilisée pour adapter les fonctions membres. Pour obtenir des exemples d’utilisation des adaptateurs de fonction membre, consultez [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<functional>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)




