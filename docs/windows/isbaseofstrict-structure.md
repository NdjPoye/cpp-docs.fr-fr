---
title: IsBaseOfStrict (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: internal/Microsoft::WRL::Details::IsBaseOfStrict
dev_langs: C++
helpviewer_keywords: IsBaseOfStrict structure
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a8e40bec0f4dedf02aab14b2c8072ccc3e60bbb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict (structure)
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <  
   typename Base,  
   typename Derived  
>  
  
struct IsBaseOfStrict;  
template <  
   typename Base  
>  
struct IsBaseOfStrict<Base, Base>;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Base`  
 Type de base.  
  
 `Derived`  
 Le type dérivé.  
  
## <a name="remarks"></a>Notes  
 Teste si un type est la base d'un autre.  
  
 Le premier modèle teste si un type est dérivé d’un type de base, ce qui peut produire **true** ou **false**. Le deuxième modèle teste si un type est dérivé lui-même, ce qui entraîne toujours une valeur **false**.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constants"></a>Constantes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[IsBaseOfStrict::value, constante](../windows/isbaseofstrict-value-constant.md)|Indique si un type est la base d’un autre.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `IsBaseOfStrict`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** internal.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)