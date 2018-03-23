---
title: InterfaceTraits (Structure) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits
dev_langs:
- C++
helpviewer_keywords:
- InterfaceTraits structure
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4b4b219091393b1195b60ae78347f952c2c9d37a
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="interfacetraits-structure"></a>InterfaceTraits (structure)
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<  
   typename I0  
>  
struct __declspec(novtable) InterfaceTraits;  
template<typename CloakedType>  
struct __declspec(novtable) InterfaceTraits<CloakedIid<CloakedType>>;  
  
template<>  
struct __declspec(novtable) InterfaceTraits<Nil>;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `I0`  
 Le nom d’une interface.  
  
 `CloakedType`  
 RuntimeClass, Implements et ChainInterfaces, une interface qui ne sont pas dans la liste des prises en charge les ID d’interface.  
  
## <a name="remarks"></a>Notes  
 Caractéristiques communes implémente d’une interface.  
  
 Le deuxième modèle est une spécialisation pour les interfaces masqués. Le troisième modèle est une spécialisation pour les paramètres Nil.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`Base`|Synonyme du paramètre de modèle `I0`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[InterfaceTraits::CanCastTo, méthode](../windows/interfacetraits-cancastto-method.md)|Indique si le pointeur spécifié peut être converti en un pointeur vers `Base`.|  
|[InterfaceTraits::CastToBase, méthode](../windows/interfacetraits-casttobase-method.md)|Convertit le pointeur spécifié vers un pointeur vers `Base`.|  
|[InterfaceTraits::CastToUnknown, méthode](../windows/interfacetraits-casttounknown-method.md)|Convertit le pointeur spécifié vers un pointeur vers IUnknown.|  
|[InterfaceTraits::FillArrayWithIid, méthode](../windows/interfacetraits-fillarraywithiid-method.md)|Attribue l’ID de l’interface de `Base` à l’élément de tableau spécifié par l’argument d’index.|  
|[InterfaceTraits::Verify, méthode](../windows/interfacetraits-verify-method.md)|Vérifie qu’est correctement dérivé de Base.|  
  
### <a name="public-constants"></a>Constantes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[InterfaceTraits::IidCount, constante](../windows/interfacetraits-iidcount-constant.md)|Contient le nombre d’interface Qu'id associées à l’objet InterfaceTraits en cours.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `InterfaceTraits`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** implements.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)