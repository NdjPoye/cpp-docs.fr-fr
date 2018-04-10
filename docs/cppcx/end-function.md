---
title: End (fonction) | Documents Microsoft
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::end
dev_langs:
- C++
helpviewer_keywords:
- end Function
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
caps.latest.revision: 4
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 264ffdad3d55ae9d2df44646240d42ac02d5fcb1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="end-function"></a>end (fonction)
Retourne un itérateur qui pointe au-delà de la fin d'une collection accessible par le paramètre d'interface spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
template <typename T>  
    ::Platform::Collections::VectorIterator<T>   
    end(  
        IVector<T>^ v       );  
  
template <typename T>  
    ::Platform::Collections::VectorViewIterator<T>   
    end(  
        IVectorView<T>^ v  
       );  
template <typename T>   
    ::Platform::Collections::InputIterator<T>   
    end(  
        IIterable<T>^ i  
       );  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Paramètre de type de modèle.  
  
 `v`  
 Une collection de vecteur\<T > ou VectorView\<T > objets accessibles par un IVector\<T >, ou IVectorView\<T > interface.  
  
 `i`  
 Collection d’arbitraires Windows Runtime objets accessibles par une IIterable\<T > interface.  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur qui pointe au-delà de la fin de la collection.  
  
### <a name="remarks"></a>Notes  
 Les deux premières fonctions de modèle retournent des itérateurs et la troisième fonction de modèle retourne un itérateur d'entrée.  
  
 L'objet [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) retourné par `end` est un itérateur de proxy qui stocke des éléments de type `VectorProxy<T>`. Toutefois, l'objet proxy n'est presque jamais visible par le code utilisateur. Pour plus d'informations, consultez [Collections (C++/CX)](../cppcx/collections-c-cx.md).  
  
### <a name="requirements"></a>Configuration requise  
 **En-tête :** collection.h  
  
 **Espace de noms :** Windows::Foundation::Collections  
  
## <a name="see-also"></a>Voir aussi  
 [Windows::Foundation :: Collections Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)