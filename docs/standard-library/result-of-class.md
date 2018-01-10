---
title: result_of, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
dev_langs: C++
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 256f24ad40234db2bbc191a50b0d7e05de39c073
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="resultof-class"></a>result_of, classe
Détermine le type de retour du type pouvant être appelé qui accepte les types d’argument spécifiés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<class>  
struct result_of; // Causes a static assert  
  
template <class Fn, class... ArgTypes>  
struct result_of<Fn(ArgTypes...)>;

// Helper type  
template<class T>
   using result_of_t = typename result_of<T>::type;
```  
  
#### <a name="parameters"></a>Paramètres  
 `Fn`  
 Type pouvant être appelé à interroger.  
  
 `ArgTypes`  
 Types de la liste d’arguments pour le type pouvant être appelé à interroger.  
  
## <a name="remarks"></a>Notes  
 Utilisez ce modèle pour déterminer, au moment de la compilation, le type de résultat de `Fn`(`ArgTypes`), où `Fn` est un type pouvant être appelé, une référence à une fonction ou une référence au type pouvant être appelé, à l’aide d’une liste d’arguments des types fournis dans `ArgTypes`. Le membre `type` de la classe de modèle désigne le type de résultat de `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))` si l’expression non évaluée `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` est bien formée. Sinon, la classe de modèle n’a aucun membre `type`. Le type `Fn` et tous les types dans le package de paramètres `ArgTypes` doivent être des types complets, `void` ou des tableaux de limite inconnue.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)



