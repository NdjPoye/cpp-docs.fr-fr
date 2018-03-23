---
title: Makeallocator, classe | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
dev_langs:
- C++
helpviewer_keywords:
- MakeAllocator class
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 33ba172099fd2554709cc539eeee8999c0e42cef
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="makeallocator-class"></a>MakeAllocator (classe)
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
template<  
   typename T,  
   bool hasWeakReferenceSupport =   
         !__is_base_of(RuntimeClassFlags<InhibitWeakReference>, T)>
 class MakeAllocator;  
  
template<typename T>  
class MakeAllocator<T, false>;  
  
template<typename T>  
class MakeAllocator<T, true>;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Un nom de type.  
  
 `hasWeakReferenceSupport`  
 `true` allocation de mémoire pour un objet qui prend en charge les références faibles ; `false` pour allouer de la mémoire pour un objet qui ne prend pas en charge les références faibles.  
  
## <a name="remarks"></a>Notes  
 Alloue la mémoire pour une classe activable, avec ou sans prise en charge de la référence faible.  
  
 Substituez la classe MakeAllocator pour implémenter un modèle d’allocation de mémoire défini par l’utilisateur.  
  
 MakeAllocator est généralement utilisé pour éviter les fuites de mémoire si un objet lève pendant la construction.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[MakeAllocator::MakeAllocator, constructeur](../windows/makeallocator-makeallocator-constructor.md)|Initialise une nouvelle instance de la classe MakeAllocator.|  
|[MakeAllocator::~MakeAllocator, destructeur](../windows/makeallocator-tilde-makeallocator-destructor.md)|Désinitialise l’instance actuelle de la classe MakeAllocator.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[MakeAllocator::Allocate, méthode](../windows/makeallocator-allocate-method.md)|Alloue de la mémoire et l’associe à l’objet MakeAllocator en cours.|  
|[MakeAllocator::Detach, méthode](../windows/makeallocator-detach-method.md)|Dissocie la mémoire allouée par le [Allocate](../windows/makeallocator-allocate-method.md) méthode à partir de l’objet MakeAllocator en cours.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `MakeAllocator`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** implements.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)