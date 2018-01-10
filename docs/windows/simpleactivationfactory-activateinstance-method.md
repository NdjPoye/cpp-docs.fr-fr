---
title: "Simpleactivationfactory::activateinstance, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
dev_langs: C++
helpviewer_keywords: ActivateInstance method
ms.assetid: 4f836e51-5a6c-4bad-b871-9f25199298b4
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6bbe9d8c215674f087c6e0fa4ca7f3439fb89b78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="simpleactivationfactoryactivateinstance-method"></a>SimpleActivationFactory::ActivateInstance, méthode

Crée une instance de l’interface spécifiée.

## <a name="syntax"></a>Syntaxe

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>Paramètres

*ppvObject*  
Lorsque cette opération se termine, pointeur vers une instance de l’objet spécifié par le `Base` paramètre de modèle de classe.

## <a name="return-value"></a>Valeur de retour

S_OK si l'opération réussit. Sinon, une valeur HRESULT indique l'erreur.

## <a name="remarks"></a>Notes

Si &#95; &#95; WRL_STRICT &#95; &#95; est défini, une erreur d’assertion est émise si n’est pas dérivée de la classe de base spécifiée dans le paramètre de modèle de classe [RuntimeClass](../windows/runtimeclass-class.md), ou n’est pas configuré avec le WinRt ou WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) valeur d’énumération.

## <a name="requirements"></a>Configuration requise

**En-tête :** module.h

**Espace de noms :** Microsoft::WRL

## <a name="see-also"></a>Voir aussi

[SimpleActivationFactory, classe](../windows/simpleactivationfactory-class.md)