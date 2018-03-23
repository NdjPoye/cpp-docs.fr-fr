---
title: Interfacetraits::casttounknown, méthode | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: aca47fa0-3c60-47f2-a73c-258f7160adff
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0c02a79a5b4d8674317c97624bf77cce9b653808
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="interfacetraitscasttounknown-method"></a>InterfaceTraits::CastToUnknown, méthode
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<typename T>  
static __forceinline IUnknown* CastToUnknown(  
   _In_ T* ptr  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de paramètre `ptr`.  
  
 `ptr`  
 Pointeur vers le type `T`.  
  
## <a name="return-value"></a>Valeur de retour  
 Pointeur vers IUnknown à partir de laquelle `Base` est dérivée.  
  
## <a name="remarks"></a>Notes  
 Convertit le pointeur spécifié vers un pointeur vers IUnknown.  
  
 Pour plus d’informations sur `Base`, consultez la section Typedefs publics dans [interfacetraits, Structure](../windows/interfacetraits-structure.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** implements.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [InterfaceTraits (Structure)](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)