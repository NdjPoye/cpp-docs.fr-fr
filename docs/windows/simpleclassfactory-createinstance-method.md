---
title: "Simpleclassfactory::CreateInstance, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::SimpleClassFactory::CreateInstance
dev_langs: C++
helpviewer_keywords: CreateInstance method
ms.assetid: 17b7947a-2608-49d9-b730-fef76501c9bc
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 68778eb1b5421cfcf22261d8b1c1efd99bc32c50
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="simpleclassfactorycreateinstance-method"></a>SimpleClassFactory::CreateInstance, méthode

Crée une instance de l’interface spécifiée.

## <a name="syntax"></a>Syntaxe

```cpp
STDMETHOD( CreateInstance )(
   _Inout_opt_ IUnknown* pUnkOuter,
   REFIID riid,
   _Deref_out_ void** ppvObject
);
```

### <a name="parameters"></a>Paramètres

*pUnkOuter*  
Doit être `nullptr`; sinon, la valeur de retour est CLASS_E_NOAGGREGATION.

SimpleClassFactory ne prend pas en charge d’agrégation. Si l’agrégation étaient pris en charge et de l’objet en cours de création faisait partie d’un agrégat, `pUnkOuter` serait un pointeur vers l’interface IUnknown de contrôle de l’agrégat.

*riid*  
ID d’interface de l’objet à créer.

*ppvObject*  
Lorsque cette opération se termine, pointeur vers une instance de l’objet spécifié par le `riid` paramètre.

## <a name="return-value"></a>Valeur de retour

S_OK si l'opération réussit. Sinon, une valeur HRESULT indique l'erreur.

## <a name="remarks"></a>Notes

Si &#95; &#95; WRL_STRICT &#95; &#95; est défini, une erreur d’assertion est émise si n’est pas dérivée de la classe de base spécifiée dans le paramètre de modèle de classe [RuntimeClass](../windows/runtimeclass-class.md), ou n’est pas configuré avec les ClassicCom WinRtClassicComMix [RuntimeClassType ](../windows/runtimeclasstype-enumeration.md) valeur d’énumération.

## <a name="requirements"></a>Configuration requise

**En-tête :** module.h

**Espace de noms :** Microsoft::WRL

## <a name="see-also"></a>Voir aussi

[SimpleClassFactory, classe](../windows/simpleclassfactory-class.md)