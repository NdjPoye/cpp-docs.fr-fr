---
title: Begin (fonction) | Documents Microsoft
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::begin
dev_langs:
- C++
helpviewer_keywords:
- begin Function
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d47244e6428979f5319c9ee02f252ef3e559f7ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="begin-function"></a>begin (fonction)
Retourne un itérateur qui pointe vers le début d’une collection accessible par le paramètre d’interface spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
template <typename T>   
    ::Platform::Collections::VectorIterator<T>   
    begin(  
          IVector<T>^ v         );  
  
template <typename T>   
    ::Platform::Collections::VectorViewIterator<T>   
    begin(  
          IVectorView<T>^ v  
         );   
  
template <typename T>   
    ::Platform::Collections::InputIterator<T>   
    begin(  
          IIterable<T>^ i         );  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Paramètre de type de modèle.  
  
 `v`  
 Une collection de vecteur\<T > ou VectorView\<T > objets accessibles par un IVector\<T > ou IVectorView\<T > interface.  
  
 `i`  
 Une collection d’objets Windows Runtime arbitraires accessibles par une IIterable\<T > interface.  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur qui pointe vers le début de la collection.  
  
### <a name="remarks"></a>Notes  
 Les deux premières fonctions de modèle retournent des itérateurs et la troisième fonction de modèle retourne un itérateur d'entrée.  
  
 L’objet VectorIterator retourné par begin est un itérateur de proxy qui stocke des éléments de type VectorProxy\<T >. Toutefois, l’objet proxy n’est presque jamais visible par le code utilisateur. Pour plus d'informations, consultez [Collections (C++/CX)](../cppcx/collections-c-cx.md).  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** collection.h  
  
 **Espace de noms :** Windows::Foundation::Collections  
  
## <a name="see-also"></a>Voir aussi  
 [Windows::Foundation :: Collections Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)