---
title: pointer_to_unary_function, classe| Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xfunctional/std::pointer_to_unary
- pointer_to_unary
dev_langs:
- C++
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
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
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 2089886ff915ce9176c883c9dc552f2a45b5c576
ms.contentlocale: fr-fr
ms.lasthandoff: 04/19/2017

---
# <a name="pointertounaryfunction-class"></a>pointer_to_unary_function, classe
Convertit un pointeur de fonction unaire en fonction unaire adaptable.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Arg, class Result>
class pointer_to_unary_function
    : public unary_function<Arg, Result>
{
public:
    explicit pointer_to_unary_function(Result(*pfunc)(Arg));
    Result operator()(Arg left) const;
};
```  
  
#### <a name="parameters"></a>Paramètres  
 `pfunc`  
 Fonction binaire à convertir.  
  
 `left`  
 Objet sur lequel la fonction *\*pfunc* est appelée.  
  
## <a name="return-value"></a>Valeur de retour  
 La classe de modèle stocke une copie de **pfunc**. Elle définit sa fonction membre `operator()` comme retournant (\* **pfunc**)(_ *Left*).  
  
## <a name="remarks"></a>Notes  
 Un pointeur de fonction unaire est un objet de fonction. Il peut être passé à n’importe quel algorithme de la bibliothèque standard C++ qui attend une fonction unaire comme paramètre, mais il n’est pas adaptable. Pour utiliser ce pointeur avec un adaptateur, en le liant à une valeur ou en l’utilisant avec une négation, vous devez également fournir les types imbriqués **argument_type** et **result_type** pour rendre l’adaptation possible. Grâce à la conversion par `pointer_to_unary_function`, les pointeurs de fonction binaire peuvent utiliser les adaptateurs de fonction.  
  
## <a name="example"></a>Exemple  
 Le constructeur de `pointer_to_unary_function` est rarement utilisé directement. Consultez la fonction d’assistance [ptr_fun](../standard-library/functional-functions.md#ptr_fun) pour obtenir un exemple montrant comment déclarer et utiliser le prédicat de l’adaptateur `pointer_to_unary_function`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<functional>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Référence de bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)




