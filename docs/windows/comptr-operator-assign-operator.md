---
title: "ComPtr::operator =, opérateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 1a0c2752-f7d8-4819-9443-07b88b69ef02
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 30f04bdfe7b508bf83e34992fefdcb10c58b4655
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="comptroperator-operator"></a>ComPtr::operator=, opérateur
Assigne une valeur au ComPtr actuel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
WRL_NOTHROW ComPtr& operator=(  
   decltype(__nullptr)  
);  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ T *other  
);  
template <  
   typename U  
>  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr &other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr<U>& other  
);  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr &&other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr<U>&& other  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `U`  
 Une classe.  
  
 `other`  
 Une référence de pointeur, référence ou rvalue à un type ou un autre ComPtr.  
  
## <a name="return-value"></a>Valeur de retour  
 Une référence au ComPtr actuel.  
  
## <a name="remarks"></a>Notes  
 La première version de cet opérateur assigne une valeur vide pour le ComPtr actuel.  
  
 Dans la deuxième version, si le pointeur d’interface affectation n’est pas le même que le pointeur d’interface ComPtr actuel, le second pointeur d’interface est attribué au ComPtr actuel.  
  
 Dans la troisième version, le pointeur d’interface affectation est assigné au ComPtr actuel.  
  
 Dans la quatrième version, si le pointeur d’interface de la valeur d’assignation n’est pas le même que le pointeur d’interface ComPtr actuel, le second pointeur d’interface est attribué au ComPtr actuel.  
  
 La cinquième version est un opérateur de copie ; une référence à un ComPtr est assignée au ComPtr actuel.  
  
 La sixième version est un opérateur de copie qui utilise la sémantique ; de déplacement une référence rvalue à un ComPtr si n’importe quel type est statique effectué, puis affecté au ComPtr actuel.  
  
 La septième version est un opérateur de copie qui utilise la sémantique ; de déplacement une référence rvalue à un ComPtr de type `U` est statique effectué puis et affecté au ComPtr actuel.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)